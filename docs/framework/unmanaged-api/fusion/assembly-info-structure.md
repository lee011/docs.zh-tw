---
title: "ASSEMBLY_INFO 結構"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyinfo-structure"></a>ASSEMBLY_INFO 結構
包含在全域組件快取中註冊組件的資訊。  
  
## <a name="syntax"></a>語法  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>成員  
  
|成員|說明|  
|------------|-----------------|  
|`cbAssemblyInfo`|以位元組為單位的結構大小。 這個欄位被保留供未來擴充。|  
|`dwAssemblyFlags`|旗標，表示組件的相關的安裝詳細資料。 支援下列值：<br /><br /> -ASSEMBLYINFO_FLAG_INSTALLED 值，指出已安裝的組件。 目前的.NET framework 版本一律設定`dwAssemblyFlags`為這個值。<br />表示組件是常駐裝載-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 值。 目前的.NET framework 版本永遠不會設定`dwAssemblyFlags`為這個值。|  
|`uliAssemblySizeInKB`|總大小，以 kb 為單位的組件包含的檔案。|  
|`pszCurrentAssemblyPathBuf`|資訊清單檔案會保留目前的路徑字串緩衝區的指標。 路徑必須以 null 字元結尾。|  
|`cchBuf`|的寬字元數目，包括 null 結束字元，`pszCurrentAssemblyPathBuf`包含。|  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** Fusion.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [融合結構](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [全域組件快取](../../../../docs/framework/app-domains/gac.md)
