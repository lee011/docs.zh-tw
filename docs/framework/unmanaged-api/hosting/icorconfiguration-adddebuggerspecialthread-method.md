---
title: "ICorConfiguration::AddDebuggerSpecialThread 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.AddDebuggerSpecialThread
api_location: mscoree.dll
api_type: COM
f1_keywords: AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2501461267ff7369cd9c48f4cef6cda42063a48b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a>ICorConfiguration::AddDebuggerSpecialThread 方法
表示特定執行緒應該可以繼續執行，而偵錯工具有 managed 或 unmanaged 偵錯案例期間停止一個應用程式執行偵錯服務。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a>參數  
 `dwSpecialThreadId`  
 [in]允許繼續執行的執行緒識別碼。  
  
## <a name="remarks"></a>備註  
 指定的執行緒不會允許執行 managed 程式碼，或以任何方式進入執行階段中。 舉例來說，這類執行緒會以支援舊版指令碼偵錯工具在處理序執行緒。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** MSCorEE.h  
  
 **程式庫：**包含做為 MSCorEE.dll 中的資源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [ICorConfiguration 介面](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
