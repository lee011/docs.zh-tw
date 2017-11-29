---
title: "ICorProfilerInfo2::GetThreadAppDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetThreadAppDomain
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4c8e16bc3d0a886e44bded3c274e5c53b43d75ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="d1558-102">ICorProfilerInfo2::GetThreadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="d1558-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="d1558-103">取得在其中指定的執行緒目前正在執行程式碼的應用程式定義域的 ID。</span><span class="sxs-lookup"><span data-stu-id="d1558-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1558-104">語法</span><span class="sxs-lookup"><span data-stu-id="d1558-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1558-105">參數</span><span class="sxs-lookup"><span data-stu-id="d1558-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="d1558-106">[in]指定在執行緒識別碼。</span><span class="sxs-lookup"><span data-stu-id="d1558-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="d1558-107">[out]應用程式定義域的識別碼指標。</span><span class="sxs-lookup"><span data-stu-id="d1558-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1558-108">需求</span><span class="sxs-lookup"><span data-stu-id="d1558-108">Requirements</span></span>  
 <span data-ttu-id="d1558-109">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1558-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1558-110">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d1558-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d1558-111">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1558-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1558-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1558-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1558-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d1558-113">See Also</span></span>  
 [<span data-ttu-id="d1558-114">ICorProfilerInfo 介面</span><span class="sxs-lookup"><span data-stu-id="d1558-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="d1558-115">ICorProfilerInfo2 介面</span><span class="sxs-lookup"><span data-stu-id="d1558-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)