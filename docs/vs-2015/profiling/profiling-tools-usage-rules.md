---
title: Pravidla používání nástrojů pro profilaci | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d508fdfe1845a75f0ef7e0ba36730afbaa4e157
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670725"
---
# <a name="profiling-tools-usage-rules"></a>Pravidla používání nástrojů pro profilaci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [pravidla používání nástrojů pro profilaci](https://docs.microsoft.com/visualstudio/profiling/profiling-tools-usage-rules).  
  
Pravidla výkonu v kategorii použití nástroje pro profilaci poskytují pokyny k používání profiler k co nejefektivnějšímu shromažďovat data.  
  
|||  
|-|-|  
|[DA0002: Chybí knihovna VSPerfCorProf.dll](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|Profilace příkazový řádek může obsahovat neúplná data pro [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] binární soubory. Příčinou může není nastavení proměnných správné prostředí.|  
|[DA0003: Vysoký počet ukázek jádra](../profiling/da0003-many-kernel-samples.md)|Mnoho profilace vzorků, ke kterým došlo mimo provádění cílový binární soubor byly zaznamenány. Pokud chcete přesnější data shromažďovat, zvažte použití metody instrumentace.|  
|[DA0004: Vysoké využití procesoru](../profiling/da0004-high-processor-usage.md)|Data profilování naznačuje, že byly vaše procesory konzistentně zaneprázdněný během spuštění profilování. Pokud chcete přesnější data shromažďovat, zvažte použití metody vzorkování.|  
|[DA0008: Shromážděno málo ukázek](../profiling/da0008-few-samples-collected.md)|Počet vzorků shromážděné při spuštění profilace nebyla dostatečně vysoká, aby se statisticky významná. Zvažte profilaci znovu a spuštění aplikace delší dobu. Pomocí metody instrumentace ke shromažďování dat můžete také zvážit.|  
|[DA0026: Nadměrný čas zpracování procesoru jádra](../profiling/da0026-excessive-kernel-cpu-time-processing.md)|V režimu jádra procesoru došlo k významné množství času během spuštění profilování. Vezměte v úvahu vzorkování pomocí systémových volání jako metriku namísto používání času jako metriku.|  
|[DA0029: Nepodporovaná verze CLR](../profiling/da0029-unsupported-clr-version.md)|PROFILOVANÉHO binární soubor používá verzi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] pomocí profileru, který není podporován. Sestavy profileru nelze přeložit názvy symbolů.|  
|[DA0030: Získat Měření interakce vrstev pro databázové projekty](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|Velký počet volání metod v <xref:System.Data?displayProperty=fullName> shromáždilo se obor názvů. Chcete-li obsahují data o volání databáze, zvažte, spustí shromažďování dat interakce vrstev ve vašem profilu.|



