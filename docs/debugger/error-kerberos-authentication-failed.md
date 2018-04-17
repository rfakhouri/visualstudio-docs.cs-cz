---
title: ': Chyba během ověřování protokolem Kerberos | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec544d1d5930990dce1ca30d84a21e2e1517f0d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-kerberos-authentication-failed"></a>Chyba: Ověření protokolem Kerberos se nezdařilo.
Když se pokusíte provést vzdálené ladění, může získat se následující chybová zpráva:  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Kerberos authentication failed.  
```  
  
 K této chybě dojde, když Visual Studio Remote Debugging Monitor běží pod účtem Local System nebo síťové služby. V rámci jednoho z těchto účtů musí vzdáleného ladicího programu navázat připojení ověřování protokolu Kerberos pro komunikaci zpět k hostitelskému počítači ladicího programu sady Visual Studio.  
  
 Ověřování pomocí protokolu Kerberos není k dispozici v těchto podmínkách:  
  
-   Cílový počítač nebo hostitelský počítač ladicí program je v pracovní skupině, namísto domény  
  
     \- nebo –  
  
-   Byla zakázána protokolu Kerberos na řadiči domény.  
  
 Pokud ověřování protokolu Kerberos není k dispozici, změňte účet, který se používá ke spuštění Visual Studio Remote Debugging Monitor. Postup najdete v tématu [chybě: Visual Studio vzdáleného ladicího programu service v cílovém počítači se nemůže připojit zpět k tomuto počítači](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).  
  
 Pokud jsou oba počítače připojeny ke stejné doméně a stále se vám tato zpráva, ověřte, že DNS na cílovém počítači správně překládá název hostitelského počítače ladicí program. Přečtěte si následující postup.  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>Chcete-li ověřit, že DNS na cílovém počítači je správně řešení název hostitelského počítače ladicí program  
  
1.  Otevřete na cílovém počítači, **spustit** nabídky, přejděte na příkaz **Příslušenství** a pak klikněte na **příkazového řádku**.  
  
2.  V **příkazového řádku** okno, zadejte:  
  
    ```  
    ping <debugger_host_computer_name>  
    ```  
  
3.  První řádek `ping` odpovědi zobrazuje úplný název počítače a IP adresu vrácenou DNS pro zadaný počítač.  
  
4.  Otevřete na hostitelském počítači ladicí program **příkazového řádku** okno a spusťte `ipconfig`.  
  
5.  Porovnejte hodnoty adres IP.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)