---
title: "RangeEnumeration 活動"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0327ca08764f35550be47c4efa111b00d16b0b5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="rangeenumeration-activity"></a>RangeEnumeration 活動
這個範例會示範如何建立自訂活動，此活動會逐一查看數字集合。下表詳述此範例中所包含的主要檔案。  
  
|檔案名稱|描述|  
|---------------|-----------------|  
|RangeEnumeration.cs|定義名為 `RangeEnumeration` 的自訂活動，此活動會覆寫 <xref:System.Activities.NativeActivity> 類別，並針對一連串的數字執行迴圈。|  
|RangeEnumerationSample.cs|使用 `RangeEnumeration` 活動的用戶端應用程式，可逐一查看數字集合。|  
  
 下表詳述 `RangeEnumeration` 活動的屬性。  
  
|屬性|描述|  
|--------------|-----------------|  
|啟動|開始迴圈的整數。|  
|停止|停止迴圈的整數。|  
|步驟|指定每次要反覆查看的數量。|  
|本文|指定每一次反覆查看時所要執行的程式碼。|  
  
#### <a name="to-use-this-sample"></a>若要使用這個範例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 開啟 RangeEnumeration.sln 方案檔。  
  
2.  若要建置此方案，請按 CTRL+SHIFT+B。  
  
3.  若要執行此方案，請按下 CTRL+F5。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4  (適用於 .NET Framework 4 的 Windows Communication Foundation (WCF) 與 Windows Workflow Foundation (WF) 範例)](http://go.microsoft.com/fwlink/?LinkId=150780) ，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。 此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`