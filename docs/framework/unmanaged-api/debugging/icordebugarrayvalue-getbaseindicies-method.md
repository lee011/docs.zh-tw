---
title: "ICorDebugArrayValue::GetBaseIndicies 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetBaseIndicies
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c8705e31e99effd8741029f9709f3982e097a693
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="ffae0-102">ICorDebugArrayValue::GetBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="ffae0-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="ffae0-103">取得陣列中的每個維度的基底的索引。</span><span class="sxs-lookup"><span data-stu-id="ffae0-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffae0-104">語法</span><span class="sxs-lookup"><span data-stu-id="ffae0-104">Syntax</span></span>  
  
```  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ffae0-105">參數</span><span class="sxs-lookup"><span data-stu-id="ffae0-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="ffae0-106">[in]這個維度的數目`ICorDebugArrayValue`物件。</span><span class="sxs-lookup"><span data-stu-id="ffae0-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="ffae0-107">此值也是大小`indicies`因為其大小的維度數目等於陣列`ICorDebugArrayValue`物件。</span><span class="sxs-lookup"><span data-stu-id="ffae0-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="ffae0-108">[out]整數的陣列，其中每一個都是這個維度的基底的索引 （也就是說，起始索引）`ICorDebugArrayValue`物件。</span><span class="sxs-lookup"><span data-stu-id="ffae0-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffae0-109">需求</span><span class="sxs-lookup"><span data-stu-id="ffae0-109">Requirements</span></span>  
 <span data-ttu-id="ffae0-110">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffae0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffae0-111">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffae0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffae0-112">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffae0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffae0-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffae0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>