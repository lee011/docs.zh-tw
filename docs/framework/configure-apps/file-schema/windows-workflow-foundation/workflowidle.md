---
title: '&lt;workflowIdle&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 66b2ff0db90a8126027eca976f73b3a8b554e3f4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
這個服務行為可控制卸載及保存閒置工作流程執行個體的時間。  
  
\<系統。ServiceModel >  
\<行為 >  
\<serviceBehaviors >  
\<行為 >  
\<workflowIdle >  
  
## <a name="syntax"></a>語法  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|timeToPersist|Timespan 值，指定工作流程進入閒置狀態與保存的時間之間的持續期間。 預設值是 TimeSpan.MaxValue。<br /><br /> 持續期間會開始在工作流程執行個體閒置時開始消逝。 這個屬性是很有用，如果您想要更積極地保存工作流程執行個體，同時仍保留在記憶體中，盡可能長期的執行個體。 這個屬性才有效，如果其值為小於**timeToUnload**屬性。 如果此屬性的值較大，則會忽略此屬性。 如果這個屬性就超過所指定的值之前**timeToUnload**屬性，持續性必須先完成工作流程已卸載。 也就是說，卸載作業可能會延遲到保存工作流程之後。 保存層負責處理重試暫時性錯誤，而且只會針對無法復原的錯誤擲回例外狀況。 因此，在保存期間擲回的所有例外狀況都會視為嚴重例外狀況，並且會中止工作流程執行個體。|  
|timeToUnload|Timespan 值，可指定在工作流程進入閒置狀態以及卸載之間的持續期間。 預設值為 1 分鐘。<br /><br /> 卸載工作流程表示會同時保存該工作流程。 如果這個屬性設為的零會保存工作流程執行個體，並將其卸載之後立即工作流程變成閒置狀態。 有效地將此屬性設定為 TimeSpan.MaxValue，就會停用卸載作業。 閒置的工作流程執行個體永遠不會卸載。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|說明|  
|-------------|-----------------|  
|[\<行為 > 的\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|指定行為項目。|  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
