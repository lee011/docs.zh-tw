---
title: "模型定義函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8e311d6e9c67a30636bdeaea7982057605678684
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="model-defined-function"></a>模型定義函式
A*模型定義函式*是概念模型中所定義的函式。 模型定義函式的主體以表示[Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)、 表示之外，獨立函式可讓規則或資料來源中支援的語言。  
  
 模型定義函式的定義包含下列資訊：  
  
-   函式名稱。 (必要項)  
  
-   傳回值的型別。 (選擇項)  
  
    > [!NOTE]
    >  若未指定任何傳回型別，則傳回值為 void。  
  
-   參數資訊。 (選擇項)  
  
-   [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)定義函式主體的運算式。  
  
 請注意，模型定義函式不支援輸出參數。 有此限制後才能夠撰寫模型定義函式。  
  
## <a name="example"></a>範例  
 下圖顯示包含三種實體類型 (`Book`、`Publisher` 和 `Author`) 的概念模型。  
  
 ![具有發行日期的模型](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)會使用稱為概念結構定義語言的特定領域語言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 來定義概念模型。 下列 CSDL 定義概念模型中的函式，會傳回上圖中 `Book` 執行個體發行年度以來的年份。  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>另請參閱  
 [實體資料模型的重要概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [實體資料模型](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [實體資料模型： 基本資料型別](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
