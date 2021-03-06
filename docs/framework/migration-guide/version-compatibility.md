---
title: ".NET Framework 的版本相容性"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework 4.5, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 166d61339d2b74f378b50ade4b78fd41e9692f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="version-compatibility-in-the-net-framework"></a>.NET Framework 的版本相容性
回溯相容性表示針對特定平台版本開發的應用程式將會在該平台的較新版本上執行。 .NET Framework 嘗試最大化回溯相容性：針對某一個 .NET Framework 版本撰寫的原始程式碼應該在較新版本的 .NET Framework 上編譯，而且在某一個 .NET Framework 版本上執行之二進位檔的行為應該與較新版本的 .NET Framework 相同。  
  
<a name="Apps"></a>   
## <a name="version-compatibility-for-apps"></a>應用程式的版本相容性  
 根據預設，應用程式會在其建置所針對的 .NET Framework 版本上執行。 如果該版本不存在，而且應用程式組態檔並未定義支援的版本，則可能會發生 .NET Framework 初始化錯誤。 在此例中，嘗試執行應用程式的作業將會失敗。  
  
 若要定義應用程式執行所在的特定版本，請將一個或多個 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 項目新增至應用程式的組態檔。 每一個 `<supportedRuntime>` 項目都會列出支援的執行階段版本，最先指定的是最優先的版本，而最後指定的則是優先順序最低的版本。  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v2.0.50727" />  
      <supportedRuntime version="v4.0" />  
   </startup>  
</configuration>  
```  
  
 如需詳細資訊，請參閱[如何：設定應用程式以支援 .NET Framework 4 或 4.x](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)。  
  
## <a name="version-compatibility-for-components"></a>元件的版本相容性  
 應用程式可以控制其執行所在的 .NET Framework 版本，但是元件則無法控制。 元件和類別庫會在特定應用程式的內容中載入，因此會自動在應用程式執行所在的 .NET Framework 版本上執行。  
  
 由於這項限制，所以相容性保證對於元件特別重要。 從 .NET Framework 4 開始，您可以指定元件在多個版本中維持相容所需的程度，方法是將 <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType> 屬性套用至該元件。 工具可以使用這個屬性來偵測將來的元件版本中，是否有可能違反相容性保證的狀況。  
  
## <a name="backward-compatibility-and-the-net-framework-45"></a>回溯相容性和 .NET Framework 4.5  
 .NET Framework 4.5 及更新版本會與舊版相容以舊版.NET Framework 所建置的應用程式。 換句話說，應用程式和元件使用舊版建置運作而不需修改.NET Framework 4.5 及更新版本。 不過，根據預設，應用程式上執行的開發時，common language runtime 的版本，您可能必須提供要啟用.NET Framework 4.5 或更新版本上執行應用程式的組態檔。 如需詳細資訊，請參閱本文前面的[應用程式的版本相容性](#Apps)一節。  
  
 在實際操作中，.NET Framework 中似乎前後不一致的變更以及程式設計技術的變更可能會破壞此相容性。 例如，.NET Framework 4.5 中的效能改良可能會暴露在舊版不會發生的競爭情況。 同樣地，使用 .NET Framework 組件的硬式編碼路徑、搭配特定版本的 .NET Framework 執行相等比較以及使用反映來取得私用欄位的值，都不是具有回溯相容性的作法。 此外，每一個 .NET Framework 版本都包含可能會影響某些應用程式與元件之相容性的 Bug 修正和安全性相關的變更。  
  
 如果您的應用程式或元件未如預期般在.NET Framework 4.5 (包括其點發行版本中， [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]、 4.5.2、 4.6、 4.6.1、 4.6.2、 4.7 或 4.7.1，使用下列檢查清單：  
  
-  如果您的應用程式是在任何版本的.NET Framework 4.0 為開頭的.NET Framework 上執行，請參閱[.NET Framework 中的應用程式相容性](application-compatibility.md)產生目標的.NET Framework 版本之間的變更清單以及您的應用程式執行所在的版本。  

- 如果您有.NET Framework 3.5 應用程式，請參閱[.NET Framework 4 移轉問題](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)。

- 如果您有.NET Framework 2.0 應用程式，請參閱[.NET Framework 3.5 SP1 中的變更](http://go.microsoft.com/fwlink/?LinkId=186989)。

- 如果您有.NET Framework 1.1 應用程式，請參閱[.NET Framework 2.0 中的變更](http://go.microsoft.com/fwlink/?LinkID=125263)。  
  
-   如果您正在重新編譯現有的程式碼執行.NET Framework 4.5 或其點發行版本，或如果您正在開發的應用程式或元件為目標的新版本[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]或其點發行版本從現有來源的程式碼基底，檢查[什麼是類別庫中的過時](../../../docs/framework/whats-new/whats-obsolete.md)的過時類型和成員，並套用所述的因應措施。 (之前編譯的程式碼將會針對已標示為過時的型別和成員繼續執行)。  
  
-   如果您判斷 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中的某項變更已經破壞您的應用程式，請查看[執行階段設定結構描述](../../../docs/framework/configure-apps/file-schema/runtime/index.md)來判斷您是否可以在應用程式組態檔中使用執行階段設定，以還原舊版行為。  
  
-   如果您遇到未記載的問題，請記錄 [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815) 錯誤 (bug)，然後連絡 [netfxcf@microsoft.com](mailto:netfxcf@microsoft.com) 並提供錯誤 (bug) 編號。  
  
## <a name="compatibility-and-side-by-side-execution"></a>相容性和並存執行  
 如果您找不到問題的適當因應措施，請記得 .NET Framework 4.5 (或其中一個點版本) 會與版本 1.1、2.0 和 3.5 並存執行，而且是取代第 4 版的就地更新。 若是以 1.1、2.0 和 3.5 版為目標的應用程式，您可以在目標電腦上安裝適當的 .NET Framework 版本，以便在最佳環境中執行應用程式。 如需並存執行的詳細資訊，請參閱[並存執行](../../../docs/framework/deployment/side-by-side-execution.md)。  
  
## <a name="see-also"></a>另請參閱  
 [新功能](../../../docs/framework/whats-new/index.md)  
 [類別庫中已淘汰的功能](../../../docs/framework/whats-new/whats-obsolete.md)  
 [應用程式相容性](../../../docs/framework/migration-guide/application-compatibility.md)  
 [Microsoft .NET Framework 支援週期原則](http://go.microsoft.com/fwlink/p/?LinkId=248212)  
 [.NET Framework 4 移轉問題](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)
