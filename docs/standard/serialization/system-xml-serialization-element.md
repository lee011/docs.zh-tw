---
title: "&lt;system.xml.serialization&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d70879d5e0a579af7b5c507910d4dcb19ddee52
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="ltsystemxmlserializationgt-element"></a>&lt;system.xml.serialization&gt; 元素
用來控制 XML 序列化的最上層項目。 如需組態檔的詳細資訊，請參閱[組態檔結構描述](../../../docs/framework/configure-apps/file-schema/index.md)。  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>語法  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
 無。  
  
### <a name="child-elements"></a>子項目  
  
|項目|說明|  
|-------------|-----------------|  
|[\<dateTimeSerialization> 元素](../../../docs/standard/serialization/datetimeserialization-element.md)|判斷 <xref:System.DateTime> 物件的序列化模式。|  
|[\<schemaImporterExtensions>元素](../../../docs/standard/serialization/schemaimporterextensions-element.md)|包含 <xref:System.Xml.Serialization.XmlSchemaImporter> 用來對應 XSD 型別至 .NET Framework 型別的型別。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|說明|  
|-------------|-----------------|  
|[\<configuration> 項目](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Common Language Runtime 與 .NET Framework 應用程式使用的所有組態檔中的根項目。|  
  
## <a name="example"></a>範例  
 下列程式碼範例描述如何指定 <xref:System.DateTime> 物件的序列化模式，以及在對應 XSD 型別至 .NET Framework 型別時 <xref:System.Xml.Serialization.XmlSchemaImporter> 使用的新增型別。  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [組態檔結構描述](../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<dateTimeSerialization> 元素](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [\<schemaImporterExtensions>元素](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [\<xmlSchemaImporterExtensions> 的 \<add> 項目](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)
