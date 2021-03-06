---
title: ICorDebugClass Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass
helpviewer_keywords: ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79e93a44f2cc532286a7e9b01fa32292a4e1c69a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass-interface1"></a>ICorDebugClass Interface1
表示類型，可以是基本類型或複雜類型 (亦即，使用者定義類型)。 如果是泛型類型，則 `ICorDebugClass` 表示未具現化的泛型類型。  
  
## <a name="methods"></a>方法  
  
|方法|說明|  
|------------|-----------------|  
|[GetModule 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|取得定義此類別的模組。|  
|[GetStaticFieldValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|取得指定的靜態欄位的值。|  
|[GetToken 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|取得`TypeDef`這個類別的中繼資料語彙基元。|  
  
## <a name="remarks"></a>備註  
 `ICorDebugClass`介面表示未具現化的泛型型別。 ICorDebugType 介面表示未具現化的泛型型別。 例如，`Hashtable<K, V>`表示`ICorDebugClass`，而`Hashtable<Int32, String>`表示`ICorDebugType`。  
  
 非泛型型別都由兩者`ICorDebugClass`和`ICorDebugType`。 處理類型具現化的.NET Framework 2.0 版中引進了第二個介面。  
  
> [!NOTE]
>  這個介面不支援跨電腦或跨處理序的遠端呼叫。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [偵錯介面](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
