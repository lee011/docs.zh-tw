---
title: "ICLRMetaHost::GetRuntime 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type: apiref
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6ebfa1af4b824f4fcd4247cd7d0a667488f3e3ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime 方法
取得[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)對應至特定版本的 common language runtime (CLR) 的介面。 這個方法會取代[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函式搭配[STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)旗標。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pwzVersion`  
 [in].NET Framework 編譯版本儲存在中繼資料，以格式"v*A*。*B*[。*X*]"。 *A*， *B*，和*X*是對應至主要版本、 次要版本和組建編號的十進位數字。  
  
> [!NOTE]
>  C:\Windows\Microsoft.NET\Framework 或 C:\Windows\Microsoft.NET\Framework64 底下所顯示的樣子，這個參數必須符合.NET Framework 版本的目錄名稱。  
  
 範例值是"v1.0.3705"、"v1.1.4322"、"v2.0.50727，"和"v4.0。*X*"，其中*X*取決於已安裝的組建編號。 需要"v"前置詞。  
  
 `riid`  
 [in]所需的介面識別項。 目前，唯一有效的值，這個參數是 IID_ICLRRuntimeInfo。  
  
 `ppRuntime`  
 [out]指標[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)對應到要求的執行階段的介面。  
  
## <a name="return-value"></a>傳回值  
 這個方法會傳回下列特定的 HRESULT 以及 HRESULT 錯誤，以指出方法失敗。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|已成功完成命令。|  
|E_POINTER|`pwzVersion` 或 `ppRuntime` 為 null。|  
  
## <a name="remarks"></a>備註  
 這個方法以一致的方式會與互動傳統介面例如[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)介面和舊版的功能，例如已被取代`CorBindTo*`函式 (請參閱[取代 CLR 裝載函式](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)裝載 API 的.NET Framework 2.0 中)。 也就是執行階段會載入與舊版的 API，會顯示新的 api，而且載入新的 api 執行階段會顯示舊版的應用程式開發介面。 。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** MetaHost.h  
  
 **程式庫：**包含做為 MSCorEE.dll 中的資源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [ICLRMetaHost 介面](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [已被取代的 CLR 裝載介面和 Coclass](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 [CLR 裝載介面](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [已被取代的 CLR 裝載函式](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [裝載](../../../../docs/framework/unmanaged-api/hosting/index.md)
