---
title: Řízení sběru dat | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- advanced tasks for profiling tools
- profiling tools, advanced tasks
ms.assetid: e713ad63-b948-46f3-8db9-59b30922ebe5
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e34c4db965cacefabe752774e393a4339042040e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68182706"
---
# <a name="controlling-data-collection"></a>Řízení shromažďování dat
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nástroje pro profilaci sady [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] umožňují řídit dobu, kdy dochází během relace výkonu k profilaci dat, a slouží k určení funkcí, které jsou profilovány. Tato část popisuje, jak spustit a zastavit shromažďování dat z **prohlížeč výkonu** a **ovládacího prvku sběru dat** windows a jak omezit objekty, pro které jsou shromažďována data profilování.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Spuštění a zastavení profilování:** Můžete spustit profilování aplikace při spuštění aplikace, nebo můžete připojit profiler k procesu, který je již spuštěna. Pokud je cílová aplikace spuštěna, je shromažďování dat možné pozastavit a obnovit. Ukončení relace profilování lze provést ukončením cílové aplikace nebo odpojením profileru od spuštěného procesu.|-   [Jak: Zahájení a ukončení shromažďování dat o výkonu](../profiling/how-to-start-and-end-performance-data-collection.md)<br />-   [Jak: Připojení nástrojů pro měření výkonu ke spuštěným procesům a jejich odpojení](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md)<br />-   [Jak: Pozastavení a opětovné spuštění shromažďování dat o výkonu](../profiling/how-to-pause-and-resume-performance-data-collection.md)|  
|**Konfigurace profilování instrumentace pro omezení sběru dat:** Vlastnosti konfigurace relace výkonu můžete omezit data, která se shromažďují v rámci profilování, které používají metodu instrumentace. Je možné zahrnout nebo vyloučit určité knihovny dll, obory názvů, třídy a funkce. Je také možné vyloučit funkce, které nesplňují zadanou mezní hodnotu velikosti.|-   [Jak: Omezení instrumentace na určité knihovny DLL](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)<br />-   [Jak: Omezení instrumentace na určité funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Jak: Vyloučení krátkých funkcí z instrumentace nebo jejich zahrnutí do instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)|  
  
## <a name="related-sections"></a>Související oddíly  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
  
## <a name="see-also"></a>Viz také  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)
