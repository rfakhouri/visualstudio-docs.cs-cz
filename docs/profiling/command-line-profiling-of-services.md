---
title: Profilace služeb z příkazového řádku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling toos,services
- profiling services
ms.assetid: f0d62318-b0e8-49c6-9a30-9f7a6adef2f6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 80e5c8d7a1edc7af76870f3d120d66365d2f1cf4
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="command-line-profiling-of-services"></a>Profilace služeb z příkazového řádku
Tato část popisuje postupy a možnosti pro shromažďování dat výkonu pro služby systému Windows pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci z příkazového řádku.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Běžné úlohy
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Shromažďování statistik aplikace:** shromažďování statistik výkonu pomocí metody vzorkování. Vzorkování dat je užitečné pro analyzovat problémy využití procesoru a principy vlastnosti Obecné výkonu aplikace.|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**Shromažďování podrobných dat časování:** pomocí metody instrumentace můžete shromažďovat informace podrobné časování. Data instrumentace je užitečný pro analyzovat problémy vstupně-výstupní operace a pro podrobné analýzy scénářů aplikace.|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|  
|**Shromažďování dat paměti .NET:** použití vzorkování nebo instrumentace ke shromažďování dat přidělení paměti .NET, která uvádí, velikost a počet přidělené objekty. Může taky shromažďovat životnosti objektů, které se dozvíte, velikost a počet objektů, které jsou v každé kolekci generace uvolňování paměti uvolnit.|-   [Shromažďování dat paměti .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**Shromažďování dat souběžnosti:** použít ke shromažďování dat kolizí prostředku a data aktivity přístup z více vláken, která obsahuje využití je využití procesoru, kolizí přístup z více vláken, migrace přístup z více vláken, synchronizace zpoždění, oblasti překryté vstupně-výstupní operace, a jiných metoda souběžného zpracování systémové události.|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
|**Přidání dat interakce vrstev:** můžete přidat data výkonu o synchronní ADO.NET volá službu provedené Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databáze.|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace samostatné (klient)**|-   [Profil samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Profil aplikace ASP.NET**|-   [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)|