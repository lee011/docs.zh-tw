---
title: "StrongNameSignatureVerificationEx 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationEx
helpviewer_keywords: StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0aebb53c6718a6812cbe6a6888f389c7b1a52dda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationex-function"></a>StrongNameSignatureVerificationEx 函式
取得值，指出是否在提供的路徑上組件資訊清單包含強式名稱簽章。  
  
 此函式已被取代。 使用[iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法改為。  
  
## <a name="syntax"></a>語法  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a>參數  
 `wszFilePath`  
 [in]可攜式執行檔 （.exe 或.dll） 檔案要驗證的組件路徑。  
  
 `fForceVerification`  
 [in]`true`執行驗證，即使它是必要的登錄設定會覆寫，否則`false`。  
  
 `pfWasVerified`  
 [out]`true`強式名稱簽章已通過驗證，否則如果`false`。 `pfWasVerified`也會設為`false`如果驗證已成功登錄設定所造成。  
  
## <a name="return-value"></a>傳回值  
 `true`如果驗證成功。否則， `false`。  
  
## <a name="remarks"></a>備註  
 `StrongNameSignatureVerificationEx`提供的功能類似於[StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)函式。 不過，第二個輸入參數和輸出參數`StrongNameSignatureVerificationEx`類型`BOOLEAN`而不是`DWORD`。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** StrongName.h  
  
 **程式庫：**包含做為 mscoree.dll 中的資源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [StrongNameSignatureVerificationEx 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [StrongNameSignatureVerification 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [ICLRStrongName 介面](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
