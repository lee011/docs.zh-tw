---
title: "ServicePointManager.s_ServicePointTable 欄位"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type: apiref
api_name: System.Net.ServicePointManager.s_ServicePointTable
api_location: System.dll
api_type: Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2f12a8ba4d2b84e5b5d73d26199adf687a95a2df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable 欄位

`ServicePointManager.s_ServicePointTable`是<xref:System.Collections.Hashtable>包含使用中的 HTTP 連接的清單 (<xref:System.Net.ServicePoint>s) 中<xref:System.AppDomain>。

## <a name="syntax"></a>語法
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> `ServicePointManager.s_ServicePointTable`欄位是私用，而且不會直接在您的程式碼中使用它們。
> 
> Microsoft 不支援在實際執行應用程式在任何情況下使用此欄位。

## <a name="requirements"></a>需求

**命名空間：**<xref:System.Net>

**組件：**系統 （在 System.dll)

**.NET framework 版本：**自 2.0 起可用。
