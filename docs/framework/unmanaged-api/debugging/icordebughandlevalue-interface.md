---
title: ICorDebugHandleValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHandleValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHandleValue
helpviewer_keywords: ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b56c23caaaed2bc63c724769db1198fd088f7f1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebughandlevalue-interface1"></a>ICorDebugHandleValue Interface1
ICorDebugReferenceValue，表示要偵錯工具已建立的記憶體回收控制代碼的參考值的子類別。  
  
## <a name="methods"></a>方法  
  
|方法|說明|  
|------------|-----------------|  
|[Dispose 方法](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|釋放的控制代碼所參考`ICorDebugHandleValue`物件，而不會明確地釋放的介面指標。|  
|[GetHandleType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|取得描述類型的控制代碼所參考的 CorDebugHandleType 值`ICorDebugHandleValue`。|  
  
## <a name="remarks"></a>備註  
 `ICorDebugReferenceValue`物件無效的執行中的偵錯的程式碼中斷。 `ICorDebugHandleValue`維護符號和接續，透過其參考，直到明確釋放為止。  
  
> [!NOTE]
>  這個介面不支援跨電腦或跨處理序的遠端呼叫。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [偵錯介面](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
