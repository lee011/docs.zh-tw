---
title: "IMetaDataFilter::IsTokenMarked 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter.IsTokenMarked
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 832f1e57e55245a84d093a41c627613d5fbe6902
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafilteristokenmarked-method"></a>IMetaDataFilter::IsTokenMarked 方法
取得值，指出指定的中繼資料語彙基元是否已標示為處理。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
#### <a name="parameters"></a>參數  
 `tk`  
 [in]要檢查處理標記的語彙基元。  
  
 `pIsMarked`  
 [out]值是`true`如果`tk`已處理，否則為`false`。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** Cor.h  
  
 **程式庫：**做為 MsCorEE.dll 中的資源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [IMetaDataFilter 介面](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
