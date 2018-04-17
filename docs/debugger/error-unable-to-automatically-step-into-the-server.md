---
title: 'Chyba: Nelze automatické krokování s vnořením serveru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, notification error
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7fb8d7eeacf8ab4a4eccf94574e0b3911019db9e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Chyba: Automatické krokování s vnořením do serveru se nezdařilo.
Chyba čtení:  
  
 Nelze automaticky krok do serveru. Ladicí program nebyl upozorněn předtím, než se spustí vzdálené procedury  
  
 K této chybě může dojít, když se pokoušíte krok do webové služby (viz [Zanoříte se do XML webové služby](http://msdn.microsoft.com/en-us/8e67de38-bf5f-41cc-a457-1b88ce63d764)). Dochází vždy, když [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] není správně nastaven.  
  
 Možné příčiny jsou:  
  
-   Souboru web.config pro vaše [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace není nastavena na hodnotu "true" debug (viz [režim ladění v aplikacích ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
-   Verzi [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] byl nainstalován po instalaci sady Visual Studio. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] by měly být nainstalovány před Visual Studio. Chcete-li tento problém vyřešit, použijte Windows **ovládací panely > programy a funkce** k opravě instalace sady Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)