---
title: "如何：對齊繪製的文字"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a2f2f6bd088ad58277839cf7e32a98d67ca3bd15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-align-drawn-text"></a>如何：對齊繪製的文字
當您執行自訂繪圖時，您通常可以置表單或控制項上描繪的文字。 您可以輕鬆地對齊，以繪製<xref:System.Drawing.Graphics.DrawString%2A>或<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法藉由建立正確格式化的物件，並設定適當的格式旗標。  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>若要繪製置中使用 GDI + (DrawString) 的文字  
  
1.  使用<xref:System.Drawing.StringFormat>適當<xref:System.Drawing.Graphics.DrawString%2A>方法來指定置中對齊的文字。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>若要繪製置中使用 GDI (DrawText) 的文字  
  
1.  使用<xref:System.Windows.Forms.TextFormatFlags>列舉文繞圖，以及垂直和水平置中與適當的文字<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 上述程式碼範例設計來搭配 Windows Form，它們需要<xref:System.Windows.Forms.PaintEventArgs> `e`，這是參數的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>另請參閱  
 [操作說明：使用 GDI 繪製文字](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [使用字型和文字](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [操作說明：建構字型系列和字型](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
