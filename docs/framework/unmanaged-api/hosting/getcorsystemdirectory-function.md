---
title: "GetCORSystemDirectory 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORSystemDirectory
helpviewer_keywords: GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 802e9a7bd4e6caedd657a8e8cf0132d75b4cbc2e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory 函式
傳回 common language runtime (CLR) 載入到處理程序的安裝的目錄。 安裝目錄是完整名稱，例如，"c:\windows\microsoft.net\framework\v1.0.3705"。  
  
 此函式已被取代。 被取代[iclrruntimeinfo:: Getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)方法中提供[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>參數  
 `pbuffer`  
 [out]在其中執行階段會傳回字串，包含載入到處理序的執行階段安裝目錄的完整格式的名稱緩衝區。 如果執行階段尚未載入到程序，則函數會傳回最新版本的執行階段電腦上安裝適當的目錄資訊。  
  
 `cchBuffer`  
 [in]大小，以位元組為單位的`pbuffer`。  
  
 `dwLength`  
 [out]傳入的字元數`pbuffer`。  
  
## <a name="remarks"></a>備註  
  
> [!CAUTION]
>  請勿使用此函式中執行的 CLR 版本 4 的處理序。 如果在電腦上已安裝舊版的 clr，此函數會傳回該版本的安裝目錄。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** MSCorEE.h  
  
 **程式庫：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [已被取代的 CLR 裝載函式](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
