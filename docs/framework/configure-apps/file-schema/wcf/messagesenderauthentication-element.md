---
title: "&lt;messageSenderAuthentication&gt; 項目"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5a280f9fe59ca5294276b98ec3632d6bc1a7ecba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagesenderauthenticationgt-element"></a>&lt;messageSenderAuthentication&gt; 項目
指定對等訊息寄件者的驗證選項。  
  
 如需端對端程式設計的詳細資訊，請參閱[對等網路](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。  
  
 \<系統。ServiceModel >  
\<行為 >  
\<endpointBehaviors >  
\<行為 >  
\<clientCredentials >  
\<對等 >  
\<messageSenderAuthentication >  
  
## <a name="syntax"></a>語法  
  
```xml  
<messageSenderAuthentication  
customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節說明屬性、子元素和父元素  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|customCertificateValidatorType|用來驗證自訂型別的型別和組件。 當 `certificateValidationMode` 設定為 `Custom` 時，必須設定這個屬性。|  
|certifcateValidationMode|指定用來驗證認證之三個模式的其中一個。 如果設定為 `Custom`，也必須提供 `customCertificateValidator`。|  
|revocationMode|用於檢查撤銷憑證清單 (CRL) 的模式之一。|  
|trustedStoreLocation|兩個系統存放位置的其中一個：`LocalMachine` 或 `CurrentUser`。 當與用戶端交涉服務憑證時，會使用這個值。 針對執行驗證**受信任的人**將儲存在指定的存放區位置。|  
  
## <a name="customcertificatevalidatortype-attribute"></a>customCertificateValidatorType 屬性  
  
|值|描述|  
|-----------|-----------------|  
|String|選擇項。 指定型別名稱和組件以及用來尋找此型別的其他資料。 至少需要命名空間和型別名稱。 選擇性的資訊包括：組件名稱、版本號碼、文化特性和公開金鑰權杖。|  
  
## <a name="certificatevalidationmode-attribute"></a>certificateValidationMode 屬性  
  
|值|描述|  
|-----------|-----------------|  
|列舉|選擇項。 下列其中一個值：`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom`。 預設為 `ChainTrust`。 預設為 `ChainTrust`。<br /><br /> 如需詳細資訊，請參閱[使用憑證](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。|  
  
## <a name="revocationmode-attribute"></a>revocationMode 屬性  
  
|值|描述|  
|-----------|-----------------|  
|列舉|下列其中一個值：`NoCheck`、`Online`、`Offline`。 預設為 `Online`。<br /><br /> 如需詳細資訊，請參閱[使用憑證](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation 屬性  
  
|值|描述|  
|-----------|-----------------|  
|列舉|下列其中一個值：`LocalMachine` 或 `CurrentUser`。 預設為 `CurrentUser`。 如果用戶端應用程式是在系統帳戶下執行，則憑證通常位於 `LocalMachine` 之下。 如果用戶端應用程式是在使用者帳戶下執行，則憑證通常位於 `CurrentUser`。 預設為 `CurrentUser`。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|說明|  
|-------------|-----------------|  
|[\<對等 >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|指定向對等服務驗證用戶端時所使用的認證。|  
  
## <a name="remarks"></a>備註  
 如果已選取訊息驗證，則必須設定這個項目。 輸出通道的每個訊息會使用簽章所提供的憑證[\<憑證 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。 所有訊息在傳遞至應用程式之前，都會使用這個項目的 `customCertificateValidatorType` 之屬性所指定的驗證程式來檢查訊息認證。 驗證器可接受或拒絕認證。  
  
## <a name="example"></a>範例  
 下列程式碼會將訊息寄件者驗證模式設定為 `PeerOrChainTrust`。  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
      <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
        <messageSenderAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
       <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [使用憑證](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [對等網路功能](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [對等通道訊息驗證](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [對等通道自訂驗證](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [保護對等通道應用程式](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
