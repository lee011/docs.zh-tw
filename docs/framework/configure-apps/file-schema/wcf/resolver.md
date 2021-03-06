---
title: "&lt;解析程式&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a9b63848590fba6e07a4a32d8ffd70c277448adf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="ltresolvergt"></a>&lt;解析程式&gt;
指定對等解析程式，用於將對等網狀結構 ID 解析成一組對等節點位址，這組位址可表示參與網狀結構的數個節點。  
  
 \<系統。ServiceModel >  
\<繫結 >  
\<netPeerBinding >  
\<繫結 >  
\<解析程式 >  
  
## <a name="syntax"></a>語法  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|`mode`|字串，指定與此服務相關聯的對等解析程式執行個體是 PNRP 專用、自訂解析程式或自動判定。 此屬性的型別為 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>。|  
|`referralPolicy`|字串，指定在對等之間共用轉介的方法。 此屬性的型別為 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>。|  
  
### <a name="child-elements"></a>子元素  
  
|項目|說明|  
|-------------|-----------------|  
|[\<標頭 >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|指定自訂對等解析程式服務的設定。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|說明|  
|-------------|-----------------|  
|[\<繫結 >](../../../../../docs/framework/misc/binding.md)|定義的所有繫結功能[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。|  
  
## <a name="remarks"></a>備註  
 對等名稱解析程式是對等通道用來尋找參與對等網狀結構之對等節點的探索服務。 您也可以使用這個解析程式將節點「註冊」到對等網狀結構，透過這樣的機制使得對等節點成為已知的，並且可從對等網狀結構中取得。 如需有關對等解析程式的詳細資訊，請參閱[對等解析程式](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [對等解析程式](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [PeerChannel 應用程式中加入自訂解析程式](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
