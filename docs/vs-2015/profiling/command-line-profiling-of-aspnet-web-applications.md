---
title: Profilace webových aplikací ASP.NET z příkazového řádku | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profiling ASP.NET applications
- profling tools,ASP.NET applications
ms.assetid: 897c00d5-5767-433b-a960-4a29c6023ede
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf3727447d17d941f477dfb71373a8c90e518dd0
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "53861692"
---
# <a name="command-line-profiling-of-aspnet-web-applications"></a>Profilace webových aplikací ASP.NET z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato část popisuje postupy a možnosti pro shromažďování dat výkonu pro [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] webové aplikace s použitím [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástroje pro profilaci z příkazového řádku.  
  
> [!NOTE]
>  Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. Aplikace Windows Store také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Shromažďování dat profilování snadno základní ASP.NET:** Použití **VSPerfASPNETCmd** nástroj pro shromažďování vzorkování, instrumentace, paměti .NET, kolize nebo vrstvy interakce dat bez potřeby jejich požadavky na konfiguraci a restartování Internetové informační služby (IIS), které jsou potřeba pro **VSPerfCmd**. **Příkaz VSPerfASPNETCmd** neumožňuje pro shromažďování dalších dat nebo pro sběr dat řídit. **Poznámka:**  **Příkaz VSPerfASPNETCmd** je preferovaný nástroj použít, můžete použít samostatný profiler k profilu ASP.NET Web sites.|-   [Pohotová profilace stránek pomocí VSPerfASPNETCmd webových](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)|  
|**Shromažďování statistik aplikace:** Shromažďování statistik výkonu pomocí metody odběru vzorků. Vzorkování dat je užitečný pro analýzu využití problémy s Procesorem a pochopení charakteristik obecné informace o výkonu aplikace.|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**Shromažďování podrobných dat časování:** Pomocí metody instrumentace ke shromažďování podrobných informací o časování. Data instrumentace je užitečné pro analýzu problémů vstupně-výstupních operací a k podrobné analýze scénáře aplikací.|-   [Shromažďování podrobných dat časování pomocí instrumentace](/visualstudio/profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method?view=vs-2015)|  
|**Shromažďování dat paměti .NET:** Pomocí vzorkování nebo instrumentace lze shromažďovat data o přidělování paměti .NET, který vám ukáže, velikost a počet přidělených objektů. Může také shromažďovat data o životním cyklu objektu, který vám ukáže, velikost a počet objektů, které jsou uvolněny v každé generaci uvolňování paměti.|-   [Shromažďování dat paměti](../profiling/collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line.md)|  
|**Shromažďování dat souběžnosti:** Za použití metody souběžnosti můžete shromažďovat data kolize prostředků. **Poznámka:**  Shromažďování dat aktivity a vizualizace vlákna se nepodporuje pro webové aplikace.|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
|**Přidání dat interakce vrstev:** Můžete přidat data o výkonu o synchronních [!INCLUDE[vstecado](../includes/vstecado-md.md)] volání [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] webová aplikace odešle společnosti Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] databáze.|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilovat samostatné (klientské) aplikace**|-   [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Profil služby**|-   [Profilace služeb](../profiling/command-line-profiling-of-services.md)|



