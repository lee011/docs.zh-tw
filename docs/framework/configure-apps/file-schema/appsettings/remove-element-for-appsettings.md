---
title: "&lt;移除&gt;元素&lt;appSettings&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 10202a38d54e4c9744dbd20fb5f226fa41f5dab5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="remove-element-for-appsettings"></a>\<移除 > 項目\<appSettings >

移除自訂應用程式設定。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<移除 >**

## <a name="syntax"></a>語法

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a>屬性

|         | 說明 |
| ------- | ----------- |
| **key** | 必要屬性。<br><br>指定要移除之索引鍵的名稱。 |

### <a name="parent-element"></a>父項目

|     | 說明 |
| --- | ----------- |
| [**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | 包含自訂應用程式設定，例如檔案路徑、XML Web 服務 URL，或應用程式的任何其他自訂組態資訊。 |

## <a name="child-elements"></a>子元素

無

## <a name="example"></a>範例

下列範例示範如何移除自訂組態設定`ApplicationName`:

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a>請參閱

[適用於.NET Framework 組態檔結構描述](~/docs/framework/configure-apps/file-schema/index.md)