---
title: "&lt;TimeSpan_LegacyFormatMode&gt;項目"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2724b3811e9cc28888a9beac0c1ed77092302c3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="lttimespanlegacyformatmodegt-element"></a>&lt;TimeSpan_LegacyFormatMode&gt;項目
決定是否執行階段會保留舊版的行為在格式化作業與<xref:System.TimeSpan?displayProperty=nameWithType>值。  
  
 \<configuration>  
\<執行階段 >  
< TimeSpan_LegacyFormatMode >  
  
## <a name="syntax"></a>語法  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|`enabled`|必要屬性。<br /><br /> 指定執行階段是否使用傳統的格式化行為<xref:System.TimeSpan?displayProperty=nameWithType>值。|  
  
## <a name="enabled-attribute"></a>啟用屬性  
  
|值|說明|  
|-----------|-----------------|  
|`false`|執行階段不會還原舊版格式的行為。|  
|`true`|執行階段會還原舊版格式的行為。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|`configuration`|通用語言執行平台和 .NET Framework 應用程式所使用之每個組態檔中的根項目。|  
|`runtime`|包含有關執行階段初始化選項的資訊。|  
  
## <a name="remarks"></a>備註  
 從開始[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]、<xref:System.TimeSpan?displayProperty=nameWithType>結構實作<xref:System.IFormattable>介面，並支援格式設定與標準和自訂格式字串的作業。 如果剖析方法時，遇到不支援的格式規範或格式字串，它會擲回<xref:System.FormatException>。  
  
 在舊版的.NET Framework 中，<xref:System.TimeSpan>結構不會實作<xref:System.IFormattable>和不支援格式字串。 不過，許多開發人員不小心假設<xref:System.TimeSpan>未支援的格式字串集，並使用它們在[複合格式化作業](../../../../../docs/standard/base-types/composite-formatting.md)與這類方法<xref:System.String.Format%2A?displayProperty=nameWithType>。 一般情況下，如果型別實作<xref:System.IFormattable>並支援格式字串，呼叫格式化方法不支援的格式字串通常會擲回<xref:System.FormatException>。 不過，因為<xref:System.TimeSpan>並未實作<xref:System.IFormattable>，執行階段略過的格式字串，並改為呼叫<xref:System.TimeSpan.ToString?displayProperty=nameWithType>方法。 這表示，雖然格式字串不會影響格式化作業，其目前狀態不會造成<xref:System.FormatException>。  
  
 中的舊版程式碼傳遞的複合格式方法和格式字串無效，而且無法重新編譯該程式碼的情況下，您可以使用`<TimeSpan_LegacyFormatMode>`項目還原舊版<xref:System.TimeSpan>行為。 當您將`enabled`此項目的屬性`true`複合格式方法的呼叫中的結果、<xref:System.TimeSpan.ToString?displayProperty=nameWithType>而非<xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>，和<xref:System.FormatException>不會擲回。  
  
## <a name="example"></a>範例  
 下列範例會具現化<xref:System.TimeSpan>物件，並嘗試使用下列格式<xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType>方法藉由使用不支援的標準格式字串。  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 當您執行此範例[!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]或在較早的版本，它會顯示下列輸出：  
  
```  
12:30:45  
```  
  
 如果您在 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] (含) 以後版本上執行範例，會出現相當不同的輸出結果：  
  
```  
Invalid Format  
```  
  
 不過，如果您將下列組態檔加入範例的目錄中，然後在 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] (含) 以後版本上執行該範例，則輸出會與在 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] 上執行範例時所產生的輸出完全相同。  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱  
 [執行階段設定結構描述](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [組態檔結構描述](../../../../../docs/framework/configure-apps/file-schema/index.md)
