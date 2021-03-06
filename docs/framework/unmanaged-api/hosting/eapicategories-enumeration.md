---
title: "EApiCategories 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EApiCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: EApiCategories
helpviewer_keywords: EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eaff0133020fe84e58f8a130bffc8ddc2a55a19d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="eapicategories-enumeration"></a>EApiCategories 列舉
描述分類的主機可以封鎖無法在部分信任程式碼中執行的功能。  
  
## <a name="syntax"></a>語法  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>成員  
  
|成員|說明|  
|------------|-----------------|  
|`eAll`|指定所有 managed 類別和成員，涵蓋的其他`EApiCategories`欄位遭到封鎖而無法在部分信任程式碼中執行。|  
|`eExternalProcessMgmt`|指定封鎖受管理的類別和成員，可讓建立、 管理和解構的外部處理序在部分信任程式碼中執行。|  
|`eExternalThreading`|指定封鎖受管理的類別和成員，可讓建立、 管理和解構的外部執行緒在部分信任程式碼中執行。|  
|`eMayLeakOnAbort`|指定封鎖無法可能遺漏記憶體中止的 managed 的類型和成員在部分信任程式碼中執行。|  
|`eNoCategory`|指定無法在部分信任程式碼中執行封鎖的任何 managed 程式碼的類別。|  
|`eSecurityInfrastructure`|指定 common language runtime (CLR) 安全性基礎結構遭到封鎖而無法由部分信任程式碼。|  
|`eSelfAffectingProcessMgmt`|指定封鎖受管理的類別和其功能可能會影響受主控的處理序的成員在部分信任程式碼中執行。|  
|`eSelfAffectingThreading`|指定封鎖受管理的類別和其功能可能會影響裝載處理序中的執行緒的成員在部分信任程式碼中執行。|  
|`eSharedState`|指定封鎖受管理的類別和成員公開共用的狀態的部分信任程式碼中執行。|  
|`eSynchronization`|指定封鎖 common language runtime 類別和成員，可讓使用者程式碼保留鎖定在部分信任程式碼中執行。|  
|`eUI`|指定封鎖受管理的類別和成員允許或需要人為互動在部分信任程式碼中執行。|  
  
## <a name="remarks"></a>備註  
 [Iclrhostprotectionmanager:: Setprotectedcategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)方法使用的型別參數`EApiCategories`。  
  
 `EApiCategories`列舉型別和`SetProtectedCategories`方法直接相關的 managed<xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType>類別。 Managed 的類別會搭配<xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>列舉型別，其值會直接對應`EApiCategories`值，將 managed 型別和成員，將功能對應至所描述的類別公開`EApiCategories`。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** MSCorEE.h  
  
 **程式庫：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [ICLRHostProtectionManager 介面](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [裝載列舉](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
