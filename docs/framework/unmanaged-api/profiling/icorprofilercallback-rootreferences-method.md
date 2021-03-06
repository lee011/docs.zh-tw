---
title: "ICorProfilerCallback::RootReferences 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RootReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12dec1ed0fecad235090592def9689f60e50193
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences 方法
通知分析工具的記憶體回收之後根參考的相關資訊。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a>參數  
 `cRootRefs`  
 [in]中的參考數目`rootRefIds`陣列。  
  
 `rootRefIds`  
 [in]參考靜態物件或物件在堆疊上的物件識別碼的陣列。  
  
## <a name="remarks"></a>備註  
 同時`RootReferences`和[icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)呼叫以通知分析工具。 程式碼剖析工具通常會實作，其中一個或另一個，但不是能同時，因為資訊傳入`RootReferences2`為傳入的超集`RootReferences`。  
  
 可能會`rootRefIds`陣列，包含 null 的物件。 例如，在堆疊上宣告的所有物件參考記憶體回收行程視為根，並將報告。  
  
 所傳回的物件識別碼`RootReferences`不自行，回呼期間有效，因為記憶體回收可能正在將物件從舊位址移到新的位址。 因此，分析工具必須不嘗試期間檢查物件`RootReferences`呼叫。 當[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)是呼叫，所有物件都已移至其新位置並且可以安全地進行檢查。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorProf.idl、CorProf.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [ICorProfilerCallback 介面](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
