---
title: "&lt;proxy&gt;項目 （網路設定）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7178527f369c698b0ab53aa41cb28dd0126436b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="ltproxygt-element-network-settings"></a>&lt;proxy&gt;項目 （網路設定）
定義 Proxy 伺服器。  
  
 \<configuration>  
\<system.net >  
\<defaultProxy >  
\<proxy >  
  
## <a name="syntax"></a>語法  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|**屬性**|**說明**|  
|-------------------|---------------------|  
|`autoDetect`|指定是否自動偵測 proxy。 預設值是 `unspecified`。|  
|`bypassonlocal`|指定是否略過本機資源的 proxy。 本機資源包括本機伺服器 （http://localhost、 http://loopback 或 http://127.0.0.1） 及沒有句號 (http://webserver) URI。 預設值是 `unspecified`。|  
|`proxyaddress`|指定 proxy 使用的 URI。|  
|`scriptLocation`|指定組態指令碼的位置。|  
|`usesystemdefault`|指定是否要使用 Internet Explorer proxy 設定。 如果設定為`true`，後續的屬性會覆寫 Internet Explorer proxy 設定。 預設值是 `unspecified`。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|**目**|**說明**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|設定超文字傳輸協定 (HTTP) 的 Proxy 伺服器。|  
  
## <a name="text-value"></a>文字值  
  
## <a name="remarks"></a>備註  
 `proxy`項目會定義應用程式 proxy 伺服器。 如果組態檔中沒有這個項目，.NET Framework 會在 Internet Explorer 中使用的 proxy 設定。  
  
 值`proxyaddress`屬性應該是語式正確的 Uniform Resource Indicator (URI)。  
  
 `scriptLocation`屬性會自動偵測 proxy 設定指令碼的參考。 <xref:System.Net.WebProxy>類別會嘗試找出在設定指令碼 (通常是具名 Wpad.dat) 時，當**使用自動設定指令碼**Internet Explorer 中選取選項。  
  
 使用`usesystemdefault`要移轉至 2.0 版的.NET Framework 1.1 版應用程式的屬性。  
  
 如果擲回例外狀況`proxyaddress`屬性會指定無效的預設 proxy。 例外狀況的 <xref:System.Exception.InnerException%2A> 屬性應該會有此錯誤的根本原因之詳細資訊。  
  
## <a name="configuration-files"></a>組態檔  
 此項目可以用於應用程式組態檔或電腦組態檔 (Machine.config)。  
  
## <a name="example"></a>範例  
 下列範例會使用來自 Internet Explorer proxy 的預設值，指定 proxy 位址，並略過本機存取的 proxy。  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [網路設定結構描述](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
