---
title: Zobrazení funkcí – Data kolizí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Functions view
ms.assetid: 208773b0-1a54-4b7a-ad37-2b6fd4f731d4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a774c3e04a2a4ded098424728cf3f9621699be1d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55068743"
---
# <a name="functions-view---contention-data"></a>Zobrazení funkcí – data kolizí
Sestavy funkce zobrazení seznamů data kolize funkcí během spuštění profilování, který se zablokoval ze spuštění během spuštění profilování.  
  
 Následující tabulka vysvětluje hodnoty, které jsou zobrazeny v zobrazení funkcí ze souboru dat profilování, která byla shromážděna pomocí metody souběžnosti.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Výhradní čas zablokování**|Množství času, během které se této funkce bylo zablokováno provádění kódu v těle funkce. Čas zablokování ve funkcích, které byly volány funkce není součástí.|  
|**% Výhradního času zablokování**|Procento času všechny zablokování při spuštění profilace, která byla výhradní čas zablokování této funkce.|  
|**Výhradní spory**|Počet pokusů, které tuto funkci bylo zablokováno provádění kódu v těle funkce. Tento počet sporů: ve funkcích, které byly volány funkce nejsou zahrnuty.|  
|**% Výhradních sporů**|Procento všech sporů během spuštění profilování bylo výhradních sporů této funkce.|  
|**Adresa funkce**|Adresa funkce.|  
|**Název funkce**|Plně kvalifikovaný název funkce.|  
|**Celkový čas zablokování**|Čas, který tuto funkci nebo funkce, která byla volána pomocí této funkce bylo zablokováno provádění.|  
|**% Celkového času zablokování**|Procento všech času zablokování spuštění profilování, která byla celkový čas zablokování této funkce nebo modulu.|  
|**Celkově sporů**|Počet pokusů, které tuto funkci nebo funkce, která byla volána pomocí této funkce bylo zablokováno provádění.|  
|**% Celkových sporů**|Procento všech sporů při spuštění, který profilace se celkově sporů této funkce nebo modulu.|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje funkci.|  
|**ID procesu**|ID procesu (PID) proces, ve kterém funkce byla spuštěna.|  
|**Název procesu**|Název procesu.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení funkcí](../profiling/functions-view.md)   
 [Zobrazení funkcí – instrumentace](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [Zobrazení funkcí – vzorkování](../profiling/functions-view-dotnet-memory-sampling-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-instrumentation-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-sampling-data.md)