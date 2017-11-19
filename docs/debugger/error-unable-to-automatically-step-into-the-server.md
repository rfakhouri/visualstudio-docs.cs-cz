---
title: "Chyba: Nelze automatické krokování s vnořením serveru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.causality_no_server_response
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords: remote debugging, notification error
ms.assetid: 9a370ccc-d358-429c-b285-9b6c0649bc68
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63e8d73b9df650a1d98b0c9f080c7b32cc0a324e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Chyba: Automatické krokování s vnořením do serveru se nezdařilo.
Chyba čtení:  
  
 Nelze automaticky krok do serveru. Ladicí program nebyl upozorněn předtím, než se spustí vzdálené procedury  
  
 K této chybě může dojít, když se pokoušíte krok do webové služby (viz [Zanoříte se do XML webové služby](http://msdn.microsoft.com/en-us/8e67de38-bf5f-41cc-a457-1b88ce63d764)). Dochází vždy, když [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] není správně nastaven.  
  
 Možné příčiny jsou:  
  
-   Souboru web.config pro vaše [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace není nastavena na hodnotu "true" debug (viz [režim ladění v aplikacích ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
-   Verzi [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] byl nainstalován po instalaci sady Visual Studio. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]by měly být nainstalovány před Visual Studio. Chcete-li tento problém vyřešit, použijte Windows **ovládací panely > programy a funkce** k opravě instalace sady Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)