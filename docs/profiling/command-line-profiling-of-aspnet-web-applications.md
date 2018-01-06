---
title: "Profilace webových aplikací ASP.NET z příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling ASP.NET applications
- profling tools,ASP.NET applications
ms.assetid: 897c00d5-5767-433b-a960-4a29c6023ede
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: aspnet
ms.openlocfilehash: 9c96d83a278f7a82c56a58e4db7ec96cbe426bea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="command-line-profiling-of-aspnet-web-applications"></a>Profilace webových aplikací ASP.NET z příkazového řádku
Tato část popisuje postupy a možnosti pro shromažďování dat výkonu pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci z příkazového řádku.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Shromažďování dat snadno profilaci základní ASP.NET:** použití **VSPerfASPNETCmd** nástroj pro shromažďování vzorkování, instrumentace, využívání paměti rozhraním .NET, kolizí, nebo úroveň dat interakce bez požadavky na konfiguraci a Restartování Internetové informační služby (IIS), které jsou potřebné pro **VSPerfCmd**. **VSPerfASPNETCmd** pro shromažďování dalších dat nebo k řízení shromažďování dat nepovoluje. **Poznámka:****VSPerfASPNETCmd** je upřednostňovaný nástroj můžete použít použijte samostatné profileru profilu ASP.NET Web sites.|-   [Rychlé profilování webových stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)|  
|**Shromažďování statistik aplikace:** shromažďování statistik výkonu pomocí metody vzorkování. Vzorkování dat je užitečné pro analýzu problémy využití procesoru a porozumět obecné výkonové charakteristiky aplikace.|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**Shromažďování podrobných dat časování:** pomocí metody instrumentace můžete shromažďovat informace podrobné časování. Data instrumentace je užitečný pro analyzovat problémy vstupně-výstupní operace a pro podrobné analýzy scénářů aplikace.|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line.md)|  
|**Shromažďování dat paměti .NET:** použití vzorkování nebo instrumentace ke shromažďování dat přidělení paměti .NET, která uvádí, velikost a počet přidělené objekty. Může taky shromažďovat životnosti objektů, které se dozvíte, velikost a počet objektů, které jsou v každé kolekci generace uvolňování paměti uvolnit.|-   [Shromažďování dat paměti](../profiling/collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line.md)|  
|**Shromažďování dat souběžnosti:** použít metodu souběžného zpracování ke shromažďování dat kolizí prostředku. **Poznámka:** shromažďování vlákno aktivity a vizualizace dat není podporován pro webové aplikace.|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
|**Přidání dat interakce vrstev:** můžete přidat data výkonu o synchronní [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] volá, který [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] provede webové aplikace Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databáze.|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace samostatné (klient)**|-   [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Profil služby**|-   [Profilace služeb](../profiling/command-line-profiling-of-services.md)|