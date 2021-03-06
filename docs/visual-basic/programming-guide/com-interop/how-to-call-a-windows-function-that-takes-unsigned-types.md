---
title: "如何：呼叫使用不帶正負號類型的 Windows 函式 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5b1a306ba694d4bbfc4719fc728112964b1ce40f
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>如何：呼叫使用不帶正負號類型的 Windows 函式 (Visual Basic)
如果您正在耗用類別、 模組或具有不帶正負號的整數類型的成員的結構，您可以存取這些成員與[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>若要呼叫 Windows 函式採用不帶正負號的類型  
  
1.  使用[Declare 陳述式](../../../visual-basic/language-reference/statements/declare-statement.md)告訴[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]哪一個程式庫會保存函式、 其名稱為該文件庫中，其呼叫的順序為何，以及如何將字串轉換呼叫它時。  
  
2.  在`Declare`陳述式中，使用`UInteger`， `ULong`， `UShort`，或`Byte`視需要針對每個參數具有不帶正負號的類型。  
  
3.  若要尋找的名稱和值的常數，它會使用呼叫 Windows 函式，請參閱文件。 其中許多 WinUser.h 檔案中定義。  
  
4.  宣告在程式碼中必要的常數。 許多 Windows 常數 32 位元不帶正負號的值，而且您應該將這些宣告`As``UInteger`。  
  
5.  以一般方式呼叫此函式。 下列範例會呼叫 Windows 函式`MessageBox`，其可接受不帶正負號的整數引數。  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     您可以測試函式`messageThroughWindows`為下列程式碼。  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  `UInteger`， `ULong`， `UShort`，和`SByte`資料類型不屬於[語言獨立性以及與語言無關的元件](../../../../docs/standard/language-independence-and-language-independent-components.md)（cls） 標準，所以符合 CLS 標準的程式碼無法使用的元件，使用它們。  
  
    > [!IMPORTANT]
    >  呼叫 unmanaged 程式碼，例如 Windows 應用程式開發介面 (API)，會公開您的程式碼有潛在的安全性風險。  
  
    > [!IMPORTANT]
    >  呼叫 Windows API 需要 unmanaged 程式碼權限，這可能會影響在部分信任情況下執行。 如需詳細資訊，請參閱<xref:System.Security.Permissions.SecurityPermission>和[程式碼存取權限](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675)。  
  
## <a name="see-also"></a>另請參閱  
 [資料類型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Integer 資料類型](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [UInteger 資料類型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [Declare 陳述式](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [逐步解說：呼叫 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
