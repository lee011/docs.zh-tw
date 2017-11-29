---
title: "ICorProfilerInfo::SetEventMask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetEventMask
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bb42be7f8e5722ec9924284c257e814a186564d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="d9180-102">ICorProfilerInfo::SetEventMask 方法</span><span class="sxs-lookup"><span data-stu-id="d9180-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="d9180-103">設定一個值，以指定分析工具想要從通用語言執行平台 (CLR) 接收其通知的事件類型。</span><span class="sxs-lookup"><span data-stu-id="d9180-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9180-104">語法</span><span class="sxs-lookup"><span data-stu-id="d9180-104">Syntax</span></span>  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9180-105">參數</span><span class="sxs-lookup"><span data-stu-id="d9180-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="d9180-106">[in] 4 個位元組的值，可指定事件的分類。</span><span class="sxs-lookup"><span data-stu-id="d9180-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="d9180-107">每個位元分別控制不同的功能、行為或事件類型。</span><span class="sxs-lookup"><span data-stu-id="d9180-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="d9180-108">中所述的位元[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列舉型別。</span><span class="sxs-lookup"><span data-stu-id="d9180-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9180-109">備註</span><span class="sxs-lookup"><span data-stu-id="d9180-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9180-110">您應該呼叫[SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法，而不是此方法。</span><span class="sxs-lookup"><span data-stu-id="d9180-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="d9180-111">雖然`SetEventMask`方法會繼續受到支援， [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)提供額外的功能。</span><span class="sxs-lookup"><span data-stu-id="d9180-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9180-112">需求</span><span class="sxs-lookup"><span data-stu-id="d9180-112">Requirements</span></span>  
 <span data-ttu-id="d9180-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9180-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9180-114">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9180-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9180-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9180-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9180-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9180-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9180-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d9180-117">See Also</span></span>  
 [<span data-ttu-id="d9180-118">ICorProfilerInfo 介面</span><span class="sxs-lookup"><span data-stu-id="d9180-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="d9180-119">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="d9180-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)