---
title: "ICorDebugVariableHome::GetOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ddedc83e4e51cf12a3f8a0504d90bda7f944a6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetoffset-method"></a>ICorDebugVariableHome::GetOffset 方法
取得從基底暫存器變數位移。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pOffset`  
 [out]基底暫存器從位移。  
  
## <a name="return-value"></a>傳回值  
 方法會傳回下列值：  
  
|值|說明|  
|-----------|-----------------|  
|`S_OK`|變數是在暫存器的相對記憶體位置。|  
|`E_FAIL`|變數不是在暫存器的相對記憶體位置。|  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [ICorDebugVariableHome 介面](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
