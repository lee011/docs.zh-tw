---
title: "如何：顯示 Windows Form 的對話方塊"
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
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3f827e9052260c1b836246d38c55e2cb2a9e5cc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>如何：顯示 Windows Form 的對話方塊
您在您的應用程式中顯示任何其他形式的相同方式顯示的對話方塊。 執行應用程式時，會自動載入啟動表單。 若要讓第二個表單或對話方塊會出現在應用程式中，撰寫程式碼載入和顯示它。 同樣地，若要讓表單或對話方塊消失，請撰寫程式碼來卸載或隱藏它。  
  
### <a name="to-display-a-dialog-box"></a>若要顯示的對話方塊  
  
1.  瀏覽至您要開啟對話方塊中的事件處理常式。 選取功能表命令時，按一下按鈕時，或任何其他事件發生時，就可能發生這情況。  
  
2.  事件處理常式中加入程式碼，以開啟對話方塊。 在此範例中，按鈕 click 事件用來顯示對話方塊：  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```
