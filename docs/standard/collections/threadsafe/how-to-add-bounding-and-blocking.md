---
title: "如何：將界限和封鎖功能加入至集合"
description: "如何：將界限和封鎖功能加入至集合"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 678d5df2-af63-418f-8b2a-e0be7ea2d77b
translationtype: Human Translation
ms.sourcegitcommit: c15f2da15c6448cf1c36dea2d5fd53e734bb6608
ms.openlocfilehash: 63a59dbcc323f392e3bf2991b1439aa062382623

---

# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>如何：將界限和封鎖功能加入至集合

這個範例示範如何實作類別中的 [System.Collections.Concurrent.IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1) 介面，然後使用類別執行個體作為 [System.Collections.Concurrent.BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) 的內部儲存機制，以將界限和封鎖功能新增至自訂集合類別。 如需界限和封鎖的詳細資訊，請參閱 [BlockingCollection 概觀](blockingcollection-overview.md)。

## <a name="example"></a>範例

自訂集合類別是優先順序層級呈現為 [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) 物件陣列的基本優先順序佇列。 在每個佇列內不會執行額外的排序。

在用戶端程式碼中，會啟動三項工作。 第一項工作只會輪詢鍵盤按鍵，可在執行期間隨時取消。 第二項工作是生產者執行緒；它會將新的項目新增至封鎖回收，並根據隨機值來指定每個項目的優先順序。 第三項工作是在項目可供使用時將其從集合中移除。 

您可以讓其中一個執行緒的執行速度快於另一個執行緒，來調整應用程式的行為。 如果生產者的執行速度較快，則會注意到界限功能，原因是封鎖回收在已包含建構函式中所指定的項目數時會防止新增項目。 如果消費者的執行速度較快，您會在消費者等待新增項目時注意到封鎖功能。

```csharp
namespace ProdConsumerCS
{
    using System;
    using System.Collections;
    using System.Collections.Concurrent;
    using System.Collections.Generic;
    using System.Diagnostics;
    using System.Linq;
    using System.Text;
    using System.Threading;
    using System.Threading.Tasks;

    // Implementation of a priority queue that has bounding and blocking functionality.
    public class SimplePriorityQueue<TPriority, TValue> : IProducerConsumerCollection<KeyValuePair<int, TValue>>
    {
        // Each internal queue in the array represents a priority level. 
        // All elements in a given array share the same priority.
        private ConcurrentQueue<KeyValuePair<int, TValue>>[] _queues = null;

        // The number of queues we store internally.
        private int priorityCount = 0;
        private int m_count = 0;

        public SimplePriorityQueue(int priCount)
        {
            this.priorityCount = priCount;
            _queues = new ConcurrentQueue<KeyValuePair<int, TValue>>[priorityCount];
            for (int i = 0; i < priorityCount; i++)
            {
                _queues[i] = new ConcurrentQueue<KeyValuePair<int, TValue>>();
            }
        }

        // IProducerConsumerCollection members
        public bool TryAdd(KeyValuePair<int, TValue> item)
        {
            _queues[item.Key].Enqueue(item);
            Interlocked.Increment(ref m_count);
            return true;
        }

        public bool TryTake(out KeyValuePair<int, TValue> item)
        {
            bool success = false;

            // Loop through the queues in priority order
            // looking for an item to dequeue.
            for (int i = 0; i < priorityCount; i++)
            {
                // Lock the internal data so that the Dequeue
                // operation and the updating of m_count are atomic.
                lock (_queues)
                {
                    success = _queues[i].TryDequeue(out item);
                    if (success)
                    {
                        Interlocked.Decrement(ref m_count);
                        return true;
                    }
                }
            }

            // If we get here, we found nothing. 
            // Assign the out parameter to its default value and return false.
            item = new KeyValuePair<int, TValue>(0, default(TValue));
            return false;
        }

        public int Count
        {
            get { return m_count; }
        }

        // Required for ICollection
        void ICollection.CopyTo(Array array, int index)
        {
            CopyTo(array as KeyValuePair<int, TValue>[], index);
        }

        // CopyTo is problematic in a producer-consumer.
        // The destination array might be shorter or longer than what 
        // we get from ToArray due to adds or takes after the destination array was allocated.
        // Therefore, all we try to do here is fill up destination with as much
        // data as we have without running off the end.                
        public void CopyTo(KeyValuePair<int, TValue>[] destination, int destStartingIndex)
        {
            if (destination == null) throw new ArgumentNullException();
            if (destStartingIndex < 0) throw new ArgumentOutOfRangeException();

            int remaining = destination.Length;
            KeyValuePair<int, TValue>[] temp = this.ToArray();
            for (int i = 0; i < destination.Length && i < temp.Length; i++)
            {
                destination[i] = temp[i];
            }    
        }

        public KeyValuePair<int, TValue>[] ToArray()
        {
            KeyValuePair<int, TValue>[] result;

            lock (_queues)
            {
                result = new KeyValuePair<int, TValue>[this.Count];
                int index = 0;
                foreach (var q in _queues)
                {
                    if (q.Count > 0)
                    {
                        q.CopyTo(result, index);
                        index += q.Count;
                    }
                }
                return result;
            }
        }

        IEnumerator IEnumerable.GetEnumerator()
        {
            return GetEnumerator();
        }

        public IEnumerator<KeyValuePair<int, TValue>> GetEnumerator()
        {
            for (int i = 0; i < priorityCount; i++)
            {
                foreach (var item in _queues[i])
                    yield return item;
            }
        }

        public bool IsSynchronized
        {
            get { throw new NotSupportedException(); }
        }

        public object SyncRoot
        {
            get { throw new NotSupportedException(); }
        }
    }

    public class TestBlockingCollection
    {
        static void Main()
        {

            int priorityCount = 7;
            SimplePriorityQueue<int, int> queue = new SimplePriorityQueue<int, int>(priorityCount);
            var bc = new BlockingCollection<KeyValuePair<int, int>>(queue, 50);

            CancellationTokenSource cts = new CancellationTokenSource();

            Task.Run(() =>
                {
                    if (Console.ReadKey(true).KeyChar == 'c')
                    {
                        cts.Cancel();
                    }
                });

            // Create a Task array so that we can Wait on it
            // and catch any exceptions, including user cancellation.
            Task[] tasks = new Task[2];

            // Create a producer thread. You can change the code to 
            // make the wait time a bit slower than the consumer 
            // thread to demonstrate the blocking capability.
            tasks[0] = Task.Run(() =>
            {
                // We randomize the wait time, and use that value
                // to determine the priority level (Key) of the item.
                Random r = new Random();

                int itemsToAdd = 40;
                int count = 0;
                while (!cts.Token.IsCancellationRequested && itemsToAdd-- > 0)
                {
                    int waitTime = r.Next(2000);
                    int priority = waitTime % priorityCount;
                    var item = new KeyValuePair<int, int>(priority, count++);

                    bc.Add(item);
                    Console.WriteLine("added pri {0}, data={1}", item.Key, item.Value);
                }
                Console.WriteLine("Producer is done adding.");
                bc.CompleteAdding();
            },
             cts.Token);

            //Give the producer a chance to add some items.
            Thread.SpinWait(1000000);

            // Create a consumer thread. The wait time is
            // a bit slower than the producer thread to demonstrate
            // the bounding capability at the high end. Change this value to see
            // the consumer run faster to demonstrate the blocking functionality
            // at the low end.

            tasks[1] = Task.Run(() =>
                {
                    while (!bc.IsCompleted && !cts.Token.IsCancellationRequested)
                    {
                        Random r = new Random();
                        int waitTime = r.Next(2000);
                        Thread.SpinWait(waitTime * 70);

                        // KeyValuePair is a value type. Initialize to avoid compile error in if(success)
                        KeyValuePair<int, int> item = new KeyValuePair<int, int>();
                        bool success = false;
                        success = bc.TryTake(out item);
                        if (success)
                        {
                            // Do something useful with the data.
                            Console.WriteLine("removed Pri = {0} data = {1} collCount= {2}", item.Key, item.Value, bc.Count);
                        }
                        else
                            Console.WriteLine("No items to retrieve. count = {0}", bc.Count);
                    }
                    Console.WriteLine("Exited consumer loop");
                },
                cts.Token);

            try 
            {
                Task.WaitAll(tasks, cts.Token);
            }
            catch (OperationCanceledException e) 
            {
                if (e.CancellationToken == cts.Token)
                    Console.WriteLine("Operation was canceled by user. Press any key to exit");
            }
            catch (AggregateException ae) 
            {
                foreach (var v in ae.InnerExceptions)
                    Console.WriteLine(v.Message);
            }
            finally 
            {
                cts.Dispose();
            }

            Console.ReadKey(true);

        }
    }

}
```

[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) 的儲存體預設是 [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1)。

## <a name="see-also"></a>另請參閱

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[安全執行緒集合](index.md)

[BlockingCollection Overview](blockingcollection-overview.md)



<!--HONumber=Nov16_HO1-->

