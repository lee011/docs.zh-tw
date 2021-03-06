---
title: "ICorDebugManagedCallback::LogSwitch 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LogSwitch
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9480b3123abceb6a108e2e00c7304829188cd162
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch 方法
告知偵錯工具中的通用語言執行平台 (CLR) managed 執行緒已呼叫方法<xref:System.Diagnostics.Switch>類別來建立、 修改或刪除偵錯/追蹤參數。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
#### <a name="parameters"></a>參數  
 `PAppDomain`  
 [in]表示包含建立、 修改或刪除偵錯/追蹤切換的 managed 的執行緒的應用程式網域的 ICorDebugAppDomain 物件指標。  
  
 `pThread`  
 [in]表示 managed 的執行緒的 ICorDebugThread 物件指標。  
  
 `lLevel`  
 [in]值，指出已寫入事件記錄檔的描述訊息的嚴重性層級。  
  
 `ulReason`  
 [in]值為[LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)切換偵錯/追蹤列舉，指出作業執行。  
  
 `pLogSwitchName`  
 [in]偵錯/追蹤參數的名稱指標。  
  
 `pParentName`  
 [in]偵錯/追蹤參數，因為父系的名稱指標。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [ICorDebugManagedCallback 介面](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
