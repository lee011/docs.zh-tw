---
title: "&lt;peerTransport&gt; 的 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 69b62699f5db0ab11fac3cc4d1ba4e2aa022934d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltpeertransportgt"></a>&lt;peerTransport&gt; 的 &lt;transport&gt;
指定使用這個繫結設定之對等所傳送安全訊息的傳輸類型。  
  
 \<system.serviceModel >  
\<繫結 >  
\<customBinding >  
\<繫結 >  
\<p >  
\<安全性 >  
\<傳輸 >  
  
## <a name="syntax"></a>語法  
  
```xml  
<security>  
   <transport credentialType="Certificate/Password" />  
</security>         
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節說明屬性、子元素和父元素  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|credentialType|選擇項。 指定認證的類型，用於驗證對等傳輸所傳送的訊息。 此屬性的型別為 <xref:System.ServiceModel.PeerTransportCredentialType>。|  
  
## <a name="credentialtype-attribute"></a>credentialType 屬性  
  
|值|描述|  
|-----------|-----------------|  
|憑證|對等通道傳輸的驗證作業需要 X509 憑證。|  
|密碼|對等通道傳輸的驗證作業需要正確的密碼。|  
  
### <a name="child-elements"></a>子元素  
 無  
  
### <a name="parent-elements"></a>父項目  
  
|項目|說明|  
|-------------|-----------------|  
|[\<安全性 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|定義對等傳輸的安全性設定。|  
  
## <a name="remarks"></a>備註  
 只有當這個項目會設定目的 mode 屬性[\<安全性 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)設`Transport`或`TransportWithMessageCredential`。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [傳輸安全性](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [傳輸](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [選擇傳輸](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [繫結](../../../../../docs/framework/wcf/bindings.md)  
 [擴充繫結](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [自訂繫結](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
