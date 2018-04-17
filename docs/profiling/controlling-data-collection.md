---
title: Řízení shromažďování dat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- advanced tasks for profiling tools
- profiling tools, advanced tasks
ms.assetid: e713ad63-b948-46f3-8db9-59b30922ebe5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e111473f4cd17e7bad71696d6512336b80b99f4a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="controlling-data-collection"></a>Řízení kolekce dat
Nástroje pro profilaci sady [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] umožňují řídit dobu, kdy dochází během relace výkonu k profilaci dat, a slouží k určení funkcí, které jsou profilovány. Tato část popisuje, jak spustit a zastavit shromažďování dat z **prohlížeč výkonu** a **ovládací prvek kolekce dat** windows a jak omezit objekty, pro které se shromažďují data vytváření profilů.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Spuštění a zastavení profilování:** můžete začít profil aplikace při spuštění aplikace, nebo můžete připojení profileru k procesu, který je již spuštěn. Pokud je cílová aplikace spuštěna, je shromažďování dat možné pozastavit a obnovit. Ukončení relace profilování lze provést ukončením cílové aplikace nebo odpojením profileru od spuštěného procesu.|-   [Postupy: spuštění a ukončení shromažďování dat výkonu](../profiling/how-to-start-and-end-performance-data-collection.md)<br />-   [Postupy: připojení a odpojení nástroje pro sledování výkonu ke spuštěným procesům](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md)<br />-   [Postupy: pozastavení a obnovení shromažďování dat výkonu](../profiling/how-to-pause-and-resume-performance-data-collection.md)|  
|**Konfigurace pro omezení shromážděných dat profilace instrumentace:** vlastnosti výkonnostní relace konfigurace můžete použít k omezení dat, která se shromažďují v profilaci spustí, které používají metody instrumentace. Je možné zahrnout nebo vyloučit určité knihovny dll, obory názvů, třídy a funkce. Je také možné vyloučit funkce, které nesplňují zadanou mezní hodnotu velikosti.|-   [Postupy: omezení instrumentace na konkrétní knihovny DLL](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)<br />-   [Postupy: omezení instrumentace na konkrétní funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Postupy: vyloučení nebo zahrnutí funkce CShort z instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)|  
  
## <a name="related-sections"></a>Související oddíly  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
  
## <a name="see-also"></a>Viz také  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)