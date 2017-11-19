---
title: "Chyba: Webový Server byl uzamčen a blokuje příkaz DEBUG. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.webdbg_debug_verb_blocked
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
ms.assetid: 9c8c4812-17db-484d-9c1b-ffd9e3bfef5a
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87c2bea224676df483e74393fe1ecf5d05e10df8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb"></a>Chyba: Webový server byl uzamčen a blokuje příkaz DEBUG.
Zanoříte se do webové aplikace nebo webové služby XML se nezdařila, protože spuštění nástroje lockdown služby IIS a URLScan byla nainstalovaná a aktivovaná. Tento stav služby IIS blokuje příjem příkaz DEBUG.  
  
 Nástroj URLScan je nástroj zabezpečení, který funguje ve spojení s nástroje Lockdown služby IIS a poskytuje správcům lokality webové služby IIS umožňuje vypnout nepotřebné funkce a omezí typ požadavků HTTP, které server zpracuje. Nástroj URLScan zabezpečení blokováním specifických požadavků zabraňuje potenciálně škodlivé požadavky dosažení serveru a způsobit škody.  
  
 Pokud vaše aplikace běží ve službě IIS 6.0 v systému Windows Server 2003, nemusí spustit nástroje Lockdown služby IIS, protože služby IIS 6.0 poskytuje stejné funkce.  
  
### <a name="to-enable-debugging-on-a-web-server-with-urlscan-installed"></a>Pokud chcete povolit ladění na webovém serveru s modulem URLScan nainstalován  
  
1.  Vyhledejte soubor Urlscan.ini. Za normálních okolností najdete je v adresáři, který vypadá takto:  
  
     C:\WINNT\System32\Inetsrv\urlscan  
  
2.  Vytvořte kopii souboru s názvem **Urlscan.old**.  
  
3.  Otevřete původní kopii souboru Urlscan.ini pomocí poznámkového bloku nebo textovém editoru podle svého výběru.  
  
4.  V Urlscan.ini přejděte do oddílu [AllowVerbs]. LADĚNÍ přidáte do sekce [AllowVerbs]. Pokud se zobrazí; ladění v sekci [AllowVerbs], středník k zrušte komentář u příkaz odebrat.  
  
5.  Přejděte do oddílu [DenyVerbs]. Pokud ladění se zobrazí v části [DenyVerbs], odeberte ji.  
  
6.  Uložte soubor.  
  
7.  Restartujte server, nebo restartujte službu IIS.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)   
 [Chyba: Webový Server nenalezl požadovaný prostředek](../debugger/error-the-web-server-could-not-find-the-requested-resource.md)