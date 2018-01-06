---
title: "Profilace služeb z příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling toos,services
- profiling services
ms.assetid: f0d62318-b0e8-49c6-9a30-9f7a6adef2f6
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0a82cc33e46c37ddba141ba1defab0aa51fcb1d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="command-line-profiling-of-services"></a>Profilace služeb z příkazového řádku
Tato část popisuje postupy a možnosti pro shromažďování dat výkonu pro služby systému Windows pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci z příkazového řádku.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Shromažďování statistik aplikace:** shromažďování statistik výkonu pomocí metody vzorkování. Vzorkování dat je užitečné pro analyzovat problémy využití procesoru a principy vlastnosti Obecné výkonu aplikace.|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**Shromažďování podrobných dat časování:** pomocí metody instrumentace můžete shromažďovat informace podrobné časování. Data instrumentace je užitečný pro analyzovat problémy vstupně-výstupní operace a pro podrobné analýzy scénářů aplikace.|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**Shromažďování dat paměti .NET:** použití vzorkování nebo instrumentace ke shromažďování dat přidělení paměti .NET, která uvádí, velikost a počet přidělené objekty. Může taky shromažďovat životnosti objektů, které se dozvíte, velikost a počet objektů, které jsou v každé kolekci generace uvolňování paměti uvolnit.|-   [Shromažďování dat paměti .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**Shromažďování dat souběžnosti:** použít ke shromažďování dat kolizí prostředku a data aktivity přístup z více vláken, která obsahuje využití je využití procesoru, kolizí přístup z více vláken, migrace přístup z více vláken, synchronizace zpoždění, oblasti překryté vstupně-výstupní operace, a jiných metoda souběžného zpracování systémové události.|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
|**Přidání dat interakce vrstev:** můžete přidat data výkonu o synchronní ADO.NET volá službu provedené Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databáze.|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace samostatné (klient)**|-   [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Profil aplikace ASP.NET**|-   [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)|