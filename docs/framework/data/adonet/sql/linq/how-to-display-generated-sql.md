---
title: "如何：顯示產生的 SQL"
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
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 523a6cbd0174da4c294e5fd2ab2d0217fc63cb5c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-generated-sql"></a>如何：顯示產生的 SQL
您可以檢視針對查詢所產生的 SQL 程式碼，並且使用 <xref:System.Data.Linq.DataContext.Log%2A> 屬性變更處理。 若要了解 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 功能以及對特定問題進行偵錯，這個方法很實用。  
  
## <a name="example"></a>範例  
 下列範例會使用 <xref:System.Data.Linq.DataContext.Log%2A> 屬性，在執行 SQL 程式碼之前，於主控台視窗中顯示該程式碼。  您可以使用這個屬性搭配查詢、插入、更新和刪除命令。  
  
 主控台視窗中的程式行就是您在執行下列 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 或 C# 程式碼時所看到的內容。  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>另請參閱  
 [偵錯支援](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
