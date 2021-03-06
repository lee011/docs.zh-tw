---
title: "CorDebugBlockingObject 結構"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingObject Structure
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingObject
helpviewer_keywords: CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c47735565c960c2600f7274d0d59d5a6ec6c178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject 結構
定義為以及封鎖執行緒的執行緒會封鎖的特定原因的物件。  
  
## <a name="syntax"></a>語法  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>成員  
  
|成員|說明|  
|------------|-----------------|  
|`pBlockingObject`|物件所在的執行緒會封鎖。 僅針對目前已同步處理狀態的持續時間，這個物件是有效的。 如果兩個執行緒會封鎖在相同的已同步處理狀態中相同的物件上，您可能預期[icordebugvalue:: Getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)方法以傳回相同的值。 不過，介面可能會或可能不是對等的指標。|  
|`dwTimeout`|逾時或無限，表示它將會逾時的值，將會封鎖作業之前的毫秒數。逾時值指定的總時間封鎖作業，而不是仍在剩餘的時間長度。|  
|`blockingReason`|執行緒已在此物件上封鎖原因。|  
  
## <a name="remarks"></a>備註  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [偵錯結構](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [偵錯](../../../../docs/framework/unmanaged-api/debugging/index.md)
