---
title: "如何：建立 Lambda 運算式 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16365b64e5430be61c113ac7601154df260e4ca5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>如何：建立 Lambda 運算式 (Visual Basic)
A *lambda 運算式*函式或副程式，沒有名稱。 Lambda 運算式可用於委派型別無效。  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>若要建立的單行 lambda 運算式函式  
  
1.  在委派類型可以使用其中任何情況下，輸入關鍵字`Function`，如下列範例所示：  
  
     `Dim add1 =`   `Function`  
  
2.  括號中，直接在之後`Function`，輸入函數的參數。 請注意，您不指定的名稱之後`Function`。  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  下列參數清單中，輸入單一運算式做為函式主體。 函數所傳回的值運算式評估為值。 您不使用`As`子句來指定傳回型別。  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     Lambda 運算式可以呼叫整數引數中傳遞。  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  此外，相同的結果便可達成以下範例：  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>若要建立的單行 lambda 運算式副程式  
  
1.  在委派類型可以使用其中任何情況下，輸入關鍵字`Sub`，如下列範例所示。  
  
     `Dim add1 =`   `Sub`  
  
2.  括號中，直接在之後`Sub`，型別副程式的參數。 請注意，您不指定的名稱之後`Sub`。  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  下列參數清單中，輸入在單一陳述式做為副程式的主體。  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Lambda 運算式可以呼叫傳入的字串引數。  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>若要建立多行 lambda 運算式函式  
  
1.  在委派類型可以使用其中任何情況下，輸入關鍵字`Function`，如下列範例所示。  
  
     `Dim add1 =`   `Function`  
  
2.  括號中，直接在之後`Function`，輸入函數的參數。 請注意，您不指定的名稱之後`Function`。  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  請按 ENTER 鍵。 `End Function`陳述式會自動加入。  
  
4.  在函式的主體內，加入下列程式碼，以建立運算式，並傳回值。 您不使用`As`子句來指定傳回型別。  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     Lambda 運算式可以呼叫整數引數中傳遞。  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>若要建立多行 lambda 運算式副程式  
  
1.  在委派類型可以使用其中任何情況下，輸入關鍵字`Sub`，如下列範例所示：  
  
     `Dim add1 =`   `Sub`  
  
2.  括號中，直接在之後`Sub`，型別副程式的參數。 請注意，您不指定的名稱之後`Sub`。  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  請按 ENTER 鍵。 `End Sub`陳述式會自動加入。  
  
4.  在函式的主體內，加入下列程式碼執行時叫用副程式。  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Lambda 運算式可以呼叫傳入的字串引數。  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>範例  
 Lambda 運算式的常見用法是定義可以做為參數的型別引數傳入的函式`Delegate`。 在下列範例中，<xref:System.Diagnostics.Process.GetProcesses%2A>方法會傳回本機電腦上執行的處理程序的陣列。 <xref:System.Linq.Enumerable.Where%2A>方法從<xref:System.Linq.Enumerable>類別會要求`Boolean`委派為其引數。 在範例中的 lambda 運算式用於此用途。 它會傳回`True`每個處理序只有一個執行緒，且那些中所選`filteredList`。  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 上述範例相當於下列程式碼，以撰寫[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]語法：  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Linq.Enumerable>  
 [Lambda 運算式](./lambda-expressions.md)  
 [Function 陳述式](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 陳述式](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [委派](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [如何：在 Visual Basic 中將程序傳遞至其他程序](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [Delegate 陳述式](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Visual Basic 中的 LINQ 簡介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
