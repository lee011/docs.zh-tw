---
title: "如何：使用異動括住提交的資料"
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
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 071c0c8bc7e0bb8dca01e9fc51c66fb930ed102b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>如何：使用異動括住提交的資料
您可以使用 <xref:System.Transactions.TransactionScope> 來括住資料庫提交。 如需詳細資訊，請參閱[交易支援](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)。  
  
## <a name="example"></a>範例  
 下列程式碼會將資料庫提交封入 <xref:System.Transactions.TransactionScope> 中。  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>另請參閱  
 [下載範例資料庫](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [建立和提交資料變更](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [異動支援](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
