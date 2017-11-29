---
title: "IMetaDataEmit::DefineTypeRefByName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ce04733fa9f149f155d850c53b65b263943cf8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="a3ac4-102">IMetaDataEmit::DefineTypeRefByName 方法</span><span class="sxs-lookup"><span data-stu-id="a3ac4-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="a3ac4-103">取得定義在指定範圍內，是在目前範圍之外的類型中繼資料語彙基元。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ac4-104">語法</span><span class="sxs-lookup"><span data-stu-id="a3ac4-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3ac4-105">參數</span><span class="sxs-lookup"><span data-stu-id="a3ac4-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="a3ac4-106">[in]指定的解析範圍語彙基元。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="a3ac4-107">下列語彙基元的型別是有效的：</span><span class="sxs-lookup"><span data-stu-id="a3ac4-107">The following token types are valid:</span></span>  
  
-   <span data-ttu-id="a3ac4-108">`mdModuleRef`如果呼叫端定義所在的相同組件中定義的類型。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="a3ac4-109">`mdAssemblyRef`如果呼叫端定義的非組件中定義類型。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="a3ac4-110">`mdTypeRef`如果類型是巢狀的類型。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
-   <span data-ttu-id="a3ac4-111">`mdModule`如果在呼叫端定義所在的相同模組中定義類型。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="a3ac4-112">如果為 null，全域定義類型。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="a3ac4-113">[in]以 Unicode 的目標類型的名稱。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="a3ac4-114">[out]指標`mdTypeRef`指派給類型的語彙基元。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3ac4-115">需求</span><span class="sxs-lookup"><span data-stu-id="a3ac4-115">Requirements</span></span>  
 <span data-ttu-id="a3ac4-116">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3ac4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3ac4-117">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a3ac4-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3ac4-118">**程式庫：**做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="a3ac4-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3ac4-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ac4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ac4-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a3ac4-120">See Also</span></span>  
 [<span data-ttu-id="a3ac4-121">IMetaDataEmit 介面</span><span class="sxs-lookup"><span data-stu-id="a3ac4-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a3ac4-122">IMetaDataEmit2 介面</span><span class="sxs-lookup"><span data-stu-id="a3ac4-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)