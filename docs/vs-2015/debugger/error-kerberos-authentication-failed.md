---
title: 'Chyba: Ověřování protokolu Kerberos se nezdařilo. | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c18053f9-9074-4bc3-a8bf-13e4acbea921
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b5e85bc7a5bac87692448aab393056fa1db5edbd
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60083995"
---
# <a name="error-kerberos-authentication-failed"></a>Chyba: Ověřování protokolu Kerberos se nezdařilo.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při pokusu provést vzdálené ladění, může se zobrazit následující chybová zpráva:  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Kerberos auythentication failed.  
```  
  
 K této chybě dochází, když Visual Studio Remote Debugging Monitor běží pod účtem místního systému nebo síťové služby. V rámci jednoho z těchto účtů musí vzdálený ladicí program navázat připojení ověřování protokol Kerberos ke komunikaci zpět na hostitelském počítači ladicího programu sady Visual Studio.  
  
 Ověřování pomocí protokolu Kerberos není k dispozici za těchto podmínek:  
  
- Cílový počítač nebo hostitelský počítač ladicí program je v pracovní skupině místo domény  
  
   \- nebo –  
  
- Na řadiči domény se zakázalo protokolu Kerberos.  
  
  Pokud ověřování protokolu Kerberos není k dispozici, změňte účet, který se používá ke spuštění Visual Studio Remote Debugging Monitor. Tento postup, naleznete v tématu [Chyba: Služba Visual Studio Remote Debugger na cílovém počítači se nemůže připojit zpět k tomuto počítači](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).  
  
  Pokud oba počítače jsou připojené ke stejné doméně a zachovat si tuto zprávu, ověřte, že DNS v cílovém počítači správně překládá název hostitelského počítače ladicího programu. Viz následující postup.  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>Chcete-li ověřit, že DNS v cílovém počítači správně překládá název hostitelského počítače ladicího programu  
  
1. V cílovém počítači, otevřete **Start** nabídky, přejděte k **Příslušenství** a potom klikněte na tlačítko **příkazového řádku**.  
  
2. V **příkazového řádku** okno, zadejte:  
  
    ```  
    ping <debugger_host_computer_name>  
    ```  
  
3. První řádek `ping` odpověď ukazuje úplný název počítače a IP adresu vrácenou funkcí DNS pro zadaný počítač.  
  
4. Otevřete na hostitelském počítači ladicího programu **příkazového řádku** okna a spusťte `ipconfig`.  
  
5. Porovnejte hodnoty IP adres.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)
