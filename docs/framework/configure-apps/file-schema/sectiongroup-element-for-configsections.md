---
title: "&lt;sectionGroup&gt;元素&lt;c&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c5c040a322c38da319f2e964519f94d761327e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="sectiongroup-element-for-configsections"></a>\<sectionGroup > 項目\<c >

定義組態區段的命名空間。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<c >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup >**

## <a name="syntax"></a>語法

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a>屬性

|           | 說明 |
| --------- | ----------- |
| **name**  | 必要屬性。<br><br>指定您要定義的區段群組名稱。 |

## <a name="parent-element"></a>父項目

|     | 說明 |
| --- | ----------- |
| [**\<c >**項目](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | 包含組態區段和命名空間宣告。 |

## <a name="child-elements"></a>子元素

|     | 說明 |
| --- | ----------- |
| [**\<區段 >**](~/docs/framework/configure-apps/file-schema/section-element.md) | 包含組態區段宣告。 |

## <a name="remarks"></a>備註

宣告區段群組建立的組態區段的容器標記，並確保沒有與其他人所定義的組態區段的命名衝突。 您可以巢狀 **\<sectionGroup >**中彼此的項目。

## <a name="example"></a>範例

下列範例會示範如何宣告區段群組和區段群組內宣告區段：

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>組態檔

此項目可以用於應用程式組態檔中，電腦組態檔 (*Machine.config*)，和*Web.config*不在應用程式目錄層級的檔案。

## <a name="see-also"></a>請參閱

[適用於.NET Framework 組態檔結構描述](~/docs/framework/configure-apps/file-schema/index.md)
