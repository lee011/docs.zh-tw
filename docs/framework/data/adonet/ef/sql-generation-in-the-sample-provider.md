---
title: "範例提供者中的 SQL 產生"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 58a49f7bf5d385466810a3c59bda748ef66d5840
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="sql-generation-in-the-sample-provider"></a>範例提供者中的 SQL 產生
[Entity Framework 範例提供者](http://go.microsoft.com/fwlink/?LinkId=180616)示範之 ADO.NET 資料提供者支援的新元件[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。  它會使用 SQL Server 2005 資料庫並且實作成 System.Data.SqlClient ADO.NET 2.0 資料提供者的包裝函式。  
  
 此範例提供者的 SQL 產生模組 (位於 SQL Generation 資料夾底下，但 DmlSqlGenerator.cs 檔案除外) 會接受輸入 DbQueryCommandTree 並且產生單一 SQL SELECT 陳述式。  
  
## <a name="in-this-section"></a>本章節內容  
 本節包括下列主題：  
  
 [架構和設計](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [逐步解說： SQL 產生](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>另請參閱  
 [SQL 產生](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
