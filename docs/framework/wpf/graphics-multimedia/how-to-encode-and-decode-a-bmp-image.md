---
title: "如何：編碼和解碼 BMP 影像"
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
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3c895a8a7c46020fa5277a3e592c7d3e18f02ab6
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a>如何：編碼和解碼 BMP 影像
下列範例示範如何解碼和編碼[!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)]映像使用特定<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>和<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>物件。  
  
## <a name="example"></a>範例  
 這個範例示範如何解碼[!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]映像使用<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>從<xref:System.Uri>。  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a>範例  
 此範例示範如何編碼<xref:System.Windows.Media.Imaging.BitmapSource>到[!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]映像使用<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>。  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a>另請參閱  
 [影像處理概觀](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
