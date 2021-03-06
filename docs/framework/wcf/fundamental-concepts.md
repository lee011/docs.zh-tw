---
title: "Windows Communication Foundation 的主要概念"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], concepts
- concepts [WCF]
- fundamentals [WCF]
- Windows Communication Foundation [WCF], concepts
ms.assetid: 3e7e0afd-7913-499d-bafb-eac7caacbc7a
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e44ded58e7c48fae281030b5757d0d891d5600e6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="fundamental-windows-communication-foundation-concepts"></a>Windows Communication Foundation 的主要概念
本文件提供 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 架構的高階檢視， 以說明重要概念，以及如何搭配運用這些概念。 如需教學課程建立的簡單版本[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服務與用戶端，請參閱[入門教學課程](../../../docs/framework/wcf/getting-started-tutorial.md)。 若要了解[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]程式設計，請參閱[基本 WCF 程式設計](../../../docs/framework/wcf/basic-wcf-programming.md)。  
  
## <a name="wcf-fundamentals"></a>WCF 基本概念  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 為執行階段及一組 API，用來建立在服務和用戶端間傳送訊息的系統。 相同的基礎結構和 API 可用來在同一個電腦系統或位於其他電腦且透過網際網路存取的系統上，建立與其他應用程式通訊的應用程式。  
  
### <a name="messaging-and-endpoints"></a>傳訊和端點  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 是以訊息通訊的概念為基礎，而且任何可模型化為訊息的項目 (例如 HTTP 要求或訊息佇列 (亦稱為 MSMQ) 訊息) 都能在程式設計模型中以制式方式表示。 如此一來，不同傳輸機制上就可以有統一的 API。  
  
 此模型區別*用戶端*，這是起始通訊，應用程式和*服務*，這是等候用戶端與其通訊並回應的應用程式通訊。 單一應用程式可以同時做為用戶端和服務。 如需範例，請參閱[雙工服務](../../../docs/framework/wcf/feature-details/duplex-services.md)和[對等網路](../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。  
  
 訊息會在端點間傳送。 *端點*傳送或接收訊息的位置 （或兩者），而且會定義所有訊息交換所需的資訊。 服務會公開一或多個應用程式端點 (以及零或多個基礎結構端點)，而用戶端則會產生與其中一個服務端點相容的端點。  
  
 *端點*描述以標準為基礎的方式應該傳送訊息的位置、 方式應該傳送，以及訊息的顯示方式。 服務可以公開此資訊做為用戶端可以處理以產生適當的中繼資料[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]用戶端和通訊*堆疊*。  
  
### <a name="communication-protocols"></a>通訊協定  
 其中一個所需的通訊堆疊的項目是*傳輸通訊協定*。 使用通用傳輸 (例如 HTTP 和 TCP)，就可以在內部網路和網際網路上傳送訊息。 另外，當中也包括了其他傳輸，以支援與訊息佇列應用程式和對等網路 mesh 上的節點通訊。 使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 的內建擴充點，可以加入其他傳輸機制。  
  
 通訊堆疊中的另一個必要元素是編碼方式，這會指定要以何種方式格式化任何給定訊息。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 提供下列編碼方式：  
  
-   文字編碼方式，互通的編碼方式。  
  
-   訊息傳輸最佳化機制 (MTOM) 編碼方式，可在服務上有效傳送或接收無結構二進位資料的互通方式。  
  
-   二進位編碼方式，可有效進行傳輸。  
  
 使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 的內建擴充點，可以加入其他編碼機制 (例如，壓縮編碼方式)。  
  
### <a name="message-patterns"></a>訊息模式  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 支援數種傳訊模式，包括要求-回覆、單向和雙工通訊。 不同傳輸支援不同傳訊模式，因此會影響所支援的互動類型。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] API 和執行階段也有助於安全、可靠地傳送訊息。  
  
## <a name="wcf-terms"></a>WCF 詞彙  
 下列是 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 文件中使用的其他概念和詞彙。  
  
 訊息  
 這是獨立的資料單位，可由數個部分組成，其中包括本文和標頭。  
  
 服務  
 這是公開一個或多個端點的建構，其中每個端點會公開一項或多項服務作業。  
  
 endpoint  
 這是訊息傳送或接收 (或兩者) 所在位置的建構。 它包含一個定義可以傳送訊息的位置 (位址)、描述如何傳送訊息的通訊機制規格 (繫結)，以及該位置 (描述可以傳送訊息的位置) 上一組可傳送或接收 (或兩者) 之訊息的定義 (服務合約)。  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服務會對外界公開為端點集合。  
  
 Application Endpoint - 應用程式端點  
 由應用程式公開的端點，會對應至應用程式所實作的服務合約。  
  
 基礎結構端點  
 由基礎結構公開的端點，可提升服務所需或提供、但與服務合約無關之功能的效率。 例如，服務可能具有提供中繼資料資訊的基礎結構端點。  
  
 address  
 指定接收訊息的位置， 可指定做為統一資源識別元 (URI)。 URI 結構描述部分會指定用來到達位址的傳輸機制，例如 HTTP 和 TCP。 URI 的階層式部分包含唯一位置，其格式取決於傳輸機制。  
  
 端點位址可讓您為服務中的每個端點建立唯一的端點位址，或在特定狀況下讓各端點共用位址。 下列範例示範將 HTTPS 通訊協定與非預設連接埠搭配使用的位址：  
  
```  
HTTPS://cohowinery:8005/ServiceModelSamples/CalculatorService  
```  
  
 繫結  
 定義端點如何與外界通訊。 它是由一組稱為繫結項目的元件所建構，這些元件會彼此「堆疊」，以建立通訊基礎結構。 繫結至少會定義傳輸 (例如 HTTP 或 TCP) 和使用的編碼方式 (例如文字或二進位)。 繫結可以包含用來指定像是安全性機制 (用來保護訊息) 等詳細資料的繫結項目，或端點所使用的訊息模式。 如需詳細資訊，請參閱[設定 Services](../../../docs/framework/wcf/configuring-services.md)。  
  
 Binding Element - 繫結項目  
 表示一項特定的繫結，例如傳輸、編碼方式、基礎結構層級通訊協定的實作 (例如 WS-ReliableMessaging)，或通訊堆疊的任何其他元件。  
  
 行為  
 此元件可控制服務、端點、特定作業或用戶端的各種執行階段層面。 行為是根據範圍來分組：通用行為會影響全域所有的端點、服務行為只會影響服務相關的層面、端點行為只會影響端點相關的屬性，而作業層級行為會影響特定作業。 例如，其中一個服務行為是節流，這會在過多訊息威脅造成服務處理功能過度負荷時，指定服務的回應方式。 另一方面，端點行為只會控制與端點相關的層面，例如尋找安全性認證的方式和位置。  
  
 System-provided Bindings - 系統提供的繫結  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 包含一些系統提供的繫結。 這些繫結是已針對特定案例最佳化的繫結項目集合。 例如，<xref:System.ServiceModel.WSHttpBinding> 是設計用來與實作各種 WS-* 規格的服務增加互通性 (Interoperability)。 這些預先定義的繫結只會提供可正確套用至特定案例的選項，因此能夠節省時間。 如果預先定義的繫結不符合您的需求，請建立自訂繫結。  
  
 組態和程式碼  
 應用程式可以透過程式碼、組態或兩者的組合來控制。 組態的優點是，在撰寫程式碼之後，允許開發人員以外的其他人 (例如，網路系統管理員) 設定用戶端和服務參數，而不需要重新編譯。 組態不僅可讓您設定如端點位址的值，還能讓您加入端點、繫結和行為，取得進一步的控制。 程式碼可讓開發人員嚴格控制服務或用戶端的所有元件，而且透過組態所做的任何設定都可以使用程式碼進行檢查，並在必要時加以覆寫。  
  
 服務作業  
 在服務的程式碼中定義的程序，以實作某項作業的功能。 這項作業會向用戶端公開為 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 用戶端上的方法。 此方法可傳回值並能接受選擇性數目的引數，或者不接受引數且不傳回任何回應。 例如，作用為簡單 "Hello" 的作業，可以做為用戶端出席狀態的通知，並且用來開始一系列的作業。  
  
 Service Contract - 服務合約  
 將多個相關作業結合成單一功能單位。 合約可以定義服務層級的設定，例如服務的命名空間、對應的回呼合約和其他類似的設定。 在大部分的情況下，合約是以您選擇的程式語言建立介面，並且將 <xref:System.ServiceModel.ServiceContractAttribute> 屬性套用至介面的方式來定義。 藉由實作介面，即可產生實際服務程式碼。  
  
 Operation Contract - 作業合約  
 作業合約會定義作業的參數和傳回型別。 當建立會定義服務合約的介面時，您可以將 <xref:System.ServiceModel.OperationContractAttribute> 屬性套用至屬於合約一部分的每個方法定義，來表示作業合約。 作業可以模式化成接受單一訊息且傳回單一訊息，或者接受一組型別且傳回一個型別。 在後者中，系統會判斷該作業需要交換之訊息的格式。  
  
 訊息合約  
 描述訊息的格式。 例如，它會宣告訊息項目應放在標頭或本文、應該將哪個層級的安全性套用至哪些訊息的項目等等。  
  
 Fault Contract - 錯誤合約  
 可以與服務作業產生關聯，來表示可以傳回至呼叫者的錯誤。 作業可以有零或多個相關聯的錯誤。 這些錯誤屬於 SOAP 錯誤，這種錯誤會模式化為程式設計模型中的例外狀況。  
  
 資料合約  
 服務所使用的資料型別其中繼資料內的描述。 這讓其他項目得以與服務相互溝通。 資料型別可以用於訊息的任何部分，例如做為參數或傳回型別。 如果服務只使用簡單型別，就不需要明確使用資料合約。  
  
 裝載  
 服務必須裝載於某些處理序。 A*主機*是控制服務存留期的應用程式。 服務可以是自我裝載，或由現有裝載處理序管理。  
  
 自我裝載的服務  
 這種服務是在開發人員建立的處理序應用程式中執行。 開發人員會控制服務存留期、設定服務屬性、開啟服務 (這會將服務設定為接聽模式) 以及關閉服務。  
  
 裝載處理序  
 一種應用程式，設計用來裝載服務。 其中包括網際網路資訊服務 (IIS)、Windows Activation Services (WAS) 和 Windows 服務。 在這些裝載案例中，主機會控制服務的存留期。 例如，您可以使用 IIS 來設定包含服務組件和組態檔的虛擬目錄。 當接收到訊息時，IIS 就會啟動服務並控制它的存留期。  
  
 執行個體  
 服務具有執行個體模型 (Instancing Model)。 執行個體模型有三種：「單一」表示單一 CLR 物件會服務所有用戶端，「每一呼叫」表示會建立新 CLR 物件來處理每個用戶端呼叫，而「每一工作階段」表示會建立一組 CLR 物件，每個物件各代表單一個別工作階段。 執行個體模型的選擇取決於應用程式需求和預期的服務使用模式。  
  
 Client Application - 用戶端應用程式  
 這是與一個或多個端點交換訊息的程式。 用戶端應用程式首先會建立 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 用戶端的執行個體，並呼叫 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 用戶端的方法。 值得注意的是，單一應用程式可以同時是用戶端和服務。  
  
 Channel - 通道  
 這是繫結項目的實體實作。 繫結表示組態，通道則是與該組態相關聯的實作。 因此，每個繫結項目都有相關聯的通道。 通道會彼此堆疊，以建立繫結的實體實作，也就是「通道堆疊」。  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 用戶端  
 一種用戶端應用程式建構，會將服務作業公開為方法 (在您所選的 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 程式語言中，例如 Visual Basic 或 Visual C#)。 任何應用程式都可以裝載 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 用戶端，包括裝載服務的應用程式， 因此，您可以建立包含其他服務之 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 用戶端的服務。  
  
 A[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]用戶端可以使用自動產生[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)和它指向發行中繼資料執行中服務。  
  
 中繼資料  
 在服務中描述服務的特性，外部實體必須了解這些服務特性，才能與此服務通訊。 中繼資料可供[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)產生[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]用戶端和用戶端應用程式可以用來與服務互動的伴隨組態。  
  
 服務公開的中繼資料包括 XML 結構描述文件 (定義服務的資料合約) 和 WSDL 文件 (描述服務的方法)。  
  
 啟用時，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 會藉由檢查服務及其端點，自動產生服務的中繼資料。 若要從服務發行中繼資料，您必須明確啟用中繼資料行為。  
  
 安全性  
 這在 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中包括了機密性 (加密訊息以防竊聽)、完整性 (偵測訊息是否遭竄改的方法)、驗證 (驗證伺服器和用戶端的方法) 以及授權 (控制對資源的存取)。 運用現有的安全性機制 (例如 TLS over HTTP，也稱為 HTTPS)，或實作一或多個不同的 WS-* 安全性規格，都能提供這些功能。  
  
 傳輸安全性模式  
 指定由傳輸層機制 (例如 HTTPS) 提供機密性、完整性和驗證。 在使用如 HTTPS 的傳輸時，這個模式的優點在於效能會更有效率，而且易於理解 (因為普遍使用在網際網路上)。 缺點是，這種類型的安全性是個別套用在通訊路徑上的每個躍點，因此通訊容易受到「攔截式」攻擊。  
  
 訊息安全性模式  
 指定安全性會提供實作一或多個安全性規格，例如規格名為[Web 服務安全性： SOAP 訊息安全性](http://go.microsoft.com/fwlink/?LinkId=94684)。 每個訊息都會包含必要機制，以便在訊息傳輸期間提供安全性，並讓接收者可以偵測竄改及解密訊息。 就這個意義而言，安全性是封裝在每個訊息內，可以在多個躍點間提供端對端安全性。 因為安全性資訊成為訊息的一部分，所以也可以將多種認證包含在訊息 (這些指*宣告*)。 這個方法的優點是，訊息可以透過任何傳輸安全地傳送，包括來源和目的地之間的多個傳輸。 缺點是使用的密碼編譯機制很複雜，因此會影響效能。  
  
 使用訊息認證的傳輸安全性模式  
 指定使用傳輸層來提供訊息的機密性、驗證和完整性，而每個訊息都包含訊息接收者所需的多個認證 (宣告)。  
  
 WS-*  
 一組發展中 Web 服務 (WS) 規格的縮寫，例如 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中所實作的 WS-Security 與 WS-ReliableMessaging 等等。  
  
## <a name="see-also"></a>另請參閱  
 [什麼是 Windows Communication Foundation](../../../docs/framework/wcf/whats-wcf.md)  
 [Windows Communication Foundation 架構](../../../docs/framework/wcf/architecture.md)  
 [安全性架構](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)
