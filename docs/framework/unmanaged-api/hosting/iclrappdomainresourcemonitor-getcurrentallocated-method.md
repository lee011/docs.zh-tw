---
title: "ICLRAppDomainResourceMonitor::GetCurrentAllocated 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dee616e1fbd071662a42af856fa2cd51f7bdd5d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="5449d-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="5449d-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="5449d-103">取得以位元組為單位建立以來，但不減去已回收的記憶體，由應用程式定義域所做的所有記憶體配置的大小總計。</span><span class="sxs-lookup"><span data-stu-id="5449d-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5449d-104">語法</span><span class="sxs-lookup"><span data-stu-id="5449d-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5449d-105">參數</span><span class="sxs-lookup"><span data-stu-id="5449d-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="5449d-106">[in]要求的應用程式定義域的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5449d-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="5449d-107">[out]所有記憶體配置總大小的指標。</span><span class="sxs-lookup"><span data-stu-id="5449d-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5449d-108">傳回值</span><span class="sxs-lookup"><span data-stu-id="5449d-108">Return Value</span></span>  
 <span data-ttu-id="5449d-109">這個方法會傳回下列特定的 HRESULT 以及 HRESULT 錯誤，以指出方法失敗。</span><span class="sxs-lookup"><span data-stu-id="5449d-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5449d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5449d-110">HRESULT</span></span>|<span data-ttu-id="5449d-111">描述</span><span class="sxs-lookup"><span data-stu-id="5449d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5449d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5449d-112">S_OK</span></span>|<span data-ttu-id="5449d-113">已成功完成命令。</span><span class="sxs-lookup"><span data-stu-id="5449d-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="5449d-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="5449d-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="5449d-115">應用程式定義域已卸載或不存在。</span><span class="sxs-lookup"><span data-stu-id="5449d-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5449d-116">備註</span><span class="sxs-lookup"><span data-stu-id="5449d-116">Remarks</span></span>  
 <span data-ttu-id="5449d-117">這個方法相當於 unmanaged 的 managed<xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>屬性。</span><span class="sxs-lookup"><span data-stu-id="5449d-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5449d-118">需求</span><span class="sxs-lookup"><span data-stu-id="5449d-118">Requirements</span></span>  
 <span data-ttu-id="5449d-119">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5449d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5449d-120">**標頭：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5449d-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5449d-121">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="5449d-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5449d-122">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5449d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5449d-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5449d-123">See Also</span></span>  
 [<span data-ttu-id="5449d-124">ICLRAppDomainResourceMonitor 介面</span><span class="sxs-lookup"><span data-stu-id="5449d-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="5449d-125">應用程式定義域資源監視</span><span class="sxs-lookup"><span data-stu-id="5449d-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="5449d-126">裝載介面</span><span class="sxs-lookup"><span data-stu-id="5449d-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="5449d-127">裝載</span><span class="sxs-lookup"><span data-stu-id="5449d-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)