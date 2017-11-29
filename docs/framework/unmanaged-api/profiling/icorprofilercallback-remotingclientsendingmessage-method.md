---
title: "ICorProfilerCallback::RemotingClientSendingMessage 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientSendingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a77acb736cec02da6839335e981016469eeb42b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="493fd-102">ICorProfilerCallback::RemotingClientSendingMessage 方法</span><span class="sxs-lookup"><span data-stu-id="493fd-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="493fd-103">通知分析工具，用戶端會將要求傳送至伺服器。</span><span class="sxs-lookup"><span data-stu-id="493fd-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="493fd-104">語法</span><span class="sxs-lookup"><span data-stu-id="493fd-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="493fd-105">參數</span><span class="sxs-lookup"><span data-stu-id="493fd-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="493fd-106">[in]一個值，對應中提供的值與[icorprofilercallback:: Remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)在這些情況下：</span><span class="sxs-lookup"><span data-stu-id="493fd-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="493fd-107">遠端處理 GUID cookie 是使用中。</span><span class="sxs-lookup"><span data-stu-id="493fd-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="493fd-108">成功的訊息傳輸通道。</span><span class="sxs-lookup"><span data-stu-id="493fd-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="493fd-109">GUID cookie 會啟用伺服器端處理程序。</span><span class="sxs-lookup"><span data-stu-id="493fd-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="493fd-110">這可讓您輕易地配對的遠端處理呼叫，以及邏輯呼叫堆疊的建立。</span><span class="sxs-lookup"><span data-stu-id="493fd-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="493fd-111">[in]值是`true`呼叫是非同步的; 否則如果`false`。</span><span class="sxs-lookup"><span data-stu-id="493fd-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="493fd-112">需求</span><span class="sxs-lookup"><span data-stu-id="493fd-112">Requirements</span></span>  
 <span data-ttu-id="493fd-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="493fd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="493fd-114">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="493fd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="493fd-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="493fd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="493fd-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="493fd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="493fd-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="493fd-117">See Also</span></span>  
 [<span data-ttu-id="493fd-118">ICorProfilerCallback 介面</span><span class="sxs-lookup"><span data-stu-id="493fd-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)