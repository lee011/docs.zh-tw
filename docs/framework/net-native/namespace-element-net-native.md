---
title: "&lt;Namespace&gt; 項目 (.NET Native)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 014dc690d034c27f0f004172fb8108249bb5c89b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="ltnamespacegt-element-net-native"></a>&lt;Namespace&gt; 項目 (.NET Native)
將執行階段反映原則套用至指定命名空間中的所有類型。  
  
## <a name="syntax"></a>語法  
  
```xml  
<Namespace Name="namespace_name"   
           Activate="policy_type"   
           Browse="policy_type" />  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
           DataContractSerializer="policy_setting"  
           DataContractJsonSerializer="policy_setting"  
           XmlSerializer="policy_setting"  
           MarshalObject="policy_setting"  
           MarshalDelegate="policy_setting"  
           MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|屬性類型|說明|  
|---------------|--------------------|-----------------|  
|`Name`|一般|必要屬性。 指定命名空間的名稱。|  
|`Activate`|反射|選擇性屬性。 控制建構函式的執行階段存取，以便啟動執行個體。|  
|`Browse`|反射|選擇性屬性。 控制程式項目相關資訊的查詢，但不會啟用任何執行階段存取。|  
|`Dynamic`|反射|選擇性屬性。 控制對所有類型成員 (包括建構函式、方法、欄位、屬性和事件) 的執行階段存取，以啟用動態程式設計。|  
|`Serialize`|序列化|選擇性屬性。 控制建構函式、欄位和屬性的執行階段存取，以便 Newtonsoft JSON 序列化程式等程式庫可對類型執行個體進行序列化和還原序列化。|  
|`DataContractSerializer`|序列化|選擇性屬性。 控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 類別的序列化原則。|  
|`DataContractJsonSerializer`|序列化|選擇性屬性。 控制使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 類別的 JSON 序列化原則。|  
|`XmlSerializer`|序列化|選擇性屬性。 控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 類別的 XML 序列化原則。|  
|`MarshalObject`|Interop|選擇性屬性。 控制 Windows 執行階段和 COM 之參考類型的封送處理原則。|  
|`MarshalDelegate`|Interop|選擇性屬性。 控制將委派類型當作函式指標封送處理至機器碼的原則。|  
|`MarshalStructure`|Interop|選擇性屬性。 控制將結構封送處理至機器碼的原則。|  
  
## <a name="name-attribute"></a>Name 屬性  
  
|值|說明|  
|-----------|-----------------|  
|*namespace_name*|命名空間名稱。 如果 \<Namespace> 項目是 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)、[\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 或 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) 項目的子項，則 *namespace_name* 必須是完整命名空間名稱。 如果 \<Namespace> 項目是另一個 \<Namespace> 項目的子項，則 *namespace_name* 必須是相對的命名空間名稱。|  
  
## <a name="all-other-attributes"></a>所有其他屬性  
  
|值|說明|  
|-----------|-----------------|  
|*policy_setting*|針對命名空間中的所有類型，要套用到此原則類型的設定。 可能的值為 `All`、`Auto`、`Excluded`、`Public`、`PublicAndInternal`、`Required Public`、`Required PublicAndInternal` 和 `Required All`。 如需詳細資訊，請參閱[執行階段指示詞原則設定](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。|  
  
### <a name="child-elements"></a>子元素  
  
|項目|描述|  
|-------------|-----------------|  
|`<Namespace>`|將執行階段反映原則套用至父命名空間中的所有類型。|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|將反映原則套用至類型。|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|將反映原則套用至建構的泛型類型。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|說明|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|做為整個應用程式的類型和類型成員的容器，這些類型和類型成員的中繼資料可在執行階段用於反映。 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 項目可以有零、一或多個 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) 項目。|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|將執行階段反映原則套用至指定組件中的所有類型。|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|定義包含類型和類型成員的組件，該類型和類型成員的中繼資料會在執行階段用於反映。 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 項目可以有零或一個 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) 項目。|  
|`<Namespace>`|將反映原則套用至父命名空間中的所有類型。|  
  
## <a name="remarks"></a>備註  
 `Activate`、`Browse`、`Dynamic` 和 `Serialize` 都是選用屬性。 如果都不存在，`<Namespace>` 元素只會用來做為子元素的容器。 如果存在，則 `<Namespace>` 元素會將執行階段反映原則套用至指定命名空間中的所有類型。  
  
 當它是 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) 項目的子項時，`<Namespace>` 項目會覆寫 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md) 項目定義的執行階段反映原則。  
  
## <a name="see-also"></a>另請參閱  
 [執行階段指示詞原則設定](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [執行階段指示詞 (rd.xml) 組態檔參考](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [執行階段指示詞項目](../../../docs/framework/net-native/runtime-directive-elements.md)
