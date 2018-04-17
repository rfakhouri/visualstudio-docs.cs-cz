---
title: Souhrnné zobrazení – Data vzorkování | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: e099bfd27e66359692effd7ae87490e1678e19ef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="summary-view---sampling-data"></a>Souhrnné zobrazení – Data vzorkování
Souhrnné zobrazení zobrazí informace o výkonu nejnákladnější funkce v profilaci spustit. Další informace, včetně popisu odkazy oznámení a sestavy seznamů v tématu [zobrazení souhrnu](../profiling/summary-view.md).  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="timeline-graph"></a>Časová osa grafu  
 Časová osa grafu v souhrnné zobrazení ukazuje procento využití procesoru (CPU) PROFILOVANÉHO aplikace v průběhu času, který profilace došlo k chybě. Časová osa grafu můžete filtrovat zobrazení vybrané časové období. Další informace najdete v tématu [postupy: filtrování zobrazení sestav ze souhrnné časové osy](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="hot-path"></a>Aktivní trase  
 **Aktivní trase** zobrazuje cestu provádění, ve které byly shromážděny Většina ukázek. Můžete kliknout na funkce, která se zobrazí zobrazení podrobností funkce pro funkci. Chcete-li zobrazit ostatních zobrazení pro funkci, klikněte pravým tlačítkem na funkci a pak klikněte na tlačítko zobrazit ze seznamu.  
  
 **Aktivní trase** zahrnuje následující data pro jednotlivé funkce:  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název funkce.|  
|**% Ukázky (včetně).**|Procento všech vzorků, které došlo k chybě při provádění této funkce nebo funkci s názvem pomocí této funkce.|  
|**% Výhradní ukázky**|Procento všech vzorků, které při funkce provádění kódu v těle funkce došlo k chybě. Ukázky shromážděny v funkce volané pomocí této funkce nejsou zahrnuty.|  
  
## <a name="functions-doing-most-individual-work"></a>Většina jednotlivých pracuje funkce  
 **Funkce provádění nejvíce jednotlivé pracovní** seznamu zobrazuje funkce, které mají nejvyšší počet výhradní ukázky v profilaci spustit. Výhradní ukázka je přiřazený k funkci, pokud funkce provádí vlastní kód, když nebyla shromážděna v ukázkovém. Výhradní ukázka není přiřazen k funkci, pokud funkce volá jinou funkci při ukázku nebyla shromážděna. Velký počet výhradní vzorků, které označuje, že byl významné čas strávený ve funkci sám sebe.  
  
 Můžete kliknout na funkce, která se zobrazí zobrazení podrobností funkce pro funkci. Zobrazit další zobrazení pro funkce, klikněte pravým tlačítkem na funkci a potom klikněte na zobrazení ze seznamu.  
  
 **Funguje to nejvíce jednotlivé pracovní** zahrnuje následující data pro jednotlivé funkce:  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název funkce.|  
|**% Výhradní ukázky**|Procento všechny ukázky v profilaci spuštění, které byly shromážděny při funkce provádění kódu v jeho tělo funkce. Procento vyloučí vzorků, které byly shromážděny při byly provádění funkcí, které tato funkce volána.|  
  
## <a name="see-also"></a>Viz také  
 [Souhrnné zobrazení](../profiling/summary-view-dotnet-memory-data.md)   
 [Souhrnné zobrazení](../profiling/summary-view-instrumentation-data.md)