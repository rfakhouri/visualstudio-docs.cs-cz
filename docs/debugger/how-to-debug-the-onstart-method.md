---
title: 'Postupy: Ladění metody OnStart | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- OnStart method
- debugging [Visual Studio], Windows services
- debugging managed code, OnStart method
- debugging Windows Services applications, OnStart method
- Windows Service applications, debugging
ms.assetid: b06b5d65-424b-490f-bf58-97583cd7006a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2cfd6153389bbfe9cbbd36f33f6a2e4384509297
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227058"
---
# <a name="how-to-debug-the-onstart-method"></a>Postupy: Ladění metody OnStart
Služba Windows můžete ladit spuštění služby a připojování ladicího programu k procesu služby. Další informace najdete v tématu [jak: Ladění aplikace služby Windows](/dotnet/framework/windows-services/how-to-debug-windows-service-applications). Ale chcete-li ladit <xref:System.ServiceProcess.ServiceBase.OnStart%2A?displayProperty=fullName> metody služby Windows, musíte spustit ladicí program z uvnitř metody.

1. Přidejte volání do <xref:System.Diagnostics.Debugger.Launch%2A> na začátku `OnStart()`metody.

    ```csharp
    protected override void OnStart(string[] args)
    {
        System.Diagnostics.Debugger.Launch();
    }
    ```

2. Spusťte službu (můžete použít `net start`, nebo jej spustit v **služby** okno).

    Zobrazí se dialogové okno vypadat asi takto:

    ![OnStartDebug](../debugger/media/onstartdebug.png "OnStartDebug")

3. Vyberte **Ano, ladit \<název služby >.**

4. V okně ladicího programu za běhu vyberte verzi sady Visual Studio, kterou chcete použít pro ladění.

    ![JustInTimeDebugger](../debugger/media/justintimedebugger.png "JustInTimeDebugger")

5. Novou instanci třídy spustí aplikace Visual Studio a provedení je zastaveno `Debugger.Launch()` metody.

## <a name="see-also"></a>Viz také
[Zabezpečení ladicího programu](../debugger/debugger-security.md)  
[Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
