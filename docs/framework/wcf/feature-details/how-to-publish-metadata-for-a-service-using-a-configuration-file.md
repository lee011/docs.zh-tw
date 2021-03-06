---
title: "HOW TO：使用組態檔發行服務的中繼資料"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 16e278fd0eb227ddd382157d38c7370e604c35d3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a>HOW TO：使用組態檔發行服務的中繼資料
在兩個示範如何發行 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服務中繼資料的 HOW TO 主題中，這是其中一個。 有兩種方法可以指定服務發行中繼資料的方式，分別是使用組態檔和使用程式碼。 本主題說明如何使用組態檔發行服務的中繼資料。  
  
> [!CAUTION]
>  本主題將示範以不安全的方法發行中繼資料。 任何用戶端都能從服務擷取中繼資料。 如果您需要您的服務發行中繼資料以安全的方式，請參閱[自訂安全中繼資料端點](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)。  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]發行中繼資料中的程式碼，請參閱[How to： 服務使用程式碼發行中繼資料](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)。 發行中繼資料可讓用戶端透過 WS-Transfer GET 要求，或是透過使用 `?wsdl` 查詢字串的 HTTP/GET 要求來擷取中繼資料。 若要確定程式碼可以正常運作，請建立基本的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服務。 為了方便使用，下列程式碼提供基本的自我裝載服務。  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
 此服務是透過組態檔設定的自我裝載服務。 下列組態檔將做為起點。  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Metadata.Example.SimpleService">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
      </service>  
    </services>  
    <behaviors>  
  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a>若要使用應用程式組態檔來發行 WCF 服務的中繼資料  
  
1.  在 App.config 檔案中，於結尾的 `</services>` 項目之後，建立 `<behaviors>` 項目。  
  
  
  
2.  在 `<behaviors>` 項目中，新增 `<serviceBehaviors>` 項目。  
  
  
  
3.  將 `<behavior>` 項目新增至 `<serviceBehaviors>` 項目，並指定 `name` 項目的  `<behavior>` 屬性值。  
  
  
  
4.  將 `<serviceMetadata>` 項目加入至 `<behavior>` 項目。 將 `httpGetEnabled` 屬性設為 `true` 並將 `policyVersion` 屬性設為 Policy15。 `httpGetEnabled` 允許服務回應由 HTTP GET 要求所提出的中繼資料要求。 `policyVersion` 會在產生中繼資料時，要求服務符合 WS-Policy 1.5 規定。  
  
  
  
5.  將 `behaviorConfiguration` 屬性加入至 `<service>` 項目，並指定 `name` 項目的 `<behavior>` 屬性 (於步驟 1 中加入)，如下列程式碼範例所示。  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
        ...  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy15" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
6.  加入一個或多個 `<endpoint>` 項目，並將合約設為 `IMetadataExchange`，如下列程式碼範例所示。  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    ```  
  
7.  針對上一個步驟中加入的中繼資料端點，將 `binding` 屬性設為下列其中一項：  
  
    -   `mexHttpBinding` (適用 HTTP 發行)。  
  
    -   `mexHttpsBinding` (適用 HTTPS 發行)。  
  
    -   `mexNamedPipeBinding` (適用具名管道發行)。  
  
    -   `mexTcpBinding` (適用 TCP 發行)。  
  
8.  針對上一個步驟中加入的中繼資料端點，將位址設為與下列項目相等：  
  
    -   如果基底位址與中繼資料繫結相同，則設定空字串以使用主應用程式的基底位址做為發行點。  
  
    -   如果主應用程式具有基底位址，則設為相對位址。  
  
    -   絕對位址。  
  
9. 建置並執行主控台應用程式。  
  
10. 使用 Internet Explorer 瀏覽至服務的基底位址 (此範例中為 http://localhost:8001/MetadataSample)，然後確認已開啟中繼資料發行功能。 如果沒有的話，結果頁面上方應該會顯示：「為此服務發行的中繼資料目前停用」。  
  
### <a name="to-use-default-endpoints"></a>若要使用預設端點  
  
1.  若要對使用預設端點的服務設定中繼資料，請在組態檔中指定 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> (如上一個範例所示)，但不要指定任何端點。 組態檔如下所示。  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="SimpleServiceBehavior">  
              <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     因為服務有 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 且 `httpGetEnabled` 設為 `true`，服務已經啟用發行中繼資料，但是因為沒有明確加入端點，所以執行階段加入預設端點。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]預設端點、 繫結和行為，請參閱[簡化的組態](../../../../docs/framework/wcf/simplified-configuration.md)和[簡化 WCF 服務的組態](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。  
  
## <a name="example"></a>範例  
 下列程式碼範例顯示基本 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服務的實作，以及發行服務中繼資料的組態檔。  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [如何：於受管理的應用程式中裝載 WCF 服務](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [自我裝載](../../../../docs/framework/wcf/samples/self-host.md)  
 [中繼資料架構概觀](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [使用中繼資料](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [如何： 使用程式碼的服務發行中繼資料](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
