---
title: "取得支援的 UI 自動化控制項模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
caps.latest.revision: "10"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 8917890d86f059d85ad9b6a0bcf6d9a41d65585a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="get-supported-ui-automation-control-patterns"></a>取得支援的 UI 自動化控制項模式
> [!NOTE]
>  這份文件適用於想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空間中定義之 Managed <xref:System.Windows.Automation> 類別的 .NET Framework 開發人員。 如需 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新資訊，請參閱 [Windows Automation API：UI 自動化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主題示範如何擷取控制項模式物件從[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]項目。  
  
### <a name="obtain-all-control-patterns"></a>取得所有控制項模式  
  
1.  取得<xref:System.Windows.Automation.AutomationElement>您對其控制項模式有興趣。  
  
2.  呼叫<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>來取得項目的所有控制項模式。  
  
> [!CAUTION]
>  強烈建議用戶端未使用<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>。 可以被嚴重影響效能，因為這個方法會呼叫<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>在內部針對每個現有的控制項模式。 可能的話，用戶端應該呼叫<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>針對感興趣的重要模式。  
  
### <a name="obtain-a-specific-control-pattern"></a>取得特定的控制項模式  
  
1.  取得<xref:System.Windows.Automation.AutomationElement>您對其控制項模式有興趣。  
  
2.  呼叫<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>或<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>以查詢特定模式。 這些方法很相似，但是，如果找不到模式，<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>引發例外狀況，以及<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>傳回`false`。  
  
## <a name="example"></a>範例  
 下列範例會擷取<xref:System.Windows.Automation.AutomationElement>清單項目，並取得<xref:System.Windows.Automation.SelectionItemPattern>從該項目。  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>另請參閱  
 [用戶端的 UI 自動化控制項模式](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
