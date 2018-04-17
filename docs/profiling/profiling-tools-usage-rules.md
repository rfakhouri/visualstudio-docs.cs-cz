---
title: Pravidla používání nástrojů pro profilaci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1de9ded71ca70f4262300805f9a160d96dd622e7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="profiling-tools-usage-rules"></a>Pravidla používání nástrojů pro profilaci
Pravidla výkonu v kategorii použití nástroje pro profilaci obsahují pokyny pro použití profileru ke shromažďování dat efektivní.  
  
|||  
|-|-|  
|[DA0002: Chybí knihovna VSPerfCorProf.dll](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|Profilace příkazového řádku může obsahovat neúplná data pro [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] binární soubory. To může být způsobeno není nastavením proměnné prostředí správné.|  
|[DA0003: Vysoký počet ukázek jádra](../profiling/da0003-many-kernel-samples.md)|Nebyly zaznamenány mnoho profilování vzorků, které došlo k chybě mimo provádění cílový binární soubor. Ke shromažďování dat přesnější, zvažte použití metody instrumentace.|  
|[DA0004: Vysoké využití procesoru](../profiling/da0004-high-processor-usage.md)|Profilace data naznačuje, že byly vaše procesory konzistentně zaneprázdněn během profilace spustit. Ke shromažďování dat přesnější, zvažte použití metody vzorkování.|  
|[DA0008: Shromážděno málo ukázek](../profiling/da0008-few-samples-collected.md)|Počet vzorků, které jsou shromažďovány v profilaci spustit nebyla dostatečně vysoký statisticky významný. Zvažte profilace znovu a spuštění aplikace delší dobu. Můžete také zvažte použití metody instrumentace ke shromažďování dat.|  
|[DA0026: Nadměrný čas zpracování procesoru jádra](../profiling/da0026-excessive-kernel-cpu-time-processing.md)|Významné množství času v profilaci spustit v režimu jádra procesoru došlo k chybě. Vezměte v úvahu vzorkování pomocí systémová volání jako metriku místo použití čas jako metriku.|  
|[DA0029: Nepodporovaná verze CLR](../profiling/da0029-unsupported-clr-version.md)|PROFILOVANÉHO binární používá verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] nepodporuje profileru. Sestav profileru nelze přeložit názvy symbolů.|  
|[DA0030: Získat Měření interakce vrstev pro databázové projekty](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|Velký počet volání metody v <xref:System.Data?displayProperty=fullName> byly shromážděny oboru názvů. Chcete-li zahrnout data o volání databáze, zvažte, shromažďování dat interakce vrstev v profilu aplikace běží.|