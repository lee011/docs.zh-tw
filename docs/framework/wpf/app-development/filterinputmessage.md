---
title: FilterInputMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b3a0e58c7485d46f004db7ea52215be60340b68
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2017
---
# <a name="filterinputmessage"></a>FilterInputMessage
除非傳回 E_NOTIMPL，否則每當收到訊息時，都會由 PresentationHost.exe 呼叫。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a>參數  
 `pMsg`  
  
 [in] 傳送給正在取得未經處理輸入之視窗的 WM_INPUT 訊息。  
  
## <a name="property-valuereturn-value"></a>屬性值/傳回值  
 HRESULT:  
  
 S_OK - 篩選未處理訊息，可能會進一步處理。  
  
 S_FALSE - 篩選已處理此訊息，應該不會進一步處理。  
  
 E_NOTIMPL – 如果此值會傳回， [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)不會再次呼叫。 這可能是從只想要提供自訂進度的主應用程式傳回，而 PresentationHost.exe 的錯誤使用者介面並不想要被從 PresentationHost.exe 轉送未經處理的輸入訊息。  
  
## <a name="remarks"></a>備註  
 PresentationHost.exe 是各種未經處理輸入裝置 (包括鍵盤、滑鼠及遙控器) 的目標。 有時候，主應用程式中的行為取決於由 PresentationHost.exe 使用的輸入。 例如，主應用程式可能取決於接收特定輸入訊息來判斷是否要顯示特定使用者介面項目。  
  
 若要允許主應用程式接收必要的輸入的訊息，以提供這些行為，PresentationHost.exe 適當原始輸入將訊息轉寄至裝載的應用程式藉由呼叫[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)。  
  
 裝載的應用程式接收未經處理輸入的訊息向原始輸入裝置 （人性化介面裝置） 所傳回的集合[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)。  
  
## <a name="see-also"></a>另請參閱  
 [澗通知](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
