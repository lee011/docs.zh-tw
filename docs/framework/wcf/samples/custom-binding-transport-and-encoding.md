---
title: "自訂繫結傳輸和編碼"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e4e26e332cc67fc462c703c502594a8a36758501
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2017
---
# <a name="custom-binding-transport-and-encoding"></a>自訂繫結傳輸和編碼
自訂繫結由經過排序的獨立繫結項目清單所定義。 這個範例會示範如何使用各種傳輸與訊息編碼項目來設定自訂繫結。  
  
> [!NOTE]
>  此範例的安裝程序與建置指示位於本主題的結尾。  
  
 這個範例根據[自我裝載](../../../../docs/framework/wcf/samples/self-host.md)，和已修改成支援 HTTP、 TCP 及具名管道傳輸自訂繫結的三個端點的設定。 用戶端組態已採用類似方式加以修改，因此用戶端程式碼已變更成與這三個端點中的每個端點進行通訊。  
  
 此範例會示範如何設定支援特定傳輸與訊息編碼的自訂繫結。 這是設定 `binding` 項目的傳輸與訊息編碼完成的。 繫結項目的順序很重要定義自訂繫結，因為每個表示通道堆疊中的圖層中 (請參閱[自訂繫結](../../../../docs/framework/wcf/extending/custom-bindings.md))。 這個範例會設定三個自訂繫結：使用文字編碼的 HTTP 傳輸、使用文字編碼的 TCP 傳輸，以及使用二進位編碼的 NamedPipe 傳輸。  
  
 服務組態會定義如下所示的自訂繫結：  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding   
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 當您執行範例時，作業要求和回應都會顯示在服務與用戶端主控台視窗中。 用戶端會與這三個端點個別進行通訊，步驟是先存取 HTTP，接著存取 TCP，最後再存取 NamedPipe。 在每個主控台視窗中按下 ENTER 鍵，即可關閉服務與用戶端。  
  
 `namedPipeTransport` 繫結不支援電腦對電腦的作業。 這個繫結只用於相同電腦上的通訊。 因此，如果是在跨電腦案例中執行此範例，請將用戶端程式碼檔中的下列程式碼行標記為註解：  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
>  如果您使用 Svcutil.exe 重新產生這個範例的組態，請務必修改用戶端組態中的端點名稱，以符合用戶端程式碼。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>若要安裝、建置及執行範例  
  
1.  請確定您已執行[的 Windows Communication Foundation 範例的單次安裝程序](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  若要建置方案的 C#、 c + + 或 Visual BASIC.NET 版本，請依照中的指示[建置 Windows Communication Foundation 範例](../../../../docs/framework/wcf/samples/building-the-samples.md)。  
  
3.  若要在單一或跨電腦組態中執行範例時，請依照中的指示[執行 Windows Communication Foundation 範例](../../../../docs/framework/wcf/samples/running-the-samples.md)。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4  (適用於 .NET Framework 4 的 Windows Communication Foundation (WCF) 與 Windows Workflow Foundation (WF) 範例)](http://go.microsoft.com/fwlink/?LinkId=150780) ，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。 此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
  
## <a name="see-also"></a>另請參閱
