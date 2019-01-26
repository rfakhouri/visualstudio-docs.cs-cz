---
title: Profilace samostatných aplikací z příkazového řádku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 728fce7348b94d458a6ce58a86e27ad48726f23c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935056"
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>Profilace samostatných aplikací z příkazového řádku
Tato část popisuje postupy a možnosti pro shromažďování dat výkonu pro samostatné (klientské) aplikace s použitím [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje pro profilaci z příkazového řádku.  

## <a name="common-tasks"></a>Běžné úkoly  

| Úloha | Související obsah |
| - | - |
| **Shromažďování statistik aplikace:** Shromažďování statistik výkonu pomocí metody odběru vzorků. Vzorkování dat je užitečné analyzovat problémy s využitím procesoru a pochopení charakteristik obecné informace o výkonu aplikace. | -   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-stand-alone-applications.md) |
| **Shromažďování podrobných dat časování:** Pomocí metody instrumentace ke shromažďování podrobných informací o časování. Data instrumentace je užitečná pro analýzu problémů vstupně-výstupních operací a k podrobné analýze scénáře aplikací. | -   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application.md) |
| **Shromažďování dat paměti .NET:** Pomocí vzorkování nebo instrumentace lze shromažďovat data o přidělování paměti .NET, který vám ukáže, velikost a počet přidělených objektů. Může také shromažďovat data o životním cyklu objektu, který vám ukáže, velikost a počet objektů, které jsou uvolněny v každé generaci uvolňování paměti. | -   [Shromažďování dat paměti .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md) |
| **Shromažďování dat souběžnosti:** Za použití metody souběžnosti můžete shromažďovat data kolize prostředků a data aktivity vláken, která ukazuje využití procesoru, kolize vlákna, migrace vlákna, zpoždění synchronizace, míst překrytí I/O a další systémové události. | -   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-stand-alone-applications.md) |
| **Přidání dat interakce vrstev:** Můžete přidat data o výkonu o synchronní ADO.NET, který volá žádosti služby Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databáze. Přidání dat interakce vrstvy do běhu profilování vyžaduje zvláštní procedury s nástroji pro profilaci příkazového řádku. | -   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md) |
| **Vyzkoušejte si to:** Krok za krokem postupem ukázková klientská aplikace profilu pomocí metody vzorkování nebo instrumentace. | -   [Návod: Příkazový řádek profilování pomocí vzorkování](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [Návod: Příkazový řádek, profilace s použitím instrumentace](/visualstudio/profiling/command-line-profiling-of-stand-alone-applications) |

## <a name="related-tasks"></a>Související úlohy  

|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace ASP.NET**|-   [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**Profil služby**|-   [Profil služby](../profiling/command-line-profiling-of-services.md)|