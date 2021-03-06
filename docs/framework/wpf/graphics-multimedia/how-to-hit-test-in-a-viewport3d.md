---
title: "如何：Viewport3D 中的點擊測試"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: efd8016e0169a258dbe7b6d9a54a81b1cda94ee4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>如何：Viewport3D 中的點擊測試
這個範例示範如何進行點擊測試的 3D 視覺效果中<xref:System.Windows.Controls.Viewport3D>。  
  
 因為<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>2D 和 3D 資訊時，會傳回可逐一查看測試結果，以了解只有 3D 的結果。  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <xref:System.Windows.Media.HitTestResultBehavior>在下列程式碼會判斷點擊的測試結果的處理方式。  `UpdateResultInfo`和`UpdateMaterial`本機定義的方法。  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a>另請參閱  
 [3-D 點擊測試範例](http://go.microsoft.com/fwlink/?LinkID=159959)
