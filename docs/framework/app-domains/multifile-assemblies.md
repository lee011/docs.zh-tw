---
title: "多檔案組件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fead0a944b464ffd8f72dca6da33fd97404fe2d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="multifile-assemblies"></a>多檔案組件
您可以搭配使用命令列編譯器或 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 與 Visual C++，來建立多個組件。 組件中的一個檔案必須包含組件資訊清單。 啟動應用程式的組件也必須包含進入點，例如 Main 或 WinMain 方法。  
  
 例如，假設您的應用程式包含兩個程式碼模組：Client.cs 和 Stringer.cs。 Stringer.cs 會建立 Client.cs 中程式碼所參考的 `myStringer` 命名空間。 Client.cs 包含 `Main` 方法，而此方法是應用程式進入點。 在此範例中，您會編譯這兩個程式碼模組，然後建立包含組件資訊清單的第三個檔案，而組件資訊清單可啟動應用程式。 組件資訊清單同時參考 `Client` 和 `Stringer` 模組。  
  
> [!NOTE]
>  多檔案組件只能有一個進入點，即使組件有多個程式碼模組也是一樣。  
  
 您有數個原因可能想要建立多檔案組件：  
  
-   合併以不同語言撰寫的模組。 這是建立多檔案組件的最常見原因。  
  
-   將很少使用的類型放在需要時才下載的模組中，以最佳化應用程式的下載。  
  
    > [!NOTE]
    >  如果您要使用 Microsoft Internet Explorer 建立將使用 `<object>` 標記所下載的應用程式，則一定要建立多檔案組件。 在此情況下，您會建立與程式碼模組不同的檔案，而此檔案只包含組件資訊清單。 Internet Explorer 會先下載組件資訊清單，然後建立背景工作執行緒來下載所需的任何額外模組或組件。 正在下載包含組件資訊清單的檔案時，Internet Explorer 不會回應使用者輸入。 包含組件資訊清單的檔案越小，Internet Explorer 無回應的時間就越短。  
  
-   合併數個開發人員所撰寫的程式碼模組。 雖然每個開發人員都可以將每個程式碼模組編譯為組件，但是將所有模組都放入多檔案組件時，這個動作會將某些未公開的類型強制為公開。  
  
 在您建立組件之後，可以簽署包含組件資訊清單 (因此包含組件) 的檔案，也可以指定檔案 (和組件) 的強式名稱，並將它放在全域組件快取中。  
  
## <a name="see-also"></a>另請參閱  
 [操作說明：建置多檔案組件](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [使用組件設計程式](../../../docs/framework/app-domains/programming-with-assemblies.md)
