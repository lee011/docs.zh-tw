---
title: "追蹤事件參考"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1c1ee87-f80a-449b-acd0-50d81eef116e
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9eaf7f8bd4d477b08cda16ca544f240a417f6b21
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="tracking-events-reference"></a>追蹤事件參考
在 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 中執行工作流程期間，會引發追蹤事件，因為工作流程會通過生命週期的各種階段。 主機可訂閱這些事件，並保持工作流程在其生命週期時的進度狀態更新。 本節中將討論引發的追蹤事件。  
  
## <a name="event-reference"></a>事件參考  
  
|事件 ID|事件層級|事件訊息|關鍵字|  
|--------------|-----------------|-------------------|--------------|  
|[100 - WorkflowInstanceRecord](../../../docs/framework/windows-workflow-foundation/100-workflowinstancerecord.md)|資訊|TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[101 - WorkflowInstanceUnhandledExceptionRecord](../../../docs/framework/windows-workflow-foundation/101-workflowinstanceunhandledexceptionrecord.md)|錯誤|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9, Annotations= %10, ProfileName = %11|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[102 - WorkflowInstanceAbortedRecord](../../../docs/framework/windows-workflow-foundation/102-workflowinstanceabortedrecord.md)|警告|TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[103 - ActivityStateRecord](../../../docs/framework/windows-workflow-foundation/103-activitystaterecord.md)|資訊|TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[104 - ActivityScheduledRecord](../../../docs/framework/windows-workflow-foundation/104-activityscheduledrecord.md)|資訊|TrackRecord = ActivityScheduledRecord、InstanceID = %1、RecordNumber = %2、EventTime = %3、Name = %4、ActivityId = %5、ActivityInstanceId = %6、ActivityTypeName = %7、ChildActivityName = %8、ChildActivityId = %9、ChildActivityInstanceId = %10、ChildActivityTypeName =%11、Annotations=%12、ProfileName = %13|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[105 - FaultPropagationRecord](../../../docs/framework/windows-workflow-foundation/105-faultpropagationrecord.md)|警告|TrackRecord = FaultPropagationRecord、InstanceID=%1、RecordNumber=%2、EventTime=%3、FaultSourceActivityName=%4、FaultSourceActivityId=%5、FaultSourceActivityInstanceId=%6、FaultSourceActivityTypeName=%7、FaultHandlerActivityName=%8、FaultHandlerActivityId = %9、FaultHandlerActivityInstanceId =%10、FaultHandlerActivityTypeName=%11、Fault=%12、IsFaultSource=%13、Annotations=%14、ProfileName = %15|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[106 - CancelRequestRecord](../../../docs/framework/windows-workflow-foundation/106-cancelrequestrecord.md)|資訊|TrackRecord = CancelRequestedRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityId=%5, ActivityInstanceId=%6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[107 -- BookmarkResumptionRecord](../../../docs/framework/windows-workflow-foundation/107-bookmarkresumptionrecord.md)|資訊|TrackRecord = BookmarkResumptionRecord、InstanceID=%1、RecordNumber=%2,EventTime=%3、Name=%4、SubInstanceID=%5、OwnerActivityName=%6、OwnerActivityId =%7、OwnerActivityInstanceId=%8、OwnerActivityTypeName=%9、Annotations=%10、ProfileName = %11|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[108 - CustomTrackingRecordInfo](../../../docs/framework/windows-workflow-foundation/108-customtrackingrecordinfo.md)|資訊|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents、EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[110 - CustomTrackingRecordWarning](../../../docs/framework/windows-workflow-foundation/110-customtrackingrecordwarning.md)|警告|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents、EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[111 - CustomTrackingRecordError](../../../docs/framework/windows-workflow-foundation/111-customtrackingrecorderror.md)|錯誤|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents、EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[112 - WorkflowInstanceSuspendedRecord](../../../docs/framework/windows-workflow-foundation/112-workflowinstancesuspendedrecord.md)|資訊|TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[113 - WorkflowInstanceTerminatedRecord](../../../docs/framework/windows-workflow-foundation/113-workflowinstanceterminatedrecord.md)|錯誤|TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|[114 - WorkflowInstanceRecordWithId](../../../docs/framework/windows-workflow-foundation/114-workflowinstancerecordwithid.md)|資訊|TrackRecord= WorkflowInstanceRecord、InstanceID = %1、RecordNumber = %2、EventTime = %3、ActivityDefinitionId = %4、State = %5、Annotations = %6、ProfileName = %7、WorkflowDefinitionIdentity = %8|HealthMonitoring、WFTracking|  
|[115 - WorkflowInstanceAbortedRecordWithId](../../../docs/framework/windows-workflow-foundation/115-workflowinstanceabortedrecordwithid.md)|警告|TrackRecord = WorkflowInstanceAbortedRecord、 InstanceID = %1、 RecordNumber = %2、 EventTime = %3、 ActivityDefinitionId = %4、 Reason = %5、 Annotations = %6、 ProfileName = %7、 WorkflowDefinitionIdentity = %8|HealthMonitoring、WFTracking|  
|[116 - WorkflowInstanceSuspendedRecordWithId](../../../docs/framework/windows-workflow-foundation/116-workflowinstancesuspendedrecordwithid.md)|資訊|TrackRecord = WorkflowInstanceSuspendedRecord、InstanceID = %1、RecordNumber = %2、EventTime = %3、ActivityDefinitionId = %4、Reason = %5、Annotations = %6、ProfileName = %7、WorkflowDefinitionIdentity = %8|HealthMonitoring、WFTracking|  
|[117 - WorkflowInstanceTerminatedRecordWithId](../../../docs/framework/windows-workflow-foundation/117-workflowinstanceterminatedrecordwithid.md)|錯誤|TrackRecord = WorkflowInstanceTerminatedRecord、 InstanceID = %1、 RecordNumber = %2、 EventTime = %3、 ActivityDefinitionId = %4、 Reason = %5、 Annotations = %6、 ProfileName = %7、 WorkflowDefinitionIdentity = %8|HealthMonitoring、WFTracking|  
|[118 - WorkflowInstanceUnhandledExceptionRecordWithId](../../../docs/framework/windows-workflow-foundation/118-workflowinstanceunhandledexceptionrecordwithid.md)|錯誤|TrackRecord = WorkflowInstanceUnhandledExceptionRecord、 InstanceID = %1、 RecordNumber = %2、 EventTime = %3、 ActivityDefinitionId = %4、 SourceName = %5、 SourceId = %6、 SourceInstanceId = %7、 SourceTypeName = %8、 Exception = %9、 Annotations = %10、 ProfileName =%11、 WorkflowDefinitionIdentity = %12|HealthMonitoring、WFTrackingHealthMonitoring、WFTracking|  
|[119 - WorkflowInstanceUpdatedRecord](../../../docs/framework/windows-workflow-foundation/119-workflowinstanceupdatedrecord.md)|資訊|TrackRecord= WorkflowInstanceUpdatedRecord、InstanceID = %1、RecordNumber = %2、EventTime = %3、ActivityDefinitionId = %4、State = %5、OriginalDefinitionIdentity = %6、UpdatedDefinitionIdentity = %7、Annotations = %8、ProfileName = %9|HealthMonitoring、WFTracking|  
|[225 - TraceCorrelationKeys](../../../docs/framework/windows-workflow-foundation/225-tracecorrelationkeys.md)|資訊|在父範圍 '%3' 中使用 '%2' 值計算的相互關聯索引鍵 '%1'。|疑難排解 WFServices|  
|[440 - StartSignpostEvent1](../../../docs/framework/windows-workflow-foundation/440-startsignpostevent.md)|資訊|活動界限。|疑難排解 WFServices|  
|[441- StopSignpostEvent1](../../../docs/framework/windows-workflow-foundation/441-stopsignpostevent.md)|資訊|活動界限。|疑難排解 WFServices|  
|[1001 - WorkflowApplicationCompleted](../../../docs/framework/windows-workflow-foundation/1001-workflowapplicationcompleted.md)|資訊|WorkflowInstance Id：'%1' 已在 Closed 狀態中完成。|WFRuntime|  
|[1002 - WorkflowApplicationTerminated](../../../docs/framework/windows-workflow-foundation/1002-workflowapplicationterminated.md)|資訊|WorkflowApplication Id：'%1' 已終止。 它已經以 Faulted 狀態完成，並發生例外狀況。|WFRuntime|  
|[1003 - WorkflowInstanceCanceled](../../../docs/framework/windows-workflow-foundation/1003-workflowinstancecanceled.md)|資訊|WorkflowInstance Id：'%1' 已在 Canceled 狀態中完成。|WFRuntime|  
|[1004 - WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation/1004-workflowinstanceaborted.md)|資訊|WorkflowInstance Id：'%1' 已中止，並發生例外狀況。|WFRuntime|  
|[1005 - WorkflowApplicationIdled](../../../docs/framework/windows-workflow-foundation/1005-workflowapplicationidled.md)|資訊|WorkflowApplication Id：'%1' 閒置。|WFRuntime|  
|[1006 - WorkflowApplicationUnhandledException](../../../docs/framework/windows-workflow-foundation/1006-workflowapplicationunhandledexception.md)|錯誤|WorkflowInstance Id: '%1' 發生未處理例外狀況。  例外狀況源自活動 '%2'、 DisplayName: '%3'。  將會採取下列動作: %4。|WFRuntime|  
|[1007 - WorkflowApplicationPersisted](../../../docs/framework/windows-workflow-foundation/1007-workflowapplicationpersisted.md)|資訊|WorkflowApplication Id：'%1' 是永續性的。|WFRuntime|  
|[1008 - WorkflowApplicationUnloaded](../../../docs/framework/windows-workflow-foundation/1008-workflowapplicationunloaded.md)|資訊|WorkflowInstance Id：'%1' 已卸載。|WFRuntime|  
|[1009 - ActivityScheduled](../../../docs/framework/windows-workflow-foundation/1009-activityscheduled.md)|資訊|父活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 已排程子活動 '%4'、DisplayName：'%5'、InstanceId：'%6'。|WFRuntime|  
|[1010 - ActivityCompleted](../../../docs/framework/windows-workflow-foundation/1010-activitycompleted.md)|資訊|父活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 已排程子活動 '%4'、DisplayName：'%5'、InstanceId：'%6'。|WFRuntime|  
|[1011 - ScheduleExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1011-scheduleexecuteactivityworkitem.md)|詳細資訊|已經為活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 排程 ExecuteActivityWorkItem。|WFRuntime|  
|[1012 - StartExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1012-startexecuteactivityworkitem.md)|詳細資訊|開始執行活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 ExecuteActivityWorkItem。|WFRuntime|  
|[1013 - CompleteExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1013-completeexecuteactivityworkitem.md)|詳細資訊|已完成活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 ExecuteActivityWorkItem。|WFRuntime|  
|[1014 - ScheduleCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1014-schedulecompletionworkitem.md)|詳細資訊|已排定 CompletionWorkItem 父活動 '%1'、 DisplayName: '%2'、 InstanceId: '%3'。  已完成活動 '%4'、DisplayName：'%5'、InstanceId：'%6'。|WFRuntime|  
|[1015 - StartCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1015-startcompletionworkitem.md)|詳細資訊|開始執行活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 CompletionWorkItem。 已完成活動 '%4'、DisplayName：'%5'、InstanceId：'%6'。|WFRuntime|  
|[1016 - CompleteCompletionWorkItem](../../../docs/framework/windows-workflow-foundation/1016-completecompletionworkitem.md)|詳細資訊|已完成父活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 CompletionWorkItem。 已完成活動 '%4'、DisplayName：'%5'、InstanceId：'%6'。|WFRuntime|  
|[1017 - ScheduleCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1017-schedulecancelactivityworkitem.md)|詳細資訊|已排定活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 CancelActivityWorkItem。|WFRuntime|  
|[1018 - StartCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1018-startcancelactivityworkitem.md)|詳細資訊|開始執行活動 '%1'、DisplayName：'%2'、InstanceId：'%3'的 CancelActivityWorkItem。|WFRuntime|  
|[1019 - CompleteCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation/1019-completecancelactivityworkitem.md)|詳細資訊|已完成活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 CancelActivityWorkItem。|WFRuntime|  
|[1020 - CreateBookmark](../../../docs/framework/windows-workflow-foundation/1020-createbookmark.md)|詳細資訊|已建立書籤的活動 '%1'、 DisplayName: '%2'、 InstanceId: '%3'。  BookmarkName：%4、BookmarkScope：%5。|WFRuntime|  
|[1021 - ScheduleBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1021-schedulebookmarkworkitem.md)|詳細資訊|BookmarkWorkItem 已排定活動 '%1'、 DisplayName: '%2'、 InstanceId: '%3'。  BookmarkName：%4、BookmarkScope：%5。|WFRuntime|  
|[1022 - StartBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1022-startbookmarkworkitem.md)|詳細資訊|開始執行的 bookmarkworkitem 活動 '%1'、 DisplayName: '%2'、 InstanceId: '%3'。  BookmarkName：%4、BookmarkScope：%5。|WFRuntime|  
|[1023 - CompleteBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation/1023-completebookmarkworkitem.md)|詳細資訊|已完成活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 BookmarkWorkItem。 BookmarkName：%4、BookmarkScope：%5。|WFRuntime|  
|[1024 - CreateBookmarkScope](../../../docs/framework/windows-workflow-foundation/1024-createbookmarkscope.md)|詳細資訊|已建立 BookmarkScope：%1。|WFRuntime|  
|[1025 - BookmarkScopeInitialized](../../../docs/framework/windows-workflow-foundation/1025-bookmarkscopeinitialized.md)|詳細資訊|已用 ID：'%2' 初始化具有 TemporaryId：'%1' 的 BookmarkScope。|WFRuntime|  
|[1026 - ScheduleTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1026-scheduletransactioncontextworkitem.md)|詳細資訊|已排定活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 TransactionContextWorkItem。|WFRuntime|  
|[1027 - StartTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1027-starttransactioncontextworkitem.md)|詳細資訊|開始執行活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 TransactionContextWorkItem。|WFRuntime|  
|[1028 - CompleteTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation/1028-completetransactioncontextworkitem.md)|詳細資訊|已完成活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 TransactionContextWorkItem。|WFRuntime|  
|[1029 - ScheduleFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1029-schedulefaultworkitem.md)|詳細資訊|FaultWorkItem 已排定活動 '%1'、 DisplayName: '%2'、 InstanceId: '%3'。  活動 '%4'、DisplayName：'%5'、InstanceId：'%6' 傳回例外狀況。|WFRuntime|  
|[1030 - StartFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1030-startfaultworkitem.md)|詳細資訊|開始執行的 faultworkitem 活動 '%1'、 DisplayName: '%2'、 InstanceId: '%3'。  活動 '%4'、DisplayName：'%5'、InstanceId：'%6' 傳回例外狀況。|WFRuntime|  
|[1031 - CompleteFaultWorkItem](../../../docs/framework/windows-workflow-foundation/1031-completefaultworkitem.md)|詳細資訊|已完成活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的 FaultWorkItem。 活動 '%4'、DisplayName：'%5'、InstanceId：'%6' 傳回例外狀況。|WFRuntime|  
|[1032 - ScheduleRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1032-scheduleruntimeworkitem.md)|詳細資訊|已排定活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的執行階段工作項目。|WFRuntime|  
|[1033 - StartRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1033-startruntimeworkitem.md)|詳細資訊|開始執行活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的執行階段工作項目。|WFRuntime|  
|[1034 - CompleteRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation/1034-completeruntimeworkitem.md)|詳細資訊|已完成活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 的執行階段工作項目。|WFRuntime|  
|[1035 - RuntimeTransactionSet](../../../docs/framework/windows-workflow-foundation/1035-runtimetransactionset.md)|詳細資訊|執行階段交易已預先設定活動 '%1'、 DisplayName: '%2'、 InstanceId: '%3'。  執行已隔離到活動 '%4'、 DisplayName: '%5'、 InstanceId: '%6'。|WFRuntime|  
|[1036 - RuntimeTransactionCompletionRequested](../../../docs/framework/windows-workflow-foundation/1036-runtimetransactioncompletionrequested.md)|詳細資訊|活動 '%1'、DisplayName：'%2'、InstanceId：'%3' 已排程完成執行階段交易。|WFRuntime|  
|[1037 - RuntimeTransactionComplete](../../../docs/framework/windows-workflow-foundation/1037-runtimetransactioncomplete.md)|詳細資訊|執行階段交易已完成，狀態為 '%1'。|WFRuntime|  
|[1038 - EnterNoPersistBlock](../../../docs/framework/windows-workflow-foundation/1038-enternopersistblock.md)|詳細資訊|正在進入無持續性區塊。|WFRuntime|  
|[1039 - ExitNoPersistBlock](../../../docs/framework/windows-workflow-foundation/1039-exitnopersistblock.md)|詳細資訊|正在結束無持續性區塊。|WFRuntime|  
|[1040 - InArgumentBound](../../../docs/framework/windows-workflow-foundation/1040-inargumentbound.md)|詳細資訊|活動 '%2'、DisplayName：'%3'、InstanceId：'%4' 中的引數 '%1' 已與值 %5 繫結。|WFActivities|  
|[1041 - WorkflowApplicationPersistableIdle](../../../docs/framework/windows-workflow-foundation/1041-workflowapplicationpersistableidle.md)|資訊|WorkflowApplication Id: '%1' 處於閒置狀態且可保存。  將會採取下列動作: %2。|WFRuntime|  
|[1101 - WorkflowActivityStart](../../../docs/framework/windows-workflow-foundation/1101-workflowactivitystart.md)|資訊|WorkflowInstance Id：'%1' E2E 活動|WFRuntime|  
|[1102 - WorkflowActivityStop](../../../docs/framework/windows-workflow-foundation/1102-workflowactivitystop.md)|資訊|WorkflowInstance Id：'%1' E2E 活動|WFRuntime|  
|[1103 - WorkflowActivitySuspend](../../../docs/framework/windows-workflow-foundation/1103-workflowactivitysuspend.md)|資訊|WorkflowInstance Id：'%1' E2E 活動|WFRuntime|  
|[1104 - WorkflowActivityResume](../../../docs/framework/windows-workflow-foundation/1104-workflowactivityresume.md)|資訊|WorkflowInstance Id：'%1' E2E 活動|WFRuntime|  
|[1124 - InvokeMethodIsStatic](../../../docs/framework/windows-workflow-foundation/1124-invokemethodisstatic.md)|資訊|InvokeMethod '%1' - 方法是靜態方法。|WFRuntime|  
|[1125 - InvokeMethodIsNotStatic](../../../docs/framework/windows-workflow-foundation/1125-invokemethodisnotstatic.md)|資訊|InvokeMethod '%1' - 方法不是靜態方法。|WFRuntime|  
|[1126 - InvokedMethodThrewException](../../../docs/framework/windows-workflow-foundation/1126-invokedmethodthrewexception.md)|資訊|在活動 '%1' 呼叫的方法中發生例外狀況。 %2|WFRuntime|  
|[1131 - InvokeMethodUseAsyncPattern](../../../docs/framework/windows-workflow-foundation/1131-invokemethoduseasyncpattern.md)|資訊|InvokeMethod '%1' - 方法使用 '%2' 和 '%3' 非同步模式。|WFRuntime|  
|[1132 - InvokeMethodDoesNotUseAsyncPattern](../../../docs/framework/windows-workflow-foundation/1132-invokemethoddoesnotuseasyncpattern.md)|資訊|InvokeMethod '%1' - 方法未使用非同步模式。|WFRuntime|  
|[1140 - FlowchartStart](../../../docs/framework/windows-workflow-foundation/1140-flowchartstart.md)|資訊|流程圖 '%1' - 已排程 Start。|WFActivities|  
|[1141 - FlowchartEmpty](../../../docs/framework/windows-workflow-foundation/1141-flowchartempty.md)|警告|Flowchart '%1' - 已在沒有節點的情況下執行。活動 '1%' 呼叫的方法擲回例外狀況。 %2|WFActivities|  
|[1143 - FlowchartNextNull](../../../docs/framework/windows-workflow-foundation/1143-flowchartnextnull.md)|資訊|流程圖 '%1'/FlowStep - 下一個節點是 null。 流程圖執行將結束。|WFActivities|  
|[1146 - FlowchartSwitchCase](../../../docs/framework/windows-workflow-foundation/1146-flowchartswitchcase.md)|資訊|流程圖 '%1'/FlowSwitch - 已選取案例 '%2'。|WFActivities|  
|[1147 - FlowchartSwitchDefault](../../../docs/framework/windows-workflow-foundation/1147-flowchartswitchdefault.md)|資訊|流程圖 '%1'/FlowSwitch - 已選取預設案例。|WFActivities|  
|[1148 - FlowchartSwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation/1148-flowchartswitchcasenotfound.md)|資訊|流程圖 '%1'/FlowSwitch - 找不到符合運算式結果的案例活動或預設案例。 流程圖執行將結束。|WFActivities|  
|[1150 - CompensationState](../../../docs/framework/windows-workflow-foundation/1150-compensationstate.md)|資訊|CompensableActivity '%1' 處於 '%2' 狀態。|WFActivities|  
|[1223 - SwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation/1223-switchcasenotfound.md)|資訊|Switch 活動 '%1' 找不到符合運算式結果的 Case 活動。|WFActivities|  
|[1449 - WfMessageReceived](../../../docs/framework/windows-workflow-foundation/1449-wfmessagereceived.md)|資訊|工作流程所接收的訊息|WFServices|  
|[1450 - WfMessageSent](../../../docs/framework/windows-workflow-foundation/1450-wfmessagesent.md)|資訊|從工作流程傳送的訊息|WFServices|  
|[2021 - ExecuteWorkItemStart](../../../docs/framework/windows-workflow-foundation/2021-executeworkitemstart.md)|詳細資訊|執行工作項目開始|WFRuntime|  
|[2022 - ExecuteWorkItemStop](../../../docs/framework/windows-workflow-foundation/2022-executeworkitemstop.md)|詳細資訊|執行工作項目停止|WFRuntime|  
|[2023 - SendMessageChannelCacheMiss](../../../docs/framework/windows-workflow-foundation/2023-sendmessagechannelcachemiss.md)|詳細資訊|SendMessageChannelCache 遺漏|WFRuntime|  
|[2024 - InternalCacheMetadataStart](../../../docs/framework/windows-workflow-foundation/2024-internalcachemetadatastart.md)|詳細資訊|活動 '%1' 上的 InternalCacheMetadata 已啟動。|WFRuntime|  
|[2025 - InternalCacheMetadataStop](../../../docs/framework/windows-workflow-foundation/2025-internalcachemetadatastop.md)|詳細資訊|活動 '%1' 上的 InternalCacheMetadata 已停止。|WFRuntime|  
|[2026 - CompileVbExpressionStart](../../../docs/framework/windows-workflow-foundation/2026-compilevbexpressionstart.md)|詳細資訊|編譯 VB 運算式 '%1'|WFRuntime|  
|[2027 - CacheRootMetadataStart](../../../docs/framework/windows-workflow-foundation/2027-cacherootmetadatastart.md)|詳細資訊|活動 '%1' 上的 CacheRootMetadata 已啟動|WFRuntime|  
|[2028 - CacheRootMetadataStop](../../../docs/framework/windows-workflow-foundation/2028-cacherootmetadatastop.md)|詳細資訊|活動 %1 上的 CacheRootMetadata 已停止。|WFRuntime|  
|[2029 - CompileVbExpressionStop](../../../docs/framework/windows-workflow-foundation/2029-compilevbexpressionstop.md)|詳細資訊|完成編譯 VB 運算式。|WFRuntime|  
|[2576 - TryCatchExceptionFromTry](../../../docs/framework/windows-workflow-foundation/2576-trycatchexceptionfromtry.md)|資訊|TryCatch 活動 '%1' 攔截到型別 '%2' 的例外狀況。|WFActivities|  
|[2577 - TryCatchExceptionDuringCancelation](../../../docs/framework/windows-workflow-foundation/2577-trycatchexceptionduringcancelation.md)|警告|TryCatch 活動 '%1' 的子活動在取消期間擲回例外狀況。|WFActivities|  
|[2578 - TryCatchExceptionFromCatchOrFinally](../../../docs/framework/windows-workflow-foundation/2578-trycatchexceptionfromcatchorfinally.md)|警告|與 TryCatch 活動 '%1' 關聯的 Catch 或 Finally 活動擲回例外狀況。|WFActivities|  
|[3501 - InferredContractDescription](../../../docs/framework/windows-workflow-foundation/3501-inferredcontractdescription.md)|資訊|已從 WorkflowService 推斷出 Name='%1' 且 Namespace='%2' 的 ContractDescription。|WFServices|  
|[3502 - InferredOperationDescription](../../../docs/framework/windows-workflow-foundation/3502-inferredoperationdescription.md)|資訊|已從 WorkflowService 推斷出合約 '%2' 中 Name='%1' 的 OperationDescription。 IsOneWay=%3。|WFServices|  
|[3503 - DuplicateCorrelationQuery](../../../docs/framework/windows-workflow-foundation/3503-duplicatecorrelationquery.md)|警告|發現 Where='%1' 的重複 CorrelationQuery。 計算相互關聯時不會使用這個重複的查詢。|WFServices|  
|[3507 - ServiceEndpointAdded](../../../docs/framework/windows-workflow-foundation/3507-serviceendpointadded.md)|資訊|已經針對位址 '%1'、繫結 '%2' 和合約 '%3' 加入服務端點。|WFServices|  
|[3508 - TrackingProfileNotFound](../../../docs/framework/windows-workflow-foundation/3508-trackingprofilenotfound.md)|詳細資訊|找不到 ActivityDefinitionId '%2' 的 TrackingProfile '%1'。 在組態檔中找不到 TrackingProfile，或者 ActivityDefinitionId 不相符。|WFServices|  
|[3550 - BufferOutOfOrderMessageNoInstance](../../../docs/framework/windows-workflow-foundation/3550-bufferoutofordermessagenoinstance.md)|資訊|目前無法執行作業 '%1'。 將在服務執行個體準備就緒可以處理這個特定作業時，再次嘗試。|WFServices|  
|[3551 - BufferOutOfOrderMessageNoBookmark](../../../docs/framework/windows-workflow-foundation/3551-bufferoutofordermessagenobookmark.md)|資訊|目前無法在服務執行個體 '%1' 上執行作業 '%2'。 將在服務執行個體準備就緒可以處理這個特定作業時，再次嘗試。|WFServices|  
|[3552 - MaxPendingMessagesPerChannelExceeded](../../../docs/framework/windows-workflow-foundation/3552-maxpendingmessagesperchannelexceeded.md)|警告|已達到節流 'MaxPendingMessagesPerChannel' 限制為 '%1'。 若要增加此限制，請調整 BufferedReceiveServiceBehavior 上的 MaxPendingMessagesPerChannel 屬性。|配額 WFServices|  
|[3557 - TransactedReceiveScopeEndCommitFailed](../../../docs/framework/windows-workflow-foundation/3557-transactedreceivescopeendcommitfailed.md)|資訊|呼叫 ID = '%1' 之 CommittableTransaction 上的 EndCommit 擲回 TransactionException，並出現下列訊息：'%2'。|WFServices|  
|[4201 - EndSqlCommandExecute](../../../docs/framework/windows-workflow-foundation/4201-endsqlcommandexecute.md)|詳細資訊|結束 SQL 命令執行：%1|WFInstanceStore|  
|[4202 - StartSqlCommandExecute](../../../docs/framework/windows-workflow-foundation/4202-startsqlcommandexecute.md)|詳細資訊|開始 SQL 命令執行：%1|WFInstanceStore|  
|[4203 - RenewLockSystemError](../../../docs/framework/windows-workflow-foundation/4203-renewlocksystemerror.md)|錯誤|無法延長鎖定期限，已超過鎖定期限或已刪除鎖定擁有人。 正在中止 SqlWorkflowInstanceStore。|WFInstanceStore|  
|[4205 - FoundProcessingError](../../../docs/framework/windows-workflow-foundation/4205-foundprocessingerror.md)|錯誤|命令失敗：%1|WFInstanceStore|  
|[4206 - UnlockInstanceException](../../../docs/framework/windows-workflow-foundation/4206-unlockinstanceexception.md)|錯誤|嘗試解除鎖定執行個體時，發生例外狀況 %1。|WFInstanceStore|  
|[4207 - MaximumRetriesExceededForSqlCommand](../../../docs/framework/windows-workflow-foundation/4207-maximumretriesexceededforsqlcommand.md)|資訊|放棄重試 SQL 命令，因為已經執行了重試次數上限。|Quota WFInstanceStore|  
|[4208 - RetryingSqlCommandDueToSqlError](../../../docs/framework/windows-workflow-foundation/4208-retryingsqlcommandduetosqlerror.md)|資訊|重試 SQL 命令，因為出現 SQL 錯誤代碼 %1。|WFInstanceStore|  
|[4209 - TimeoutOpeningSqlConnection](../../../docs/framework/windows-workflow-foundation/4209-timeoutopeningsqlconnection.md)|錯誤|嘗試開啟 SQL 連接時發生逾時。 無法在分配的逾時 %1 內完成作業。 分配給此作業的時間可能是較長逾時的一部分。|WFInstanceStore|  
|[4210 - SqlExceptionCaught](../../../docs/framework/windows-workflow-foundation/4210-sqlexceptioncaught.md)|警告|攔截到 SQL 例外狀況編號 %1 訊息 %2。|WFInstanceStore|  
|[4211 - QueuingSqlRetry](../../../docs/framework/windows-workflow-foundation/4211-queuingsqlretry.md)|警告|佇列 SQL 重試，但延遲 %1 毫秒。|WFInstanceStore|  
|[4212 - LockRetryTimeout](../../../docs/framework/windows-workflow-foundation/4212-lockretrytimeout.md)|警告|嘗試取得執行個體鎖定時發生逾時。  無法在分配的逾時 %1 內完成作業。 分配給此作業的時間可能是較長逾時的一部分。|WFInstanceStore|  
|[4213 - RunnableInstancesDetectionError](../../../docs/framework/windows-workflow-foundation/4213-runnableinstancesdetectionerror.md)|錯誤|偵測可執行的執行個體失敗，因為發生下列例外狀況|WFInstanceStore|  
|[4214 - InstanceLocksRecoveryError](../../../docs/framework/windows-workflow-foundation/4214-instancelocksrecoveryerror.md)|錯誤|復原執行個體鎖定失敗，因為發生下列例外狀況|WFInstanceStore|  
|[39456 - TrackingRecordDropped](../../../docs/framework/windows-workflow-foundation/39456-trackingrecorddropped.md)|警告|追蹤記錄 %1 的大小已超出提供者 %2 的 ETW 工作階段所允許的最大值|WFTracking|  
|[39457 - TrackingRecordRaised](../../../docs/framework/windows-workflow-foundation/39457-trackingrecordraised.md)|資訊|追蹤記錄 %1 提升至 %2。|WFRuntime|  
|[39458 - TrackingRecordTruncated](../../../docs/framework/windows-workflow-foundation/39458-trackingrecordtruncated.md)|警告|已將截斷的追蹤記錄 %1 寫入提供者 %2 的 ETW 工作階段。 變數/附註/使用者資料已移除|WFTracking|  
|[39459 - TrackingDataExtracted](../../../docs/framework/windows-workflow-foundation/39459-trackingdataextracted.md)|詳細資訊|追蹤在活動 %2 中擷取到的資料 %1。|WFRuntime|  
|[39460 - TrackingValueNotSerializable](../../../docs/framework/windows-workflow-foundation/39460-trackingvaluenotserializable.md)|警告|擷取的引數/變數 '%1' 不可序列化。|WFTracking|  
|[57398 - MaxInstancesExceeded](../../../docs/framework/windows-workflow-foundation/57398-maxinstancesexceeded.md)|警告|系統已到達針對 'MaxConcurrentInstances' 節流所設定的限制。 此節流的限制設為 %1。 若要變更節流值，請修改 serviceThrottle 元素中的屬性 'maxConcurrentInstances'，或修改行為 ServiceThrottlingBehavior 的 'MaxConcurrentInstances' 屬性。|WFServices|
