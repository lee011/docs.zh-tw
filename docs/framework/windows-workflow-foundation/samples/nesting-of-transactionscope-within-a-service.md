---
title: "巢狀處理服務中的 TransactionScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7455f2b45e47a6d72118055bd891f7c297b56483
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="nesting-of-transactionscope-within-a-service"></a>巢狀處理服務中的 TransactionScope
這個範例是由兩個執行的案例所組成，可示範如何在服務中處理 <xref:System.Activities.Statements.TransactionScope> 活動執行個體。 首先，交易是使用 <xref:System.Activities.Statements.TransactionScope> 活動 (可在用戶端建立新交易) 及 <xref:System.ServiceModel.Activities.TransactedReceiveScope> (可在伺服器上接收交易存留期及設定其範圍) 所起始。 服務內的第一個案例會執行次要 <xref:System.Activities.Statements.TransactionScope> 活動，以示範服務內 <xref:System.Activities.Statements.TransactionScope> 活動的巢狀結構。 第二個案例會示範如何在巢狀 <xref:System.Activities.Statements.TransactionScope> 活動內遵守逾時。  
  
## <a name="client-application"></a>用戶端應用程式  
 用戶端應用程式會執行一個工作流程，此工作流程會啟動 <xref:System.Activities.Statements.TransactionScope> 活動、列印分散式交易識別碼、傳送訊息給伺服器、讓交易流動、接收回應、再次列印分散式交易識別碼，然後完成。 它會針對每一個服務案例執行一次這項處理。  
  
## <a name="server-application"></a>伺服器應用程式  
 伺服器專案會在 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 中裝載，後者會建立用來接聽用戶端訊息的端點。 此工作流程會集中在 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，它會接收來自用戶端的流動交易、列印分散式交易識別碼，然後執行第二個 <xref:System.Activities.Statements.TransactionScope> 活動。 在第一個案例中，已順利完成交易。 在第二個案例中，<xref:System.Activities.Statements.TransactionScope> 活動的主體為五秒鐘延遲，而交易的逾時設為兩秒。 當交易逾時的時候，就會中止交易。  
  
#### <a name="to-run-the-sample"></a>若要執行範例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中開啟 TransactionServiceExample.sln 方案。  
  
2.  若要建置此方案，請按 CTRL + SHIFT + B 或選取**建置方案**從**建置**功能表。  
  
3.  已成功建置，以滑鼠右鍵按一下方案，並選取**設定啟始專案**。 從對話方塊中，選取**多個啟始專案**，並確定這兩個專案的動作是**啟動**。  
  
4.  按 F5 或選取**開始偵錯**從**偵錯**功能表。 或者，您可以按 CTRL + F5 或選取**啟動但不偵錯**從**偵錯**執行，而不偵錯 功能表。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4  (適用於 .NET Framework 4 的 Windows Communication Foundation (WCF) 與 Windows Workflow Foundation (WF) 範例)](http://go.microsoft.com/fwlink/?LinkId=150780) ，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。 此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TRSComposability`
