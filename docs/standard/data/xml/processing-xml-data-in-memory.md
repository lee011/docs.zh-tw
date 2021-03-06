---
title: "處理記憶體中的 XML 資料"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec4ccbff095071b279e07cee6a1aab3ca830423f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="processing-xml-data-in-memory"></a>處理記憶體中的 XML 資料
Microsoft.NET Framework 包含三個模型，來處理 XML 資料：<xref:System.Xml.XmlDocument>類別<xref:System.Xml.XPath.XPathDocument>類別，和[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)。  
  
 <xref:System.Xml.XmlDocument> 類別會實作 W3C 文件物件模型 (DOM) 層級 1 核心及核心 DOM 層級 2 建議事項。 DOM 是 XML 文件的記憶體中 (快取) 樹狀結構表示。 透過 <xref:System.Xml.XmlDocument> 及其相關類別，您可以建構 XML 文件、載入並存取資料、修改資料，以及儲存變更。  
  
 <xref:System.Xml.XPath.XPathDocument> 類別是唯讀的記憶體中資料存放區，以 XPath 資料模型為基礎。 <xref:System.Xml.XPath.XPathNavigator> 類別提供了數種可在唯讀 <xref:System.Xml.XPath.XPathDocument> 類別及 <xref:System.Xml.XmlDocument> 類別包含的 XML 文件中使用游標模型的編輯選項與巡覽功能。  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)是.NET Framework 3.5 版來處理 XML 資料中的新模型。 它是記憶體中模型，其會利用[LINQ (Language-Integrated Query ()](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)。 LINQ 會擴充 C# 和 Visual Basic 的語言語法，以提供新的查詢功能。  
  
## <a name="in-this-section"></a>本章節內容  
 [使用 DOM 模型處理 XML 資料](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 討論如何使用 <xref:System.Xml.XmlDocument> 及其相關類別來處理 XML 資料。  
  
 [使用 XPath 資料模型處理 XML 資料](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 討論如何使用 <xref:System.Xml.XPath.XPathDocument>、<xref:System.Xml.XmlDocument> 及 <xref:System.Xml.XPath.XPathNavigator> 類別來處理 XML 資料。  
  
 [使用 LINQ to XML 處理 XML 資料](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 提供 LINQ to XML 的簡短概觀，並提供 LINQ to XML 文件的連結。  
  
## <a name="related-sections"></a>相關章節  
 [XML 文件和資料](../../../../docs/standard/data/xml/index.md)
