---
title: "如何：使用 Windows Form Timer 元件以設定的間隔執行程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af16d1e2c3ef683a6e3da4197a30af58d7758a0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a>如何：使用 Windows Form Timer 元件以設定的間隔執行程序
您有時可能會想要建立一個程序，依特定時間間隔執行，直到迴圈完成，或是在經過設定的時間間隔之後執行。 <xref:System.Windows.Forms.Timer> 元件可讓您建立這樣的程序。  
  
 這個元件是專為 Windows Form 環境所設計。 如果您需要適用於伺服器環境的計時器，請參閱[伺服器架構的計時器簡介](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。  
  
> [!NOTE]
>  使用 <xref:System.Windows.Forms.Timer> 元件時，有一些限制。 如需詳細資訊，請參閱[Windows Form Timer 元件的 Interval 屬性限制](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)。  
  
### <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a>若要使用計時器元件，依設定的間隔來執行程序  
  
1.  將 <xref:System.Windows.Forms.Timer> 加入您的表單。 請參閱下面的＜範例＞一節，以取得以程式設計方式執行此動作的範例。 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 也有將元件加入表單的支援。 另請參閱[如何： 新增控制項沒有使用者介面的 Windows form](http://msdn.microsoft.com/library/becyw7bz\(v=vs.110\))。  
  
2.  設定計時器的 <xref:System.Windows.Forms.Timer.Interval%2A> 屬性 (以毫秒為單位)。 此屬性可決定，經過多少時間之後，會再執行該程序。  
  
    > [!NOTE]
    >  計時器事件發生的頻率愈高，就會用愈多的處理器時間來回應事件。 這會降低整體效能。 請不要設定小於您所需的間隔。  
  
3.  在 <xref:System.Windows.Forms.Timer.Tick> 事件處理常式中撰寫適當的程式碼。 您在這個事件中撰寫的程式碼，將會依 <xref:System.Windows.Forms.Timer.Interval%2A> 屬性中指定的間隔執行。  
  
4.  請將 <xref:System.Windows.Forms.Timer.Enabled%2A> 屬性設為 `true`，以啟動計時器。 <xref:System.Windows.Forms.Timer.Tick> 事件會開始發生，依所設定的間隔來執行您的程序。  
  
5.  在適當的時間，將 <xref:System.Windows.Forms.Timer.Enabled%2A> 屬性設為 `false`，使程序停止再次執行。 將間隔設`0`不會造成停止計時器。  
  
## <a name="example"></a>範例  
 第一個程式碼範例會追蹤一天的時間，以一秒為增量單位。 它會在表單上使用 <xref:System.Windows.Forms.Button>、<xref:System.Windows.Forms.Label> 和 <xref:System.Windows.Forms.Timer> 元件。 <xref:System.Windows.Forms.Timer.Interval%2A> 屬性設為 1000 (等於 1 秒)。 在 <xref:System.Windows.Forms.Timer.Tick> 事件中，標籤的標題設為目前的時間。 按一下按鈕時，<xref:System.Windows.Forms.Timer.Enabled%2A> 屬性會設為 `false`，使計時器停止更新標籤的標題。 下列程式碼範例需要您擁有的表單具有<xref:System.Windows.Forms.Button>控制項，名為`Button1`、<xref:System.Windows.Forms.Timer>控制項，名為`Timer1`，和<xref:System.Windows.Forms.Label>控制項，名為`Label1`。  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)     
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,    
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,   
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a>範例  
 這個第二個程式碼範例會每隔 600 毫秒執行一次程序，直到迴圈完成為止。 下列程式碼範例需要您擁有的表單具有<xref:System.Windows.Forms.Button>控制項，名為`Button1`、<xref:System.Windows.Forms.Timer>控制項，名為`Timer1`，和<xref:System.Windows.Forms.Label>控制項，名為`Label1`。  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)     
{  
   if (counter >= 10)   
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)   
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.Timer>  
 [Timer 元件](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Timer 元件概觀](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
