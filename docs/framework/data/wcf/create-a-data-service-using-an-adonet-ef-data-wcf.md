---
title: "如何：使用 ADO.NET Entity Framework 資料來源建立資料服務 (WCF 資料服務)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77a4b90b16a92e993d9283932b2a609f874c7568
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>如何：使用 ADO.NET Entity Framework 資料來源建立資料服務 (WCF 資料服務)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 會將實體資料公開為資料服務。 當資料來源為關聯式資料庫時，這個實體資料會由 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 提供。 本主題示範如何在以現有資料庫為基礎的 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 應用程式中建立 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 架構資料模型，並使用此資料模型建立新的資料服務。  
  
 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 也提供命令列工具，可在 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 專案以外產生 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 模型。 如需詳細資訊，請參閱[How to： 使用 EdmGen.exe 產生模型和對應檔](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>若要將以現有資料庫為基礎的 Entity Framework 模型加入至現有的 Web 應用程式  
  
1.  在**專案**功能表上，按一下 **加入新項目**。  
  
2.  在**範本**] 窗格中，按一下 [**資料**類別目錄，然後選取**ADO.NET 實體資料模型**。  
  
3.  輸入模型名稱，然後按一下**新增**。  
  
     [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 精靈的第一頁隨即出現。  
  
4.  在**選擇模型內容**對話方塊中，選取**從資料庫產生**。 然後按 [下一步] 。  
  
5.  按一下**新連線** 按鈕。  
  
6.  在**連接屬性**對話方塊中，輸入您的伺服器名稱、 選取驗證方法、 輸入資料庫名稱，然後按一下**確定**。  
  
     **選擇資料連接**的對話方塊會更新與您的資料庫連接設定。  
  
7.  請確認**將實體連接設定儲存為 App.Config 中：**核取方塊。 然後按 [下一步] 。  
  
8.  在**選擇您的資料庫物件**對話方塊中，選取的所有資料庫物件想要在資料服務中公開。  
  
    > [!NOTE]
    >  資料服務不會自動公開包含在資料模型中的物件， 必須由服務本身明確公開。 如需詳細資訊，請參閱[設定資料服務](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)。  
  
9. 按一下**完成**以完成精靈。  
  
     這樣會根據特定資料庫建立預設資料模型。 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 可讓您自訂資料模型。 如需詳細資訊，請參閱[工作](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb)。  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a>若要使用新的資料模型建立資料服務  
  
1.  在 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 中，開啟代表該資料模型的 .edmx 檔案。  
  
2.  在**模型瀏覽器**、 以滑鼠右鍵按一下模型、 按一下**屬性**，然後記下實體容器的名稱。  
  
3.  在**方案總管 中**，以滑鼠右鍵按一下名稱您[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]專案，然後再按一下**加入新項目**。  
  
4.  在**加入新項目**對話方塊中，選取**WCF 資料服務**。  
  
5.  提供服務的名稱，然後按一下 **確定**。  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 會針對新的服務建立 XML 標記和程式碼檔案。 根據預設，程式碼編輯器視窗隨即開啟。  
  
6.  在資料服務的程式碼中，以繼承自 `/* TODO: put your data source class name here */` 類別且為資料模型實體容器 (您已在步驟 2 中記下該容器) 的型別，取代定義資料服務之類別定義中的 <xref:System.Data.Objects.ObjectContext> 註解。  
  
7.  在資料服務的程式碼中，啟用已授權的用戶端以存取資料服務所公開的實體集。 如需詳細資訊，請參閱[建立資料服務](../../../../docs/framework/data/wcf/creating-the-data-service.md)。  
  
8.  若要使用網頁瀏覽器測試 Northwind.svc 資料服務，請遵循本主題中的指示[從網頁瀏覽器存取服務](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)。  
  
## <a name="see-also"></a>另請參閱  
 [定義 WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [資料服務提供者](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [如何： 建立資料服務，使用反映提供者](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [如何： 建立使用 LINQ to SQL 資料來源的資料服務](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
