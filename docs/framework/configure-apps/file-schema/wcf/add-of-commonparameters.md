---
title: "&lt;commonParameters&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ff136c5d1b21b3cbc4e4f675a2ae49eddf05811
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a>&lt;commonParameters&gt; 的 &lt;add&gt;
指定跨多項服務全域使用之名稱/值組的參數。 這個參數通常會包含資料庫連線字串，這個字串可能會由長期服務所共用。  
  
 \<系統。ServiceModel >  
\<行為 >  
\<serviceBehaviors >  
\<行為 >  
\<workflowRuntime >  
\<一般參數 >  
\<add>  
  
## <a name="syntax"></a>語法  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|name|為服務指定的參數名稱。|  
|value|為服務指定的參數值。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|說明|  
|-------------|-----------------|  
|[\<一般參數 >](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|服務所使用的一般參數集合。 這個集合通常會包含資料庫連線字串，這個字串可能會由長期服務所共用。|  
  
## <a name="remarks"></a>備註  
 `<commonParameters>` 項目定義全球多種服務間使用的所有參數，例如在使用 `ConnectionString` 時的 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>。  
  
 針對認可工作批次持續儲存的服務 (例如 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 及 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)，您可以使用 `EnableRetries` 參數允許它們重試交易，如下列範例所示：  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 請注意，`EnableRetries`可以設定參數在全域層級 (如中所示*CommonParameters* > 一節) 或個別服務支援`EnableRetries`(中所示*服務*> 一節)。  
  
 如需有關使用組態檔來控制行為的<xref:System.Workflow.Runtime.WorkflowRuntime>物件的 Windows Workflow Foundation 主應用程式，請參閱[工作流程組態檔](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)。  
  
## <a name="example"></a>範例  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [工作流程組態檔](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [\<一般參數 >](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
