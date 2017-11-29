---
title: "IAssemblyName::GetDisplayName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetDisplayName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 810192848e15a200a4b2eb33eaf60ddbd7c7c607
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="bc569-102">IAssemblyName::GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="bc569-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="bc569-103">取得人類看得懂的名稱所參考的組件[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)物件。</span><span class="sxs-lookup"><span data-stu-id="bc569-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc569-104">語法</span><span class="sxs-lookup"><span data-stu-id="bc569-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc569-105">參數</span><span class="sxs-lookup"><span data-stu-id="bc569-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="bc569-106">[out]包含參考的組件名稱的字串緩衝區。</span><span class="sxs-lookup"><span data-stu-id="bc569-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="bc569-107">[in、 out]大小`szDisplayName`寬字元，包括 null 結束字元。</span><span class="sxs-lookup"><span data-stu-id="bc569-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="bc569-108">[in]位元組合[ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md)會影響的功能值`szDisplayName`。</span><span class="sxs-lookup"><span data-stu-id="bc569-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc569-109">需求</span><span class="sxs-lookup"><span data-stu-id="bc569-109">Requirements</span></span>  
 <span data-ttu-id="bc569-110">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc569-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc569-111">**標頭：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="bc569-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bc569-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc569-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc569-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bc569-113">See Also</span></span>  
 [<span data-ttu-id="bc569-114">IAssemblyName 介面</span><span class="sxs-lookup"><span data-stu-id="bc569-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="bc569-115">融合列舉</span><span class="sxs-lookup"><span data-stu-id="bc569-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)