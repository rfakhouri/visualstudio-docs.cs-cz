---
title: Řízení sběru dat | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- advanced tasks for profiling tools
- profiling tools, advanced tasks
ms.assetid: e713ad63-b948-46f3-8db9-59b30922ebe5
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6170ee5e93bcb8faeadd1d918468a44c4badb99
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629461"
---
# <a name="controlling-data-collection"></a>Řízení kolekce dat
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [řízení shromažďování dat](https://docs.microsoft.com/visualstudio/profiling/controlling-data-collection).  
  
Nástroje pro profilaci sady [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] umožňují řídit dobu, kdy dochází během relace výkonu k profilaci dat, a slouží k určení funkcí, které jsou profilovány. Tato část popisuje, jak spustit a zastavit shromažďování dat z **prohlížeč výkonu** a **ovládacího prvku sběru dat** windows a jak omezit objekty, pro které jsou shromažďována data profilování.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Spuštění a zastavení profilování:** můžete spustit profilování aplikace při spuštění aplikace, nebo můžete připojit profiler k procesu, který je již spuštěna. Pokud je cílová aplikace spuštěna, je shromažďování dat možné pozastavit a obnovit. Ukončení relace profilování lze provést ukončením cílové aplikace nebo odpojením profileru od spuštěného procesu.|-   [Postupy: zahájení a ukončení shromažďování dat výkonu](../profiling/how-to-start-and-end-performance-data-collection.md)<br />-   [Postupy: připojení a odpojení nástroje Sledování výkonu ke spuštěným procesům](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md)<br />-   [Postupy: pozastavení a pokračování shromažďování dat výkonu](../profiling/how-to-pause-and-resume-performance-data-collection.md)|  
|**Konfigurace profilování instrumentace pro omezení sběru dat:** vlastností konfigurace relace výkonu můžete omezit data, která se shromažďují v rámci profilování, které používají metodu instrumentace. Je možné zahrnout nebo vyloučit určité knihovny dll, obory názvů, třídy a funkce. Je také možné vyloučit funkce, které nesplňují zadanou mezní hodnotu velikosti.|-   [Postupy: omezení instrumentace na konkrétní knihovny DLL](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)<br />-   [Postupy: omezení instrumentace na konkrétní funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Postupy: vyloučení nebo zahrnutí krátkých funkcí z instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)|  
  
## <a name="related-sections"></a>Související oddíly  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
  
## <a name="see-also"></a>Viz také  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)



