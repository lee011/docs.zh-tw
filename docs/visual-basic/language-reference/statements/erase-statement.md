---
title: "Erase 陳述式 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a2b439cf5ad04d59cea59bb21d345d0057b322
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="erase-statement-visual-basic"></a>Erase 陳述式 (Visual Basic)
用來釋放陣列變數及取消配置其元素所使用的記憶體。  
  
## <a name="syntax"></a>語法  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>組件  
 `arraylist`  
 必要項。 要清除的陣列變數的清單。 以逗號分隔多個變數。  
  
## <a name="remarks"></a>備註  
 `Erase`陳述式只可以出現在程序層級。 這表示您可以釋放程序內，但不是能在類別或模組層級的陣列。  
  
 `Erase`陳述式相當於指派`Nothing`給每個陣列變數。  
  
## <a name="example"></a>範例  
 下列範例會使用`Erase`陳述式來清除兩個陣列，並釋放其記憶體 (1000年和 100 個儲存體項目，分別)。 `ReDim`陳述式，然後將新的陣列執行個體指派給三維陣列。  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>另請參閱  
 [Nothing](../../../visual-basic/language-reference/nothing.md)  
 [ReDim 陳述式](../../../visual-basic/language-reference/statements/redim-statement.md)
