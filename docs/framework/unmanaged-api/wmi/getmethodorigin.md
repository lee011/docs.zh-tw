---
title: "GetMethodOrigin 函式 （Unmanaged API 參考）"
description: "GetMethodOrigin 函式判斷宣告方法的類別。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethodOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethodOrigin
helpviewer_keywords: GetMethodOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7982ef2f272173e89434b64a4c296a2ce963594e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2017
---
# <a name="getmethodorigin-function"></a>GetMethodOrigin 函式
判斷在其中宣告方法的類別。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>語法  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a>參數

`vFunc`  
[in]未使用這個參數。

`ptr`  
[in]指標[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)執行個體。

`wszMethodName`  
[in]正在要求其主控類別之物件的方法名稱。 

`pstrClassName`  
[out]接收擁有方法的類別名稱。

## <a name="return-value"></a>傳回值

這個函式傳回下列值會定義在*WbemCli.h*標頭檔，或者您可以定義它們以常數的形式在程式碼中：

|常數  |值  |說明  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 而會收到 0x80041002 | 找不到指定的方法。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一或多個參數都不是有效的。 |
|`WBEM_S_NO_ERROR` | 0 | 函式呼叫成功。  |
  
## <a name="remarks"></a>備註

此函式會包裝呼叫[IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)方法。

類別可以繼承一或多個基底類別方法，因為開發人員通常會想要判斷指定的方法定義所在的類別。

`pstrClassName`參數必須是指向有效`BSTR`因為這是在呼叫函式前`out`參數; 此指標會取消配置函式傳回後。

## <a name="requirements"></a>需求  
**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>請參閱  
[WMI 和效能計數器 （Unmanaged API 參考）](index.md)
