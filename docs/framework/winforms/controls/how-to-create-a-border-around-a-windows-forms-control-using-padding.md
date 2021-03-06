---
title: "如何：使用邊框距離在 Windows Form 控制項周圍建立框線"
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
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 573a27343a15ef12ad955295c3beb3fef9130023
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>如何：使用邊框距離在 Windows Form 控制項周圍建立框線
下列程式碼範例示範如何建立框線或外框<xref:System.Windows.Forms.RichTextBox>控制項。 此範例設定的值<xref:System.Windows.Forms.Panel>控制項的<xref:System.Windows.Forms.Padding>5 和集合的屬性<xref:System.Windows.Forms.Control.Dock%2A>屬性的子系<xref:System.Windows.Forms.RichTextBox>控制權傳輸至<xref:System.Windows.Forms.DockStyle.Fill>。 <xref:System.Windows.Forms.Control.BackColor%2A>的<xref:System.Windows.Forms.Panel>控制設為  <xref:System.Drawing.Color.Blue%2A>，它會建立周圍的藍色框線<xref:System.Windows.Forms.RichTextBox>控制項。  
  
## <a name="example"></a>範例  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.Padding>  
 [Windows Forms 控制項的邊界和邊框距離](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)
