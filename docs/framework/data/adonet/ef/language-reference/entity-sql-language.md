---
title: "Entity SQL 語言"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 08e366e8bbd9df31f367496ca5e106b876921896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="entity-sql-language"></a>Entity SQL 語言
Entity SQL 是與儲存體無關的查詢語言，與 SQL 類似。 Entity SQL 可讓您查詢實體資料 (無論以物件形式或在表格式資料表中)。 在下列情況下，您可以考慮使用 Entity SQL：  
  
-   必須在執行階段動態建構查詢時。 在此情況下，您也可以考慮使用 <xref:System.Data.Objects.ObjectQuery%601> 的查詢產生器方法，而不在執行階段建構 Entity SQL 查詢字串。  
  
-   當您想要將查詢定義為模型定義的一部分時。 資料模型僅支援 Entity SQL。 如需詳細資訊，請參閱[QueryView 元素 (MSL)](http://msdn.microsoft.com/en-us/f0426b34-45cb-4fd7-9777-e0570c5e0e80)  
  
-   使用 EntityClient 傳回唯讀實體資料，做為使用 <xref:System.Data.EntityClient.EntityDataReader> 的資料列集時。 如需詳細資訊，請參閱[Entity Framework 的 EntityClient 提供者](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)。  
  
-   如果您非常熟悉 SQL 查詢語言，對您來說，Entity SQL 可能最易於使用。  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>搭配 EntityClient 提供者使用 Entity SQL  
 如果您想要搭配 EntityClient 提供者使用 Entity SQL，請參閱下列主題取得詳細資訊：  
  
 [Entity Framework 的 EntityClient 提供者](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [如何： 建置 Entitycollection 連接字串](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [如何： 執行可傳回 PrimitiveType 結果的查詢](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [如何： 執行可傳回 StructuralType 結果的查詢](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [如何： 執行可傳回 RefType 結果的查詢](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [如何： 執行可傳回複雜類型的查詢](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [如何： 執行可傳回巢狀的集合的查詢](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [如何： 使用 EntityCommand Entity SQL 查詢的執行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [如何： 執行參數化預存程序使用 EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [如何： 執行多型查詢](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [如何： 巡覽關聯性巡覽運算子](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>搭配物件查詢使用 Entity SQL  
 如果您想要搭配物件查詢使用 Entity SQL，請參閱下列主題取得詳細資訊：  
  
 [如何： 執行可傳回實體類型物件的查詢](http://msdn.microsoft.com/en-us/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [如何： 執行參數化的查詢](http://msdn.microsoft.com/en-us/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [如何： 巡覽關聯性使用導覽屬性](http://msdn.microsoft.com/en-us/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [如何： 呼叫使用者定義函式](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [如何： 篩選資料](http://msdn.microsoft.com/en-us/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [如何： 排序資料](http://msdn.microsoft.com/en-us/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [如何： 分組資料](http://msdn.microsoft.com/en-us/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [如何： 彙總資料](http://msdn.microsoft.com/en-us/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [如何： 執行可傳回匿名型別物件的查詢](http://msdn.microsoft.com/en-us/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [如何： 執行可傳回基本型別的集合的查詢](http://msdn.microsoft.com/en-us/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [如何： 查詢相關的物件的 EntityCollection](http://msdn.microsoft.com/en-us/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [如何： 排序兩個查詢的 Union](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313)  
  
 [如何： 逐頁檢視查詢結果](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a>本章節內容  
 [Entity SQL 概觀](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Entity SQL 參考](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>另請參閱  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [語言參考](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
