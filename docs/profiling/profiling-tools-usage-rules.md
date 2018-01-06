---
title: "Pravidla používání nástrojů pro profilaci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5585f6828677387d07f00039634fdfe904216ef2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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