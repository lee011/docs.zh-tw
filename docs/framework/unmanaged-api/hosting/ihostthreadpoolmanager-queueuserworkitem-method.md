---
title: "IHostThreadPoolManager::QueueUserWorkItem 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.QueueUserWorkItem
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9948673d6988de21c83c37538fb4d7c030296e58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="37d10-102">IHostThreadPoolManager::QueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="37d10-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="37d10-103">對於執行，函式，並指定包含該函式所使用的資料的物件。</span><span class="sxs-lookup"><span data-stu-id="37d10-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="37d10-104">使用執行緒時，就會執行此函式。</span><span class="sxs-lookup"><span data-stu-id="37d10-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37d10-105">語法</span><span class="sxs-lookup"><span data-stu-id="37d10-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37d10-106">參數</span><span class="sxs-lookup"><span data-stu-id="37d10-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="37d10-107">[in]函式指標，表示要執行的函式。</span><span class="sxs-lookup"><span data-stu-id="37d10-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="37d10-108">[in]物件，包含要供資料`Function`。</span><span class="sxs-lookup"><span data-stu-id="37d10-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="37d10-109">[in]其中一個旗標值，如定義 win32`QueueUserWorkItem`方法，可控制執行。</span><span class="sxs-lookup"><span data-stu-id="37d10-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37d10-110">傳回值</span><span class="sxs-lookup"><span data-stu-id="37d10-110">Return Value</span></span>  
  
|<span data-ttu-id="37d10-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37d10-111">HRESULT</span></span>|<span data-ttu-id="37d10-112">描述</span><span class="sxs-lookup"><span data-stu-id="37d10-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37d10-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="37d10-113">S_OK</span></span>|<span data-ttu-id="37d10-114">`QueueUserWorkItem`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="37d10-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="37d10-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37d10-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37d10-116">Common language runtime (CLR) 尚未載入到處理程序，或 CLR 正在中它無法執行 managed 程式碼，或成功地處理呼叫的狀態。</span><span class="sxs-lookup"><span data-stu-id="37d10-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37d10-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37d10-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37d10-118">呼叫已逾時。</span><span class="sxs-lookup"><span data-stu-id="37d10-118">The call timed out.</span></span>|  
|<span data-ttu-id="37d10-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37d10-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37d10-120">呼叫端未擁有鎖定。</span><span class="sxs-lookup"><span data-stu-id="37d10-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37d10-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37d10-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37d10-122">事件已取消時封鎖的執行緒或 fiber 等候它。</span><span class="sxs-lookup"><span data-stu-id="37d10-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37d10-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37d10-123">E_FAIL</span></span>|<span data-ttu-id="37d10-124">發生未知的嚴重失敗。</span><span class="sxs-lookup"><span data-stu-id="37d10-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37d10-125">方法會傳回 E_FAIL CLR 已不再可用的處理序內。</span><span class="sxs-lookup"><span data-stu-id="37d10-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37d10-126">裝載方法的後續呼叫會傳回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="37d10-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37d10-127">備註</span><span class="sxs-lookup"><span data-stu-id="37d10-127">Remarks</span></span>  
 <span data-ttu-id="37d10-128">`QueueUserWorkItem`排入佇列的執行緒集區中，工作者執行緒的工作項目。</span><span class="sxs-lookup"><span data-stu-id="37d10-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="37d10-129">其簽章和參數型別完全相同，所對應的 Win32 函式，其具有相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="37d10-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="37d10-130">如需詳細資訊，請參閱 Windows 平台的文件。</span><span class="sxs-lookup"><span data-stu-id="37d10-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37d10-131">需求</span><span class="sxs-lookup"><span data-stu-id="37d10-131">Requirements</span></span>  
 <span data-ttu-id="37d10-132">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37d10-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37d10-133">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="37d10-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37d10-134">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="37d10-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37d10-135">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37d10-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d10-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="37d10-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="37d10-137">IHostThreadPoolManager 介面</span><span class="sxs-lookup"><span data-stu-id="37d10-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)