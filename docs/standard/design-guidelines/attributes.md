---
title: Attributes1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86fa2556e6b8fb82e31a7d4753354aa2dff627ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="attributes"></a><span data-ttu-id="df9c0-102">屬性</span><span class="sxs-lookup"><span data-stu-id="df9c0-102">Attributes</span></span>
<span data-ttu-id="df9c0-103"><xref:System.Attribute?displayProperty=nameWithType>是基底類別，用來定義自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="df9c0-104">屬性是可以加入至程式設計項目，例如組件、 類型、 成員和參數的註解。</span><span class="sxs-lookup"><span data-stu-id="df9c0-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="df9c0-105">它們會儲存在組件的中繼資料，而且可以在執行階段使用反映 Api 存取。</span><span class="sxs-lookup"><span data-stu-id="df9c0-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="df9c0-106">例如，架構會定義<xref:System.ObsoleteAttribute>，可以套用至類型或成員，表示類型或成員已被取代。</span><span class="sxs-lookup"><span data-stu-id="df9c0-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="df9c0-107">屬性可以有一或多個執行其他資料與屬性相關的屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="df9c0-108">例如，`ObsoleteAttribute`無法執行的版本中的其他資訊的類型或成員已被取代，而描述為新的 Api 取代過時的 API。</span><span class="sxs-lookup"><span data-stu-id="df9c0-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="df9c0-109">套用屬性時，就必須指定屬性的某些屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="df9c0-110">這些稱為必要的屬性或必要的引數，因為它們以位置的建構函式參數。</span><span class="sxs-lookup"><span data-stu-id="df9c0-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="df9c0-111">例如，<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A>屬性<xref:System.Diagnostics.ConditionalAttribute>是必要的屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="df9c0-112">選擇性的屬性 （或選擇性引數），會呼叫不一定需要指定已套用該屬性的屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="df9c0-113">所表示的可設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-113">They are represented by settable properties.</span></span> <span data-ttu-id="df9c0-114">編譯器提供特殊的語法，來套用屬性時設定這些屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="df9c0-115">例如，<xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>屬性表示選擇性的引數。</span><span class="sxs-lookup"><span data-stu-id="df9c0-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="df9c0-116">**✓ 不要**自訂屬性的後置詞的類別命名為 「 屬性 」。</span><span class="sxs-lookup"><span data-stu-id="df9c0-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="df9c0-117">**✓ 不要**套用<xref:System.AttributeUsageAttribute>自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="df9c0-118">**✓ 不要**提供選擇性引數的可設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="df9c0-119">**✓ 不要**屬性僅提供必要的引數。</span><span class="sxs-lookup"><span data-stu-id="df9c0-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="df9c0-120">**✓ 不要**提供初始化屬性對應到必要的引數的建構函式參數。</span><span class="sxs-lookup"><span data-stu-id="df9c0-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="df9c0-121">每個參數應該具有相同的名稱 （但仍會有不同的大小寫） 做為對應的屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="df9c0-122">**請避免 x**提供初始化屬性對應至選擇性引數的建構函式參數。</span><span class="sxs-lookup"><span data-stu-id="df9c0-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="df9c0-123">也就是說，不需要可以設定具有一個建構函式和 setter 的屬性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="df9c0-124">這個指導方針可讓非常明確的引數是選擇性的這是必要的並避免有兩個介面的操作方式相同。</span><span class="sxs-lookup"><span data-stu-id="df9c0-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="df9c0-125">**請避免 x**自訂屬性建構函式多載。</span><span class="sxs-lookup"><span data-stu-id="df9c0-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="df9c0-126">包含只有一個建構函式可清楚地使用者哪些引數是必要、 哪些是選擇性。</span><span class="sxs-lookup"><span data-stu-id="df9c0-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="df9c0-127">**✓ 不要**儘可能封裝自訂屬性的類別。</span><span class="sxs-lookup"><span data-stu-id="df9c0-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="df9c0-128">這可讓屬性查閱更快。</span><span class="sxs-lookup"><span data-stu-id="df9c0-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="df9c0-129">*部分 © 2005年，2009 Microsoft Corporation。All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="df9c0-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="df9c0-130">*皮耳森教育，inc.從權限所印製[Framework 設計方針： 慣例、 慣用語和可重複使用.NET 程式庫，第 2 版的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 並 Brad Abrams，發行 2008 年 10 月 22 日由Addison Wesley Professional，做為 Microsoft Windows 程式開發系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="df9c0-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9c0-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="df9c0-131">See Also</span></span>  
 [<span data-ttu-id="df9c0-132">Framework 設計方針</span><span class="sxs-lookup"><span data-stu-id="df9c0-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="df9c0-133">使用指導方針</span><span class="sxs-lookup"><span data-stu-id="df9c0-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)