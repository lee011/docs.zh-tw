---
title: "COR_DEBUG_IL_TO_NATIVE_MAP 結構"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_DEBUG_IL_TO_NATIVE_MAP
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords: COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa191a4235defc5f47d0f7b3d823605da17fb5f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugiltonativemap-structure"></a>COR_DEBUG_IL_TO_NATIVE_MAP 結構
包含用來將 Microsoft 中繼語言 (MSIL) 程式碼對應至機器碼的位移。  
  
## <a name="syntax"></a>語法  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a>成員  
  
|成員|說明|  
|------------|-----------------|  
|`ilOffset`|MSIL 程式碼的位移。|  
|`nativeStartOffset`|原生程式碼的開始位移。|  
|`nativeEndOffset`|原生程式碼結尾的位移。|  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorProf.idl、 CorDebug.idl  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [GetILToNativeMapping 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [GetILToNativeMapping 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [偵錯結構](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [偵錯](../../../../docs/framework/unmanaged-api/debugging/index.md)
