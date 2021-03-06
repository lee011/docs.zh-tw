---
title: "HOW TO：為安全工作階段建立安全性內容權杖"
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
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 83e455c2377168c316bf34c25b687cde48b0fa3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a>HOW TO：為安全工作階段建立安全性內容權杖
在安全工作階段中使用具狀態的安全性內容權杖時，工作階段可以承受正在回收的服務。 例如，當安全工作階段使用沒有狀態的 SCT 而且重設了網際網路資訊服務 (IIS)，則與該服務相關聯的工作階段資料就會遺失。 這個工作階段資料包含 SCT 權杖快取。 因此，下一次當用戶端傳送的服務是沒有狀態的 SCT 時，便會傳回錯誤，因為無法擷取與 SCT 相關聯的金鑰。 但是，如果使用可設定狀態的 SCT，則與 SCT 相關聯的金鑰就會包含在 SCT 中。 由於金鑰是包含在 SCT (因此也包含在訊息中)，安全工作階段就不會受到正在回收的服務所影響。 根據預設，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 會在安全工作階段中使用沒有狀態的 SCT。 此主題將詳細說明如何在安全工作階段中使用可設定狀態的 SCT。  
  
> [!NOTE]
>  您無法在安全工作階段 (與衍生自 <xref:System.ServiceModel.Channels.IDuplexChannel> 的合約相關) 中使用可設定狀態的 SCT。  
  
> [!NOTE]
>  對於在安全工作階段中使用可設定狀態之 SCT 的應用程式來說，服務的執行緒識別必須是具有相關使用者設定檔的使用者帳戶。 如果服務透過不具備使用者設定檔的帳戶來執行，例如 `Local Service`，可能會擲回例外狀況。  
  
> [!NOTE]
>  當 Windows XP 需要模擬時，請使用不包含可設定狀態之 SCT 的安全工作階段。 當可設定狀態的 SCT 與模擬一起使用時，就會擲回 <xref:System.InvalidOperationException>。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][不支援的案例](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)。  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a>若要在安全工作階段中使用具狀態的 SCT  
  
-   建立自訂繫結，以指定 SOAP 訊息由使用具狀態之 SCT 的安全工作階段來保護。  
  
    1.  藉由加入定義自訂繫結， [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)至服務組態檔。  
  
        ```xml  
        <customBinding>  
        ```  
  
    2.  新增[\<繫結 >](../../../../docs/framework/misc/binding.md)的子項目[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)。  
  
         您可以在組態檔中將 `name` 屬性設為唯一的名稱來指定繫結名稱。  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  指定加上傳送與此服務之訊息的驗證模式[\<安全性 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)的子項目[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)。  
  
         您可以將 `authenticationMode` 屬性設為 `SecureConversation`，指定使用安全工作階段。 您可以將 `requireSecurityContextCancellation` 屬性設為 `false`，指定使用可設定狀態的 SCT。  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  指定加上建立安全工作階段時，如何驗證用戶端[ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)的子項目[\<安全性 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)。  
  
         您可以設定 `authenticationMode` 屬性，指定用戶端的驗證方式。  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  指定訊息的編碼方式將編碼的項目，例如[ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)。  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6.  指定的傳輸，藉由新增傳輸項目，例如[ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)。  
  
        ```xml  
        <httpTransport />  
        ```  
  
     下列程式碼範例使用組態來指定安全工作階段中，訊息可以搭配具狀態的 SCT 使用的自訂繫結。  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a>範例  
 下列程式碼範例建立了一個會使用 <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> 驗證模式來啟動載入安全工作階段的自訂繫結。  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 當 Windows 驗證與可設定狀態的 SCT 一起使用時，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不會使用實際呼叫者的身分識別來填入 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 屬性，而是將屬性設為匿名。 由於 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全性必須為每個來自傳入 SCT 的要求重新建立服務安全性內容 (context) 的內容 (content)，因此伺服器不會追蹤記憶體中的安全性工作階段。 由於您不可能將 <xref:System.Security.Principal.WindowsIdentity> 執行個體序列化為 SCT，<xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 屬性將傳回匿名身分識別。  
  
 下列組態將示範此行為。  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a>另請參閱  
 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
