---
title: "Souhrnné zobrazení – Data instrumentace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Summary view
ms.assetid: 0a3b3a1f-e22b-4ac8-b46e-71694e9b2cf1
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e486f7df85081ce010e6d2f518978f0952412ea1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="summary-view---instrumentation-data"></a>Souhrnné zobrazení – Data instrumentace
Souhrnné zobrazení zobrazí informace o výkonu nejnákladnější funkce v profilaci spustit. Další informace, včetně popisu odkazy oznámení a sestavy seznamů v tématu [zobrazení souhrnu](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Časová osa grafu  
 Časová osa grafu v souhrnné zobrazení zobrazuje využití procesoru (CPU) podle PROFILOVANÉHO aplikace v průběhu času, který profilace došlo k chybě. Časová osa grafu můžete filtrovat zobrazení vybrané časové období. Další informace najdete v tématu [postupy: filtrování zobrazení sestav ze souhrnné časové osy](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="hot-path"></a>Aktivní trase  
 **Aktivní trase** zobrazuje cestu spuštění, který nejvíce času. Můžete kliknout na funkce, která se zobrazí zobrazení podrobností funkce pro funkci. Zobrazit další zobrazení pro funkce, klikněte pravým tlačítkem na funkci a potom klikněte na zobrazení ze seznamu.  
  
 **Aktivní trase** zahrnuje následující data pro jednotlivé funkce:  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název funkce.|  
|**% Uplynulá doba (včetně).**|Procento všech čas v profilaci data, která funkci stráví provádění kódu v jeho tělo funkce a funkce, které ji volat.|  
|**Uplynulý čas výhradní %**|Procento všech čas v profilaci dat, který stráví funkce provádění kódu v jeho tělo funkce. Čas strávený v funkce, které volá funkci není součástí.|  
  
## <a name="functions-with-most-individual-work"></a>Funkce s nejvíce jednotlivé pracovní  
 Seznam funkcí, které využívat většinu času provádění kódu v tělo funkce a není funkce, které ji volat.  
  
 **Funkce s nejvíce jednotlivé pracovní** zahrnuje následující data pro jednotlivé funkce:  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název funkce.|  
|**Výhradní čas: %**|Procento všech čas v profilaci dat, který stráví funkce provádění kódu v jeho tělo funkce. Čas strávený v funkce, které volá funkci není součástí.|  
  
## <a name="see-also"></a>Viz také  
 [Souhrnné zobrazení](../profiling/summary-view-sampling-data.md)   
 [Souhrnné zobrazení](../profiling/summary-view-dotnet-memory-data.md)