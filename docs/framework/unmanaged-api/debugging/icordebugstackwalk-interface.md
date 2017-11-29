---
title: "ICorDebugStackWalk 介面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk
helpviewer_keywords: ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0c8a4421b716614081368755388bd2ab8d8fe22e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="9c6ed-102">ICorDebugStackWalk 介面</span><span class="sxs-lookup"><span data-stu-id="9c6ed-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="9c6ed-103">提供用來在執行緒堆疊上取得 Managed 方法或框架的方法。</span><span class="sxs-lookup"><span data-stu-id="9c6ed-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c6ed-104">方法</span><span class="sxs-lookup"><span data-stu-id="9c6ed-104">Methods</span></span>  
  
|<span data-ttu-id="9c6ed-105">方法</span><span class="sxs-lookup"><span data-stu-id="9c6ed-105">Method</span></span>|<span data-ttu-id="9c6ed-106">說明</span><span class="sxs-lookup"><span data-stu-id="9c6ed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c6ed-107">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="9c6ed-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="9c6ed-108">傳回目前的框架中的內容`ICorDebugStackWalk`物件。</span><span class="sxs-lookup"><span data-stu-id="9c6ed-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="9c6ed-109">SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="9c6ed-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="9c6ed-110">設定`ICorDebugStackWalk`物件的目前有效的內容執行緒內容。</span><span class="sxs-lookup"><span data-stu-id="9c6ed-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="9c6ed-111">Next 方法</span><span class="sxs-lookup"><span data-stu-id="9c6ed-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="9c6ed-112">移動`ICorDebugStackWalk`下一個畫面格的物件。</span><span class="sxs-lookup"><span data-stu-id="9c6ed-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="9c6ed-113">GetFrame 方法</span><span class="sxs-lookup"><span data-stu-id="9c6ed-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="9c6ed-114">取得目前的框架中`ICorDebugStackWalk`物件。</span><span class="sxs-lookup"><span data-stu-id="9c6ed-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c6ed-115">備註</span><span class="sxs-lookup"><span data-stu-id="9c6ed-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c6ed-116">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="9c6ed-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c6ed-117">需求</span><span class="sxs-lookup"><span data-stu-id="9c6ed-117">Requirements</span></span>  
 <span data-ttu-id="9c6ed-118">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c6ed-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c6ed-119">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c6ed-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c6ed-120">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c6ed-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c6ed-121">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c6ed-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c6ed-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9c6ed-122">See Also</span></span>  
 [<span data-ttu-id="9c6ed-123">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="9c6ed-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9c6ed-124">偵錯</span><span class="sxs-lookup"><span data-stu-id="9c6ed-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)