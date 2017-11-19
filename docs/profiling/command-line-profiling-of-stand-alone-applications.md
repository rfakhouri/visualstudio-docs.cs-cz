---
title: "Profilace samostatných aplikací z příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 212631838fa6c396fc6f1a5af5164538a156bcd0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>Profilace samostatných aplikací z příkazového řádku
Tato část popisuje postupy a možnosti pro shromažďování dat výkonu pro samostatné (klient) aplikace pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci z příkazového řádku.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Shromažďování statistik aplikace:** shromažďování statistik výkonu pomocí metody vzorkování. Vzorkování dat je užitečné pro analyzovat problémy využití procesoru a principy vlastnosti Obecné výkonu aplikace.|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Shromažďování podrobných dat časování:** pomocí metody instrumentace můžete shromažďovat informace podrobné časování. Data instrumentace je užitečný pro analyzovat problémy vstupně-výstupních operací a pro podrobné analýzy scénářů aplikace.|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**Shromažďování dat paměti .NET:** použití vzorkování nebo instrumentace ke shromažďování dat přidělení paměti .NET, která uvádí, velikost a počet přidělené objekty. Může taky shromažďovat životnosti objektů, které se dozvíte, velikost a počet objektů, které jsou v každé kolekci generace uvolňování paměti uvolnit.|-   [Shromažďování dat paměti .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Shromažďování dat souběžnosti:** použít ke shromažďování dat kolizí prostředku a data aktivity přístup z více vláken, která obsahuje využití procesoru můžete, kolizí přístup z více vláken, migrace přístup z více vláken, synchronizace zpoždění, oblasti překryté vstupně-výstupních operací, a jiných metoda souběžného zpracování systémové události.|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Přidání dat interakce vrstvy:** můžete přidat data výkonu o synchronní ADO.NET volá o žádosti na Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databáze. Přidání dat interakce vrstev pro spuštění profilování vyžaduje konkrétní postupy s příkazového řádku nástroje pro profilaci.|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Vyzkoušejte si to:** použít podrobné postupy profilu pomocí metody vzorkování nebo instrumentace vzorku klientskou aplikaci.|-   [Návod: Profilace z příkazového řádku pomocí vzorkování](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [Návod: Profilace z příkazového řádku pomocí instrumentace](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace ASP.NET**|-   [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**Profil služby**|-   [Profilace služeb](../profiling/command-line-profiling-of-services.md)|