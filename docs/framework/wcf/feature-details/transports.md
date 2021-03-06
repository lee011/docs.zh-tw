---
title: "Windows Communication Foundation 中的傳輸"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9275f1812111365ed6b0fb3be6957cd9ca883fdf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="transports-in-windows-communication-foundation"></a>Windows Communication Foundation 中的傳輸
傳輸層 (Transport Layer) 屬於通道堆疊中的最底層。 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中所使用的主要傳輸有 HTTP、HTTPS、TCP 和具名管道。 本節中的主題將討論如何在這些傳輸之間進行選擇、設定傳輸，以及設定調整屬性。  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 包含額外的傳輸。 如需訊息佇列 (也稱為 MSMQ) 傳輸的資訊，請參閱[佇列和可靠工作階段](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)。 如需端對端傳輸的資訊，請參閱[對等網路](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。  
  
## <a name="in-this-section"></a>本章節內容  
 [選擇傳輸](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 說明這三種主要傳輸，以及進行選擇時的考量因素。  
  
 [選擇訊息編碼器](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 說明選擇訊息編碼繫結項目時的考量因素。  
  
 [資料流訊息傳輸](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 說明如何設定傳輸層來傳送資料流。  
  
 [設定 HTTP 和 HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 說明如何設定 HTTP 和 HTTPS 傳輸繫結項目。  
  
 [如何： 以受限制的保留項目取代 WCF URL 保留項目](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 說明如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]URL 限制的保留區。  
  
 [傳輸配額](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 說明在設定傳輸層之可用配額時的考量因素。  
  
 [使用 Nat 與防火牆](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 說明當訊息是在防火牆後方進行傳送或接收、或是當網路位址轉譯 (NAT) 存在時的傳輸層設定方式。  
  
 [Net.TCP 連接埠共用](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 說明如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的 Net.TCP 連接埠共用服務元件。  
  
## <a name="reference"></a>參考資料  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>相關章節  
 [繫結](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [擴充繫結](../../../../docs/framework/wcf/extending/extending-bindings.md)
