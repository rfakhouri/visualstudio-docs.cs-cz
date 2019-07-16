---
title: Profilace samostatných aplikací z příkazového řádku | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3f4b2b78f7187b7a49b78312a1105a2af884fda3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68186637"
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>Profilace samostatných aplikací z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato část popisuje postupy a možnosti pro shromažďování dat výkonu pro samostatné (klientské) aplikace s použitím [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástroje pro profilaci z příkazového řádku.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Shromažďování statistik aplikace:** Shromažďování statistik výkonu pomocí metody odběru vzorků. Vzorkování dat je užitečné analyzovat problémy s využitím procesoru a pochopení charakteristik obecné informace o výkonu aplikace.|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Shromažďování podrobných dat časování:** Pomocí metody instrumentace ke shromažďování podrobných informací o časování. Data instrumentace je užitečná pro analýzu problémů vstupně-výstupních operací a k podrobné analýze scénáře aplikací.|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**Shromažďování dat paměti .NET:** Pomocí vzorkování nebo instrumentace lze shromažďovat data o přidělování paměti .NET, který vám ukáže, velikost a počet přidělených objektů. Může také shromažďovat data o životním cyklu objektu, který vám ukáže, velikost a počet objektů, které jsou uvolněny v každé generaci uvolňování paměti.|-   [Shromažďování dat paměti .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Shromažďování dat souběžnosti:** Za použití metody souběžnosti můžete shromažďovat data kolize prostředků a data aktivity vláken, která ukazuje využití procesoru, kolize vlákna, migrace vlákna, zpoždění synchronizace, míst překrytí I/O a další systémové události.|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Přidání dat interakce vrstev:** Můžete přidat data o výkonu o synchronní ADO.NET, který volá žádosti služby Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] databáze. Přidání dat interakce vrstvy do běhu profilování vyžaduje zvláštní procedury s nástroji pro profilaci příkazového řádku.|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Vyzkoušejte si to:** Krok za krokem postupem ukázková klientská aplikace profilu pomocí metody vzorkování nebo instrumentace.|-   [Návod: Profilace z příkazového řádku s použitím vzorkování](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [Návod: Profilace z příkazového řádku s použitím instrumentace](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace ASP.NET**|-   [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**Profil služby**|-   [Profilace služeb](../profiling/command-line-profiling-of-services.md)|
