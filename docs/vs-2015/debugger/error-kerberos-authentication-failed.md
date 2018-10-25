---
title: 'Chyba: Ověřování protokolem Kerberos se nezdařilo | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c18053f9-9074-4bc3-a8bf-13e4acbea921
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd142d08574d93053ce8a0ebd8b4ca27ed4f0790
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49815049"
---
# <a name="error-kerberos-authentication-failed"></a>Chyba: Ověření protokolem Kerberos se nezdařilo.
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
  
  Pokud ověřování protokolu Kerberos není k dispozici, změňte účet, který se používá ke spuštění Visual Studio Remote Debugging Monitor. Tento postup, naleznete v tématu [Chyba: služba The Visual Studio Remote Debugger na cílovém počítači se nemůže připojit zpět k tomuto počítači](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).  
  
  Pokud oba počítače jsou připojené ke stejné doméně a zachovat si tuto zprávu, ověřte, že DNS v cílovém počítači správně překládá název hostitelského počítače ladicího programu. Viz následující postup.  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>Chcete-li ověřit, že DNS v cílovém počítači správně překládá název hostitelského počítače ladicího programu  
  
1.  V cílovém počítači, otevřete **Start** nabídky, přejděte k **Příslušenství** a potom klikněte na tlačítko **příkazového řádku**.  
  
2.  V **příkazového řádku** okno, zadejte:  
  
    ```  
    ping <debugger_host_computer_name>  
    ```  
  
3.  První řádek `ping` odpověď ukazuje úplný název počítače a IP adresu vrácenou funkcí DNS pro zadaný počítač.  
  
4.  Otevřete na hostitelském počítači ladicího programu **příkazového řádku** okna a spusťte `ipconfig`.  
  
5.  Porovnejte hodnoty IP adres.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)



