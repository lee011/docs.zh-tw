---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dead17435cd147bdcdf91bdc5b8e0aa651e9e9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="optimize"></a>/optimize
啟用或停用編譯器最佳化。  
  
## <a name="syntax"></a>語法  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a>引數  
  
|詞彙|定義|  
|---|---|  
|`+` &#124; `-`|選擇項。 `/optimize-`選項會停用編譯器最佳化。 `/optimize+`選項啟用最佳化。 根據預設，會停用最佳化。|  
  
## <a name="remarks"></a>備註  
 較小、 更快更有效率，編譯器最佳化會使輸出檔。 不過，因為最佳化導致輸出檔中的程式碼重新排列`/optimize+`可能會造成偵錯困難。  
  
 使用產生的所有模組`/target:module`組件必須使用相同`/optimize`設定與組件。 如需詳細資訊，請參閱[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)。  
  
 您可以結合`/optimize`和`/debug`選項。  
  
|若要設定 / Visual Studio 整合式的開發環境中最佳化|  
|---|  
|1.在 **方案總管**中選取專案。 在 [專案] 功能表上，按一下 [屬性]。<br />     如需詳細資訊，請參閱[專案設計工具簡介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。<br />2.按一下 [編譯] 索引標籤。<br />3.按一下 [ **進階** ] 按鈕。<br />4.修改**啟用最佳化**核取方塊。|  
  
## <a name="example"></a>範例  
 下列程式碼編譯`T2.vb`並啟用編譯器最佳化。  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a>另請參閱  
 [Visual Basic 命令列編譯器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [編譯命令列範例](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
