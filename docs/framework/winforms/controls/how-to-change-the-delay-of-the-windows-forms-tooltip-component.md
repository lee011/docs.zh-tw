---
title: "如何：變更 Windows Form ToolTip 元件的延遲時間"
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
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48bb8c08fa02a54f9bfd3febbe99f683fd68d7f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>如何：變更 Windows Form ToolTip 元件的延遲時間
有多個您可以設定 Windows Form 的延遲值<xref:System.Windows.Forms.ToolTip>元件。 所有這些屬性的量值的單位是毫秒。 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A>屬性會決定使用者必須指向在關聯控制項顯示之工具提示字串的時間長度。 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>屬性會設定才會出現一個工具提示相關聯的控制項在滑鼠移動，至另一個工具提示字串所花費的毫秒數。 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>屬性決定的工具提示字串會顯示的時間長度。 您可以個別或藉由設定的值來設定這些值<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>屬性; 屬性會根據設定的值指派給其他延遲<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>屬性。 例如，當<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>設為值為 N，<xref:System.Windows.Forms.ToolTip.InitialDelay%2A>設為 N，<xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>設定的值為<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>除以五個 （或 N/5） 和<xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>設定之值的五倍的值為<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>屬性 （或 5N）。  
  
### <a name="to-set-the-delay"></a>若要設定延遲  
  
1.  在此範例所示，設定下列屬性。  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>另請參閱  
 [ToolTip 元件概觀](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [操作說明：在設計階段設定 Windows Forms 上控制項的工具提示](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [ToolTip 元件](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
