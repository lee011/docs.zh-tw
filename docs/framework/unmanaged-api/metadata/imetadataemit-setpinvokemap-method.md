---
title: "IMetaDataEmit::SetPinvokeMap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a10482b12f9a34b0f247779f22c7cc70f871324a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="a8e9a-102">IMetaDataEmit::SetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="a8e9a-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="a8e9a-103">設定或變更在先前呼叫所定義的功能，該方法的 PInvoke 簽章， [imetadataemit:: Definepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e9a-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e9a-104">語法</span><span class="sxs-lookup"><span data-stu-id="a8e9a-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8e9a-105">參數</span><span class="sxs-lookup"><span data-stu-id="a8e9a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a8e9a-106">[in]`mdToken`資訊套用到對應。</span><span class="sxs-lookup"><span data-stu-id="a8e9a-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="a8e9a-107">[in]用來執行對應 PInvoke 旗標。</span><span class="sxs-lookup"><span data-stu-id="a8e9a-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="a8e9a-108">這是位元遮罩`CorPinvokeMap`值。</span><span class="sxs-lookup"><span data-stu-id="a8e9a-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="a8e9a-109">[in]原生 DLL 中匯出目標的名稱。</span><span class="sxs-lookup"><span data-stu-id="a8e9a-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="a8e9a-110">[in]`mdModuleRef`權杖的目標 unmanaged DLL。</span><span class="sxs-lookup"><span data-stu-id="a8e9a-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8e9a-111">需求</span><span class="sxs-lookup"><span data-stu-id="a8e9a-111">Requirements</span></span>  
 <span data-ttu-id="a8e9a-112">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e9a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8e9a-113">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8e9a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8e9a-114">**程式庫：**做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="a8e9a-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8e9a-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8e9a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e9a-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a8e9a-116">See Also</span></span>  
 [<span data-ttu-id="a8e9a-117">IMetaDataEmit 介面</span><span class="sxs-lookup"><span data-stu-id="a8e9a-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a8e9a-118">IMetaDataEmit2 介面</span><span class="sxs-lookup"><span data-stu-id="a8e9a-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)