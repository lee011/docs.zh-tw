---
title: "操作說明：從繫結的目標屬性取得繫結物件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 498849cc0205775f88c21d90d12b45c6b71a5dec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>操作說明：從繫結的目標屬性取得繫結物件
這個範例顯示如何從資料繫結目標屬性取得繫結物件。  
  
## <a name="example"></a>範例  
 您可以執行下列命令來取得<xref:System.Windows.Data.Binding>物件：  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  因為目標物件可能有多個屬性使用資料繫結，所以必須指定所要繫結的相依性屬性。  
  
 或者，您可以取得<xref:System.Windows.Data.BindingExpression>，然後取得的值<xref:System.Windows.Data.BindingExpression.ParentBinding%2A>屬性。  
  
 如需完整範例，請參閱[繫結驗證範例 (英文)](http://go.microsoft.com/fwlink/?LinkID=159972)。  
  
> [!NOTE]
>  如果您繫結是<xref:System.Windows.Data.MultiBinding>，使用<xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>。 如果是<xref:System.Windows.Data.PriorityBinding>，使用<xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>。 如果您不確定是否目標屬性會使用繫結<xref:System.Windows.Data.Binding>、 <xref:System.Windows.Data.MultiBinding>，或<xref:System.Windows.Data.PriorityBinding>，您可以使用<xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>。  
  
## <a name="see-also"></a>另請參閱  
 [使用程式碼建立繫結](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [操作說明主題](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
