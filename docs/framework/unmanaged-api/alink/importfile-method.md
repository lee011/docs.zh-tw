---
title: "ImportFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportFile
api_location: alink.dll
api_type: COM
f1_keywords: ImportFile
helpviewer_keywords: ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 46830699ba43c406da313653e1910e8f7a18a2ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="importfile-method"></a><span data-ttu-id="427eb-102">ImportFile 方法</span><span class="sxs-lookup"><span data-stu-id="427eb-102">ImportFile Method</span></span>
<span data-ttu-id="427eb-103">匯入組件和未繫結的模組。</span><span class="sxs-lookup"><span data-stu-id="427eb-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="427eb-104">語法</span><span class="sxs-lookup"><span data-stu-id="427eb-104">Syntax</span></span>  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="427eb-105">參數</span><span class="sxs-lookup"><span data-stu-id="427eb-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="427eb-106">要匯入檔案的完整限定的名稱。</span><span class="sxs-lookup"><span data-stu-id="427eb-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="427eb-107">可用來重新命名檔案，因為它會連結至組件的選擇性的輸出檔名稱。</span><span class="sxs-lookup"><span data-stu-id="427eb-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="427eb-108">如果為 TRUE，會使用 ImportTypes，否則匯入必須手動執行。</span><span class="sxs-lookup"><span data-stu-id="427eb-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="427eb-109">語彙基元的唯一檔案識別碼的儲存位置的指標。</span><span class="sxs-lookup"><span data-stu-id="427eb-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="427eb-110">組件或檔案，可以是檔案。</span><span class="sxs-lookup"><span data-stu-id="427eb-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="427eb-111">接收指標[IMetaDataAssemblyImport 介面](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="427eb-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="427eb-112">如果檔案不是組件時，就可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="427eb-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="427eb-113">檔案及/或已匯入的範圍數目指標。</span><span class="sxs-lookup"><span data-stu-id="427eb-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="427eb-114">傳回值</span><span class="sxs-lookup"><span data-stu-id="427eb-114">Return Value</span></span>  
 <span data-ttu-id="427eb-115">如果方法成功則傳回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="427eb-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="427eb-116">需求</span><span class="sxs-lookup"><span data-stu-id="427eb-116">Requirements</span></span>  
 <span data-ttu-id="427eb-117">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="427eb-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427eb-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="427eb-118">See Also</span></span>  
 [<span data-ttu-id="427eb-119">IALink 介面</span><span class="sxs-lookup"><span data-stu-id="427eb-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="427eb-120">IALink2 介面</span><span class="sxs-lookup"><span data-stu-id="427eb-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="427eb-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="427eb-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)