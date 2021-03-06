---
title: "如何：叫用委派方法 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea94d4bb26e168667fd75c6928e52261f230c85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>如何：叫用委派方法 (Visual Basic)
這個範例示範如何將方法產生關聯的委派，然後叫用委派透過該方法。  
  
### <a name="create-the-delegate-and-matching-procedures"></a>建立委派和比對程序  
  
1.  建立名為委派`MySubDelegate`。  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  包含具有相同的簽章與委派的方法將類別宣告。  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  定義方法，以建立委派的執行個體，並叫用方法呼叫內建和委派關聯`Invoke`方法。  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a>另請參閱  
 [Delegate 陳述式](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [委派](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [多執行緒應用程式](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
