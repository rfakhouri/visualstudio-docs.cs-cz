---
title: Souhrnné zobrazení – vzorkování dat | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method, Summary view
- Summary view
ms.assetid: 79056873-2985-40be-9112-cdbc26a65156
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d0b1c1da6bd493fc53419ef5b371b74488002e27
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53938602"
---
# <a name="summary-view---sampling-data"></a>Souhrnné zobrazení – vzorkování dat
Souhrnné zobrazení zobrazuje informace o výkonu – nejdražší funkce v profilování. Další informace, včetně popisu odkazy oznámení a sestavy seznamy, naleznete v tématu [souhrnné zobrazení](../profiling/summary-view.md).  
  
> [!NOTE]
>  Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="timeline-graph"></a>Časová osa grafu  
 Časová osa grafu v souhrnném zobrazení zobrazuje procento využití procesoru (CPU) profilované aplikace v čase, které profilaci došlo k chybě. Časová osa grafu můžete použít k filtrování zobrazení tak, aby ve vybraném časovém rozsahu. Další informace najdete v tématu [jak: Filtrování zobrazení sestav ze časová osa souhrnu](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="hot-path"></a>Kritická cesta  
 **Kritickou cestu** zobrazí cesta provedení, ve kterém byly shromážděny Většina ukázek. Můžete kliknout na funkci, kterou chcete zobrazit podrobnosti o funkci pro funkci. Ostatní zobrazení pro funkci, klikněte pravým tlačítkem na funkci a potom klikněte na zobrazit ze seznamu.  
  
 **Kritickou cestu** zahrnuje následující data pro každou funkci:  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Název**|Název funkce.|  
|**% Celkových vzorků**|Procento všechny ukázky, ke kterým došlo při provádění této funkci nebo funkce volaných touto funkcí.|  
|**% Výhradních vzorků**|Procento všechny ukázky, ke kterým došlo při provádění kódu funkce v těle funkce. Vzorky se shromažďují ve funkcích volaných touto funkcí nejsou zahrnuty.|  
  
## <a name="functions-doing-most-individual-work"></a>Funkce provádějící nejvíce individuální práce  
 **Funkce provádějící nejvíce samostatné práce** seznam zobrazuje funkce, které mají největší počet výhradních vzorků při spuštění profilace. Exkluzivní ukázky je přiřazen k funkci, pokud funkci spouští vlastní kód po shromáždění vzorku. Exkluzivní ukázky není přiřazen k funkci, pokud funkce volá jinou funkci po shromáždění vzorku. Velký počet výhradních vzorků označuje, že byl spoustu času stráveného samotné funkce.  
  
 Můžete kliknout na funkci, kterou chcete zobrazit podrobnosti o funkci pro funkci. Další zobrazení, pro funkce, klikněte pravým tlačítkem na funkci a potom klikněte na zobrazit ze seznamu.  
  
 **Funkce provádějící nejvíce samostatné práce** zahrnuje následující data pro každou funkci:  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Název**|Název funkce.|  
|**% Výhradních vzorků**|Procento vzorků při spuštění profilace, které byly shromážděny při provádění kódu funkce v těle jeho funkce. Procento vyloučí ukázky, které byly shromážděny při byly provádění funkcí, které tato funkce volána.|  
  
## <a name="see-also"></a>Viz také:  
 [Souhrnné zobrazení – data paměti .NET](../profiling/summary-view-dotnet-memory-data.md)   
 [Souhrnné zobrazení – data instrumentace](../profiling/summary-view-instrumentation-data.md)