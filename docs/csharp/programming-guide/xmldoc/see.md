---
title: "&lt;see&gt; (C# 程式設計手冊)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 065c85ba411794858c8c4d70de0ac1467da1fe56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="ltseegt-c-programming-guide"></a>&lt;see&gt; (C# 程式設計手冊)
## <a name="syntax"></a>語法  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>參數  
 cref = " `member`"  
 可從目前編譯環境呼叫的成員或欄位參考。 編譯器會檢查指定的程式碼項目是否存在，並將 `member` 傳遞給輸出 XML 中的項目名稱。請將 *member* 放在雙引號 (" ") 內。  
  
## <a name="remarks"></a>備註  
 \<see> 標記可讓您在文字內指定連結。 使用 [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) 指出文字應該放置於＜請參閱＞一節中。 使用 [cref 屬性](../../../csharp/programming-guide/xmldoc/cref-attribute.md)，建立程式碼項目之文件頁面的內部超連結。  
  
 編譯搭配 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 可處理檔案的文件註解。  
  
 下列範例示範摘要區段內的 \<see> 標記。  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a>另請參閱  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [建議使用的文件註解標籤](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
