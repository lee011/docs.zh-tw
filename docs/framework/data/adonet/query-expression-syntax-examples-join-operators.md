---
title: "查詢運算式語法範例：聯結運算子 (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 28f2627e991d6761306d6655ad4b2e3c0f61ebfc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="query-expression-syntax-examples-join-operators-linq-to-dataset"></a>查詢運算式語法範例：聯結運算子 (LINQ to DataSet)
在以彼此沒有可瀏覽關聯性之資料來源 (例如關聯式資料庫資料表) 為目標的查詢中，聯結 (Join) 是一項重要的作業。 兩個資料來源的聯結是指某個資料來源中的物件與另一個資料來源中共用相同屬性之物件的關聯。 如需詳細資訊，請參閱[標準查詢運算子概觀](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)。  
  
 此主題中的範例將示範如何使用 <xref:System.Linq.Enumerable.GroupJoin%2A> 和 <xref:System.Linq.Enumerable.Join%2A> 方法並搭配查詢運算式語法來查詢 <xref:System.Data.DataSet>。  
  
 `FillDataSet`這些範例中使用的方法會指定於[載入資料至資料集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。  
  
 此主題中的範例將使用 AdventureWorks 範例資料庫中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 資料表。  
  
 本主題中的範例使用下列`using` / `Imports`陳述式：  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 如需詳細資訊，請參閱[How to： 建立 LINQ to DataSet 專案在 Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)。  
  
## <a name="groupjoin"></a>GroupJoin  
  
### <a name="example"></a>範例  
 這則範例會針對 <xref:System.Linq.Enumerable.GroupJoin%2A> 和 `SalesOrderHeader` 資料表執行 `SalesOrderDetail`，以便尋找每位客戶的訂單數目。 群組聯結是左外部聯結的對等項目，它會傳回第一個 (左) 資料來源的每個項目，即使其他資料來源中沒有相互關聯的項目也一樣。  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a>範例  
 這則範例會針對 <xref:System.Linq.Enumerable.GroupJoin%2A> 和 `Contact` 資料表執行 `SalesOrderHeader`。 群組聯結是左外部聯結的對等項目，它會傳回第一個 (左) 資料來源的每個項目，即使其他資料來源中沒有相互關聯的項目也一樣。  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a>Join  
  
### <a name="example"></a>範例  
 這則範例會針對 `SalesOrderHeader` 和 `SalesOrderDetail` 資料表執行聯結，以便取得八月份的線上訂單。  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>另請參閱  
 [載入資料至資料集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [LINQ to DataSet 範例](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [標準查詢運算子概觀](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
