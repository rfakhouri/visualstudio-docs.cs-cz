---
title: Pravidla používání nástrojů pro profilaci | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 15b5789a04b4a94156ebec33e525eafe4e22f296
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66745286"
---
# <a name="profiling-tools-usage-rules"></a>Pravidla používání nástrojů pro profilaci
Pravidla výkonu v kategorii použití nástroje pro profilaci poskytují pokyny k používání profiler k co nejefektivnějšímu shromažďovat data.

| | |
| - | - |
| [DA0002: Chybí knihovna VSPerfCorProf.dll](../profiling/da0002-vsperfcorprof-dll-is-missing.md) | Profilace příkazový řádek může obsahovat neúplná data pro binární soubory rozhraní .NET Framework. Příčinou může není nastavení proměnných správné prostředí. |
| [DA0003: Velký počet ukázek jádra](../profiling/da0003-many-kernel-samples.md) | Mnoho profilace vzorků, ke kterým došlo mimo provádění cílový binární soubor byly zaznamenány. Pokud chcete přesnější data shromažďovat, zvažte použití metody instrumentace. |
| [DA0004: Vysoké využití procesoru](../profiling/da0004-high-processor-usage.md) | Data profilování naznačuje, že byly vaše procesory konzistentně zaneprázdněný během spuštění profilování. Pokud chcete přesnější data shromažďovat, zvažte použití metody vzorkování. |
| [DA0008: Shromážděno málo vzorků](../profiling/da0008-few-samples-collected.md) | Počet vzorků shromážděné při spuštění profilace nebyla dostatečně vysoká, aby se statisticky významná. Zvažte profilaci znovu a spuštění aplikace delší dobu. Pomocí metody instrumentace ke shromažďování dat můžete také zvážit. |
| [DA0026: Nadměrný čas zpracování procesoru jádra](../profiling/da0026-excessive-kernel-cpu-time-processing.md) | V režimu jádra procesoru došlo k významné množství času během spuštění profilování. Vezměte v úvahu vzorkování pomocí systémových volání jako metriku namísto používání času jako metriku. |
| [DA0029: Nepodporovaná verze CLR](../profiling/da0029-unsupported-clr-version.md) | PROFILOVANÉHO binární soubor používá verzi rozhraní .NET Framework, kterou profiler nepodporuje. Sestavy profileru nelze přeložit názvy symbolů. |
| [DA0030: Získání měření interakce vrstev pro databázové projekty](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md) | Velký počet volání metod v <xref:System.Data?displayProperty=fullName> shromáždilo se obor názvů. Chcete-li obsahují data o volání databáze, zvažte, spustí shromažďování dat interakce vrstev ve vašem profilu. |
