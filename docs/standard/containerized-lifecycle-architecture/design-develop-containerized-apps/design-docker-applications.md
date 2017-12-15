---
title: "設計 Docker 應用程式"
description: "Microsoft 平台和工具與 Docker 容器化應用程式生命週期"
keywords: "Docker, 微服務, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: db8376abf95aab51fad23f4b351cb772351117ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="design-docker-applications"></a><span data-ttu-id="b83ef-104">設計 Docker 應用程式</span><span class="sxs-lookup"><span data-stu-id="b83ef-104">Design Docker applications</span></span>

<span data-ttu-id="b83ef-105">第 1 導入了有關容器和 Docker 的基本概念。</span><span class="sxs-lookup"><span data-stu-id="b83ef-105">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="b83ef-106">該資訊是資訊的基本的層級，若要開始使用您需要。</span><span class="sxs-lookup"><span data-stu-id="b83ef-106">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="b83ef-107">但是，企業應用程式可能很複雜，而不是單一服務或容器的多個服務所組成。</span><span class="sxs-lookup"><span data-stu-id="b83ef-107">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="b83ef-108">選擇性的使用情況下，您需要知道額外的方法，例如 Service-Oriented 架構 (SOA) 的設計，以及更多進階 microservices 概念和容器協調流程的概念。</span><span class="sxs-lookup"><span data-stu-id="b83ef-108">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="b83ef-109">本文件的範圍並不限於 microservices，但任何 Docker 應用程式生命週期 」，因此，它不會不瀏覽 microservices 架構深度因為您也可以使用容器和 Docker 規則聖多美、 背景工作或作業，或甚至使用整合型應用程式部署方法。</span><span class="sxs-lookup"><span data-stu-id="b83ef-109">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="b83ef-110">不過，我們 DevOps 與應用程式生命週期之前，務必了解如何您要設計並建構您的應用程式，以及您的設計選擇。</span><span class="sxs-lookup"><span data-stu-id="b83ef-110">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b83ef-111">[上一個](index.md) [下一步] (常見的容器-設計-principles.md)</span><span class="sxs-lookup"><span data-stu-id="b83ef-111">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>