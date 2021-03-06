---
title: "如何：在 Windows 應用程式中提供說明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0f407f1c17c67ec99f4499b89c49932a4ba6d32c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-provide-help-in-a-windows-application"></a>如何：在 Windows 應用程式中提供說明
您可以使用的<xref:System.Windows.Forms.HelpProvider>附加至 Windows Form 上的特定控制項的說明檔內的 [說明] 主題的元件。 說明檔可以是 HTML 或 HTMLHelp 1.x 或更高的格式。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱 [Visual Studio 中的自訂開發設定](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-provide-help"></a>提供說明  
  
1.  從**工具箱**，拖曳<xref:System.Windows.Forms.HelpProvider>元件加入至表單。  
  
     此元件將位在 Windows Forms 設計工具底部的系統匣中。  
  
2.  在**屬性**視窗中，將<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>.chm、.col 或.htm 的說明檔的屬性。  
  
3.  選取您對您的表單，然後在另一個控制項**屬性**視窗中，將<xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>屬性。  
  
     這是透過傳遞的字串<xref:System.Windows.Forms.HelpProvider>元件至您召喚適當的 [說明] 主題的說明檔。  
  
4.  在**屬性**視窗中，將<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>屬性的值<xref:System.Windows.Forms.HelpNavigator>列舉型別。  
  
     這會決定將 **HelpKeyword** 屬性傳遞給說明系統的方式。 下表顯示可能的設定和其描述。  
  
    |成員名稱|描述|  
    |-----------------|-----------------|  
    |AssociateIndex|指定在指定的 URL 中執行所指定主題的索引。|  
    |Find|指定顯示所指定 URL 的搜尋頁面。|  
    |索引|指定顯示所指定 URL 的索引。|  
    |KeywordIndex|指定要搜尋的關鍵字以及要在指定的 URL 中採取的動作。|  
    |TableOfContents|指定顯示 HTML 1.0 說明檔的目錄。|  
    |主題|指定顯示指定之 URL 所參考的主題。|  
  
 在執行階段，按下 F1 時控制項，您已設定為**HelpKeyword**和**HelpNavigator**屬性 — 具有焦點會開啟說明檔案，與相關聯<xref:System.Windows.Forms.HelpProvider>元件。  
  
 目前，**HelpNamespace** 屬性支援下列三種格式的說明檔：HTMLHelp 1.x、HTMLHelp 2.0 和 HTML。 因此，您可以將 **HelpNamespace** 屬性設定為 http:// 位址，例如網頁。 如果這麼做，則會開啟將 **HelpKeyword** 屬性中所指定的字串用作錨點之網頁的預設瀏覽器。 錨點是用來跳到 HTML 網頁的特定組件。  
  
> [!IMPORTANT]
>  請先仔細檢查用戶端所傳送的任何資訊，再將它用於應用程式中。 惡意使用者可能會嘗試傳送或插入可執行的指令碼、SQL 陳述式或其他程式碼。 在顯示使用者的輸入、將它儲存在資料庫中，或使用它之前，請先檢查它未包含可能不安全的資訊。 一般檢查方式是在您收到來自使用者的輸入時，使用規則運算式來尋找關鍵字，例如 "SCRIPT"。  
  
 您也可以使用<xref:System.Windows.Forms.HelpProvider>顯示快顯的說明，即使您已經設定要顯示在 Windows Form 上控制項的說明檔案的元件。 如需詳細資訊，請參閱[如何：顯示快顯說明](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)。  
  
## <a name="see-also"></a>另請參閱  
 [操作說明：顯示快顯說明](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [使用工具提示來顯示控制項說明](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [整合 Windows Forms 中的使用者說明](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
