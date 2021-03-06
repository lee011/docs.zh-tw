---
title: "readonly (C# 參考)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords: readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b499f9fc5121afe6c2e92bcf8c5d2ac593b4c06c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-c-reference"></a>readonly (C# 參考)
`readonly` 關鍵字是您可以在欄位上使用的修飾詞。 欄位宣告包含 `readonly` 修飾詞時，宣告所引進欄位的指派只能出現為宣告的一部分或在相同類別的建構函式中。  
  
## <a name="example"></a>範例  
 在此範例中，無法變更 `ChangeYear`方法中的 `year` 欄位值，即使它在類別建構函式中獲指派值也是一樣︰  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 您只能在下列內容中將值指派給 `readonly` 欄位︰  
  
-   在宣告中初始化變數時，例如︰  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   對於執行個體欄位，在包含欄位宣告的類別的執行個體建構函式中，或者，對於靜態欄位，在包含欄位宣告的類別的靜態建構函式中。 這些也是適用於將 `readonly` 欄位傳遞為 [out](../../../csharp/language-reference/keywords/out.md) 或 [ref](../../../csharp/language-reference/keywords/ref.md) 參數的唯一內容。  
  
> [!NOTE]
>  `readonly` 關鍵字與 [const](../../../csharp/language-reference/keywords/const.md) 關鍵字不同。 `const` 欄位只能在欄位的宣告中初始化。 `readonly` 欄位可在宣告或建構函式中初始化。 因此，`readonly` 欄位可能會因使用的建構函式而有不同的值。 此外，雖然 `const` 欄位是編譯時間常數，但是 `readonly` 欄位可用於執行階段常數，如下列範例所示：  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a>範例  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 在上述範例中，如果您使用如下的陳述式︰  
  
 `p2.y = 66;        // Error`  
  
 則會收到編譯器錯誤訊息：  
  
 `The left-hand side of an assignment must be an l-value`  
  
 這是您嘗試將值指派給常數時所收到的相同錯誤。  
  
## <a name="c-language-specification"></a>C# 語言規格  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [C# 參考](../../../csharp/language-reference/index.md)  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [C# 關鍵字](../../../csharp/language-reference/keywords/index.md)  
 [修飾詞](../../../csharp/language-reference/keywords/modifiers.md)  
 [const](../../../csharp/language-reference/keywords/const.md)  
 [欄位](../../../csharp/programming-guide/classes-and-structs/fields.md)
