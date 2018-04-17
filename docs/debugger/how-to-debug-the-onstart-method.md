---
title: 'Postupy: ladění metody OnStart | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 369cebf83f1d3dc54472b4c912b4196427684a38
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-the-onstart-method"></a>Postupy: Ladění metody OnStart
Služby systému Windows můžete ladit spouštění služby a připojení ladicího programu pro proces služby. Další informace najdete v tématu [postupy: ladění aplikace služby systému Windows](/dotnet/framework/windows-services/how-to-debug-windows-service-applications). Však k ladění <xref:System.ServiceProcess.ServiceBase.OnStart%2A?displayProperty=fullName> metoda služby systému Windows, musíte spustit ladicí program z uvnitř metody.  
  
1.  Přidejte volání <xref:System.Diagnostics.Debugger.Launch%2A> na začátku `OnStart()`metoda.  
  
    ```csharp  
    protected override void OnStart(string[] args)  
    {  
        System.Diagnostics.Debugger.Launch();  
     }  
    ```  
  
2.  Spusťte službu (můžete použít `net start`, nebo jej spustit v **služby** okno).  
  
     Zobrazí dialogové okno takto:  
  
     ![OnStartDebug](../debugger/media/onstartdebug.png "OnStartDebug")  
  
3.  Vyberte **Ano, ladění \<název služby >.**  
  
4.  V okně ladicí program JIT vyberte verzi Visual Studia, kterou chcete použít pro ladění.  
  
     ![JustInTimeDebugger](../debugger/media/justintimedebugger.png "JustInTimeDebugger")  
  
5.  Je zastaveno novou instanci třídy sady Visual Studio spustí a provádění `Debugger.Launch()` metoda.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)