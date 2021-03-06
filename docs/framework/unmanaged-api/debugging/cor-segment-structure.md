---
title: "COR_SEGMENT 結構"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_SEGMENT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_SEGMENT
helpviewer_keywords: COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc7a749f92149d7f0f5725aec6d90d72e0582c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="corsegment-structure"></a>COR_SEGMENT 結構
包含 Managed 堆積中記憶體區域的相關資訊。  
  
## <a name="syntax"></a>語法  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a>成員  
  
|成員|說明|  
|------------|-----------------|  
|`start`|記憶體區域的起始位址。|  
|`end`|記憶體區域的結束位址。|  
|`gen`|A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)列舉的成員，表示記憶體區域的層代。|  
|`heap`|記憶體區域所在堆積數目。 如需詳細資訊，請參閱＜備註＞一節。|  
  
## <a name="remarks"></a>備註  
 `COR_SEGMENTS`結構表示的 managed 堆積中記憶體區域。  `COR_SEGMENTS`物件是成員的[ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)集合物件，會填入呼叫[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)方法。  
  
 `heap`欄位則是處理器數目，其對應到所回報的堆積。 用於工作站記憶體回收行程，其值永遠是零，因為工作站必須只有一個記憶體回收堆積。 伺服器記憶體回收行程，其值會對應至堆積附加至該處理器。 請注意可能會有更多或更少記憶體回收堆積比實際處理器由於記憶體回收行程的實作詳細資料。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [偵錯結構](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [偵錯](../../../../docs/framework/unmanaged-api/debugging/index.md)
