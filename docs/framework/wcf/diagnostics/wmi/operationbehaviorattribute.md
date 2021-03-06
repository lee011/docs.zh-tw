---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da0bc2ac9a4283ec9b23a1d4767f664de071ef47
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>語法  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>方法  
 OperationBehaviorAttribute 類別並未定義任何方法。  
  
## <a name="properties"></a>屬性  
 OperationBehaviorAttribute 類別具有下列屬性：  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  
 資料型別：布林值  
  
 存取類型：唯讀  
  
 參數自動處置功能的狀態。  
  
### <a name="impersonation"></a>模擬  
 資料型別：字串  
  
 存取類型：唯讀  
  
 表示作業支援的呼叫端模擬等級。  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  
 資料型別：字串  
  
 存取類型：唯讀  
  
 表示在作業引動過程當中要回收物件的時機。  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 資料型別：布林值  
  
 存取類型：唯讀  
  
 表示未發生未處理的例外狀況時是否要自動認可目前的交易。  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 資料型別：布林值  
  
 存取類型：唯讀  
  
 表示作業是否需要交易。  
  
## <a name="requirements"></a>需求  
  
|MOF|於 Servicemodel.mof 中宣告。|  
|---------|-----------------------------------|  
|命名空間|於 root\ServiceModel 中定義|  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
