---
title: DataTableReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ed9094a036262bac2e101e7b4268aac2e66a0d10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="datatablereaders"></a>DataTableReader
<xref:System.Data.DataTableReader> 會以一個或多個唯讀順向結果集的形式來呈現 <xref:System.Data.DataTable> 或 <xref:System.Data.DataSet> 的內容。  
  
 當您建立**DataTableReader**從**DataTable**，產生**DataTableReader**物件包含一個結果集具有相同的資料為**DataTable**它是用來建立，除了已標示為已刪除的任何資料列。 資料行出現在相同的順序，與原始**DataTable**。  
  
 A **DataTableReader**可能包含多個結果集，如果它由呼叫建立<xref:System.Data.DataSet.CreateDataReader%2A>。 結果會依照相同順序**Datatable**中**資料集**物件的<xref:System.Data.DataSet.Tables%2A>集合。  
  
## <a name="in-this-section"></a>本章節內容  
 [建立 DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 討論如何建立**DataTableReader**物件。  
  
 [導覽 Datatable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 說明如何使用**讀取**方法來移動的內容**DataTableReader**。  
  
## <a name="see-also"></a>另請參閱  
 [在 ADO.NET 中擷取和修改資料](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed 提供者和 DataSet 開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)
