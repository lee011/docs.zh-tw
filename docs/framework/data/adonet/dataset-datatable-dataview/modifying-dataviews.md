---
title: "修改 DataView"
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
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0a8478e9b21c6c2abdc02677305e468109e7b9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="modifying-dataviews"></a>修改 DataView
您可以使用 <xref:System.Data.DataView> 加入、刪除或修改基底資料表中的資料列。 能夠使用**DataView**來修改基礎資料表中的資料由設定其中的三個布林值屬性**DataView**。 這些屬性是 <xref:System.Data.DataView.AllowNew%2A>、<xref:System.Data.DataView.AllowEdit%2A> 和 <xref:System.Data.DataView.AllowDelete%2A>。 它們會設定為**true**預設。  
  
 如果**AllowNew**是**true**，您可以使用<xref:System.Data.DataView.AddNew%2A>方法**DataView**來建立新的<xref:System.Data.DataRowView>。 請注意，新的資料列不是實際加入基礎<xref:System.Data.DataTable>直到<xref:System.Data.DataRowView.EndEdit%2A>方法**DataRowView**呼叫。 如果<xref:System.Data.DataRowView.CancelEdit%2A>方法**DataRowView**是呼叫，就會捨棄新的資料列。 也請注意，您可以進行編輯只有一個**DataRowView**一次。 如果您呼叫**AddNew**或**BeginEdit**方法**DataRowView**暫止資料列存在時， **EndEdit**上隱含呼叫暫止的資料列。 當**EndEdit**是呼叫，所做的變更套用至基礎**DataTable**而且可以稍後再認可或拒絕使用**AcceptChanges**或**RejectChanges**方法**DataTable**，**資料集**，或**DataRow**物件。 如果**AllowNew**是**false**，如果您呼叫會擲回例外狀況**AddNew**方法**DataRowView**。  
  
 如果**AllowEdit**是**true**，您可以修改的內容**DataRow**透過**DataRowView**。 您可以確認變更為基礎的資料列使用**DataRowView.EndEdit**或拒絕變更使用**DataRowView.CancelEdit**。 請注意您一次只能編輯一筆資料列。 如果您呼叫**AddNew**或**BeginEdit**方法**DataRowView**暫止資料列存在時， **EndEdit**上隱含呼叫暫止的資料列。 當**EndEdit**呼叫時，建議的變更會放在**目前**基礎的資料列版本**DataRow**而且可以稍後再認可或拒絕使用**AcceptChanges**或**RejectChanges**方法**DataTable**，**資料集**，或**DataRow**物件。 如果**AllowEdit**是**false**，如果您嘗試修改中的值，會擲回例外狀況**DataView**。  
  
 當現有**DataRowView**正在編輯中，基礎事件**DataTable**仍會引發與建議的變更。 請注意，如果您呼叫**EndEdit**或**CancelEdit**基礎**DataRow**、 暫止變更，將套用或取消無論**EndEdit**或**CancelEdit**上呼叫**DataRowView**。  
  
 如果**AllowDelete**是**true**，您可以刪除資料列從**DataView**使用**刪除**方法**DataView**或**DataRowView**物件和資料列會從基礎刪除**DataTable**。 您可以稍後再認可或拒絕刪除使用**AcceptChanges**或**RejectChanges**分別。 如果**AllowDelete**是**false**，如果您呼叫會擲回例外狀況**刪除**方法**DataView**或**DataRowView**。  
  
 下列程式碼範例會停用使用**DataView**來刪除資料列，並將新的資料列加入至基礎的資料表使用**DataView**。  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET Managed 提供者和 DataSet 開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)
