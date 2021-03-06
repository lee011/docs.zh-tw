---
title: "&lt;qualifyAssembly&gt;項目"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 521bbccd83f224cc824dae41309715d65472454e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="ltqualifyassemblygt-element"></a>&lt;qualifyAssembly&gt;項目
指定應該在使用部分名稱時以動態方式載入的組件的完整名稱。  
  
 \<configuration>  
\<執行階段 >  
\<assemblyBinding >  
\<qualifyAssembly >  
  
## <a name="syntax"></a>語法  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|`partialName`|必要屬性。<br /><br /> 指定出現在程式碼中的組件部分的名稱。|  
|`fullName`|必要屬性。<br /><br /> 指定出現在全域組件快取中的組件的完整名稱。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|說明|  
|-------------|-----------------|  
|`assemblyBinding`|包含有關組件版本重新導向和組件位置的資訊。|  
|`configuration`|通用語言執行平台和 .NET Framework 應用程式所使用之每個組態檔中的根項目。|  
|`runtime`|包含有關組件繫結和記憶體回收的資訊。|  
  
## <a name="remarks"></a>備註  
 呼叫<xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>使用部分的組件名稱的方法會導致 common language runtime 的組件只能在應用程式基底目錄中尋找。 使用 **\<qualifyAssembly >**應用程式組態檔中提供完整的組件資訊 （名稱、 版本、 公開金鑰語彙基元和文化特性），而造成 common language runtime 来搜尋的項目全域組件快取中的組件。  
  
 **FullName**屬性必須包含組件識別四個欄位： 名稱、 版本、 公開金鑰語彙基元和文化特性。 **PartialName**屬性部分必須參考的組件。 您至少必須指定組件的文字名稱 （最常見的情況），但您也可以包含版本、 公開金鑰語彙基元或文化特性 （或任何組合的四個，但是並非所有的四個欄位）。 **PartialName**必須符合您的呼叫中指定的名稱。 例如，您無法指定`"math"`為**partialName**屬性在組態檔，並呼叫`Assembly.Load("math, Version=3.3.3.3")`程式碼中。  
  
## <a name="example"></a>範例  
 下列範例邏輯上會呼叫`Assembly.Load("math")`到`Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱  
 [執行階段設定結構描述](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [執行階段如何找出組件](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [NIB： 部分組件參考](http://msdn.microsoft.com/en-us/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
