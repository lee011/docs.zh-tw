---
title: "命名參數"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b61f2b56b3b8bab67cec6db68a76916c6d7fa05a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="naming-parameters"></a>命名參數
超出明顯原因的可讀性，請務必遵循的指導方針的參數名稱，因為參數會顯示在文件和設計工具中，在視覺化設計工具提供 Intellisense 和瀏覽功能的類別。  
  
 **✓ 不要**camelCasing 用於參數名稱。  
  
 **✓ 不要**使用描述性的參數名稱。  
  
 **✓ 考慮**使用根據參數的意義，而不是參數的型別名稱。  
  
### <a name="naming-operator-overload-parameters"></a>運算子多載參數命名  
 **✓ 不要**使用`left`和`right`的二元運算子多載參數名稱是否有任何參數的意義。  
  
 **✓ 不要**使用`value`的一元運算子多載的參數名稱是否有任何參數的意義。  
  
 **✓ 考慮**有意義的名稱，如運算子多載參數，如果這樣做會增加重要的值。  
  
 **X 不**使用縮寫或數值索引運算子多載的參數名稱。  
  
 *部分 © 2005年，2009 Microsoft Corporation。All rights reserved.*  
  
 *皮耳森教育，inc.從權限所印製[Framework 設計方針： 慣例、 慣用語和可重複使用.NET 程式庫，第 2 版的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 並 Brad Abrams，發行 2008 年 10 月 22 日由Addison Wesley Professional，做為 Microsoft Windows 程式開發系列的一部分。*  
  
## <a name="see-also"></a>另請參閱  
 [Framework 設計方針](../../../docs/standard/design-guidelines/index.md)  
 [命名方針](../../../docs/standard/design-guidelines/naming-guidelines.md)
