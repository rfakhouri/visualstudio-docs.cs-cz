---
title: Pravidla používání nástrojů pro profilaci | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 693b43d4a421bd0d0d87fbf485af88573b26adff
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68165734"
---
# <a name="profiling-tools-usage-rules"></a>Pravidla používání nástrojů pro profilaci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pravidla výkonu v kategorii použití nástroje pro profilaci poskytují pokyny k používání profiler k co nejefektivnějšímu shromažďovat data.  
  
|||  
|-|-|  
|[DA0002: Chybí knihovna VSPerfCorProf.dll](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|Profilace příkazový řádek může obsahovat neúplná data pro [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] binární soubory. Příčinou může není nastavení proměnných správné prostředí.|  
|[DA0003: Velký počet ukázek jádra](../profiling/da0003-many-kernel-samples.md)|Mnoho profilace vzorků, ke kterým došlo mimo provádění cílový binární soubor byly zaznamenány. Pokud chcete přesnější data shromažďovat, zvažte použití metody instrumentace.|  
|[DA0004: Vysoké využití procesoru](../profiling/da0004-high-processor-usage.md)|Data profilování naznačuje, že byly vaše procesory konzistentně zaneprázdněný během spuštění profilování. Pokud chcete přesnější data shromažďovat, zvažte použití metody vzorkování.|  
|[DA0008: Shromážděno málo vzorků](../profiling/da0008-few-samples-collected.md)|Počet vzorků shromážděné při spuštění profilace nebyla dostatečně vysoká, aby se statisticky významná. Zvažte profilaci znovu a spuštění aplikace delší dobu. Pomocí metody instrumentace ke shromažďování dat můžete také zvážit.|  
|[DA0026: Nadměrný čas zpracování procesoru jádra](../profiling/da0026-excessive-kernel-cpu-time-processing.md)|V režimu jádra procesoru došlo k významné množství času během spuštění profilování. Vezměte v úvahu vzorkování pomocí systémových volání jako metriku namísto používání času jako metriku.|  
|[DA0029: Nepodporovaná verze CLR](../profiling/da0029-unsupported-clr-version.md)|PROFILOVANÉHO binární soubor používá verzi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] pomocí profileru, který není podporován. Sestavy profileru nelze přeložit názvy symbolů.|  
|[DA0030: Získání měření interakce vrstev pro databázové projekty](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|Velký počet volání metod v <xref:System.Data?displayProperty=fullName> shromáždilo se obor názvů. Chcete-li obsahují data o volání databáze, zvažte, spustí shromažďování dat interakce vrstev ve vašem profilu.|
