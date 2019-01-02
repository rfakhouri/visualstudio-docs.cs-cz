---
title: Pravidla používání nástrojů pro profilaci | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd7a74f546a7d9ae09767ee79747ce9d7fcaba36
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53961800"
---
# <a name="profiling-tools-usage-rules"></a>Pravidla používání nástrojů pro profilaci
Pravidla výkonu v kategorii použití nástroje pro profilaci poskytují pokyny k používání profiler k co nejefektivnějšímu shromažďovat data.  


| | |
| - | - |
| [DA0002: CHYBÍ KNIHOVNA VSPerfCorProf.dll chybí.](../profiling/da0002-vsperfcorprof-dll-is-missing.md) | Profilace příkazový řádek může obsahovat neúplná data pro [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] binární soubory. Příčinou může není nastavení proměnných správné prostředí. |
| [DA0003: VYSOKÝ POČET Počet ukázek jádra](../profiling/da0003-many-kernel-samples.md) | Mnoho profilace vzorků, ke kterým došlo mimo provádění cílový binární soubor byly zaznamenány. Pokud chcete přesnější data shromažďovat, zvažte použití metody instrumentace. |
| [DA0004: Vysoké využití procesoru](../profiling/da0004-high-processor-usage.md) | Data profilování naznačuje, že byly vaše procesory konzistentně zaneprázdněný během spuštění profilování. Pokud chcete přesnější data shromažďovat, zvažte použití metody vzorkování. |
| [DA0008: Shromážděno málo ukázek](../profiling/da0008-few-samples-collected.md) | Počet vzorků shromážděné při spuštění profilace nebyla dostatečně vysoká, aby se statisticky významná. Zvažte profilaci znovu a spuštění aplikace delší dobu. Pomocí metody instrumentace ke shromažďování dat můžete také zvážit. |
| [DA0026: Čas zpracování procesoru jádra nadměrné](../profiling/da0026-excessive-kernel-cpu-time-processing.md) | V režimu jádra procesoru došlo k významné množství času během spuštění profilování. Vezměte v úvahu vzorkování pomocí systémových volání jako metriku namísto používání času jako metriku. |
| [DA0029: Nepodporovaná verze CLR](../profiling/da0029-unsupported-clr-version.md) | PROFILOVANÉHO binární soubor používá verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] pomocí profileru, který není podporován. Sestavy profileru nelze přeložit názvy symbolů. |
| [DA0030: Získat měření interakce vrstev pro databázové projekty](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md) | Velký počet volání metod v <xref:System.Data?displayProperty=fullName> shromáždilo se obor názvů. Chcete-li obsahují data o volání databáze, zvažte, spustí shromažďování dat interakce vrstev ve vašem profilu. |
