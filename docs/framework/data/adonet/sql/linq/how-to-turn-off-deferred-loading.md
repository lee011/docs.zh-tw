---
title: "如何：關閉延後載入"
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
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d98b190ef4454ff29318eb6ef0f20624c85b62a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-turn-off-deferred-loading"></a>如何：關閉延後載入
您可以將 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> 設定為 `false`，以關閉延後載入。 如需詳細資訊，請參閱[延後執行與立即載入](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)。  
  
> [!NOTE]
>  關閉物件追蹤時，也會隱含地關閉延後載入。 如需詳細資訊，請參閱[How to： 擷取資訊為唯讀](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)。  
  
## <a name="example"></a>範例  
 下列範例顯示如何將 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> 設定為 `false`，以關閉延後載入。  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>另請參閱  
 [查詢概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [查詢資料庫](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
