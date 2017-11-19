---
title: "Souhrnné zobrazení – Data paměti .NET | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Summary view
ms.assetid: 0cb317c3-0ae6-4531-aaa8-447576eec037
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 968d46c4fe771229647282c719815982d81bf416
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="summary-view---net-memory-data"></a>Souhrnné zobrazení – Data paměti .NET
Souhrnné zobrazení zobrazí informace o funkcích rozhraní .NET a typy, které nejvíce paměti přidělené a typy, které byly vytvořeny většinu doby v profilaci spustit. Další informace, včetně popisu odkazy oznámení a sestavy seznamů v tématu [zobrazení souhrnu](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Časová osa grafu  
 Časová osa grafu v souhrnné zobrazení zobrazuje využití procesoru (CPU) podle PROFILOVANÉHO aplikace v průběhu času, který profilace došlo k chybě. Časová osa grafu můžete filtrovat zobrazení vybrané časové období. Další informace najdete v tématu [postupy: filtrování zobrazení sestav ze souhrnné časové osy](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="functions-allocating-most-memory"></a>Funkce přidělování většina paměti  
 Obsahuje seznam funkcí, které přiděleny největší počet bajtů paměti při spuštění profilování.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název funkce.|  
|**% Bajtů**|Procento všechny přidělené bajty v profilaci spuštění, které byly přiděleny pomocí této funkce nebo podřízené funkci, která byla volána pomocí této funkce.|  
  
## <a name="types-with-most-memory-allocated"></a>Typy s nejvíce paměti přidělené  
 Obsahuje typy, pro které byly přiděleny největší počet bajtů paměti v profilaci spustit.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název typu.|  
|**% Bajtů**|Procento všechny přidělené bajty v profilaci spuštění, které byly přiděleny pro tento typ.|  
  
## <a name="types-with-most-instances"></a>Typy s většina instancí  
 Seznam typů, které byly vytvořeny nejvíce doby při vytváření profilu spustit. měl  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název typu.|  
|**Instance %**|Procento celkový počet of.NET objekty, které byly vytvořeny v profilaci spuštění, které byly instance tohoto typu.|  
  
## <a name="see-also"></a>Viz také  
 [Souhrnné zobrazení](../profiling/summary-view-sampling-data.md)   
 [Souhrnné zobrazení](../profiling/summary-view-instrumentation-data.md)