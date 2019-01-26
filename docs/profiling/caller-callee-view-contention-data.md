---
title: Volající – zobrazení volaný – Data kolizí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Caller/Callee view
ms.assetid: a18a1b1b-9b39-43c7-b1f3-708fd20376f6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1bdb13bace56a257327d21981aab55e44d42ecd7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54932893"
---
# <a name="callercallee-view----contention-data"></a>Zobrazení volající/volaný – data kolizí
Zobrazení volající/volaný – zobrazí informace kolizí pro vybrané funkce a jeho funkce pro nadřazené a podřízené. Zobrazení volající/volaný obsahuje tři mřížky.  
  
 **Aktuální funkce** se zobrazí v mřížce střední a zobrazuje informace o kolizí pro vybrané funkce. Hodnoty zahrnují všechny blokující tento počet sporů: pro funkci.  
  
 **Funkce, které volaly aktuální funkcí** se zobrazí v hlavní mřížky a funkce na hodnoty vybrané – funkce (aktuální) ukazuje jednotlivé příspěvky volající (nadřazené).  
  
 **Funkce, které byly volány aktuální funkcí** se zobrazí v mřížce dolů a zobrazuje informace kolizí pro volaných (podřízený) funkce vybrané funkce při podřízené funkce byla volána aktuální funkce.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Typ**|Kontext funkce:<br /><br /> -   **0** -aktuální funkce<br />-   **1** – funkce, která volá aktuální funkci<br />-   **2** – funkce, která volá aktuální funkci<br /><br /> Pouze v [VSPerfReport](../profiling/vsperfreport.md) příkazového řádku sestavy.|  
|**Výhradní čas zablokování**|-Pro aktuální funkci čas, který tuto funkci bylo zablokováno provádění kódu v těle funkce. Čas zablokování ve funkcích volaných touto funkcí není zahrnut.<br />-Pro volající funkce část výhradní čas zablokování aktuální funkce, ke které došlo při volání této funkce aktuální funkce.<br />-Pro volaných funkce čas, který tuto funkci bylo zablokováno spouští vlastní kód, když tato funkce byla volána aktuální funkce. Čas zablokování podřízené funkcí volaných funkcí volaných není zahrnut.|  
|**% Výhradního času zablokování**|Procento všechny čas zablokování při spuštění profilace, která byla pro tuto funkci v tomto kontextu výhradní čas zablokování.|  
|**Výhradní spory**|-Pro aktuální funkci počet případů, kdy se tato funkce byla blokovat spouštění kódu v těle funkce. Tento počet sporů:, ke kterým došlo ve funkcích, které byly volány funkce nejsou zahrnuty.<br />-Pro volající funkci, počet výhradních sporů aktuální funkce, ke které došlo při volání této funkce aktuální funkce.<br />-Pro volaných funkce počet případů, kdy se tato funkce se zablokoval ve spouštění kódu v těle funkce, když se tato funkce byla volána aktuální funkce. Tento počet sporů:, ke kterým došlo ve funkcích volaných funkcí volaných nejsou zahrnuty.|  
|**% Výhradních sporů**|Procento všech sporů v profilování, které byly výhradních sporů pro tuto funkci v tomto kontextu.|  
|**Adresa funkce**|Adresa funkce nebo token.|  
|**Název funkce**|Plně kvalifikovaný název funkce.|  
|**Celkový čas zablokování**|-Pro aktuální funkci čas, který tuto funkci nebo jedna z funkcí, které byly volány touto funkcí bylo zablokováno provádění. Čas zablokování ve funkcích, které byly volány aktuální funkcí je v ceně.<br />-Pro volající funkci je čas aktuální funkce, ke které došlo při volání této funkce aktuální funkci zablokování část také zahrnuto.<br />-Pro volaných funkci čas, který tuto funkci nebo jedna z funkcí, které byla volána funkce bylo zablokováno spuštěný, když se tato funkce byla volána aktuální funkce. Čas zablokování ve funkcích, které byly volány volaných funkcí je v ceně.|  
|**% Celkového času zablokování**|Procento všechny čas zablokování při spuštění profilace, která byla pro tuto funkci v tomto kontextu celkový čas zablokování.|  
|**Celkově sporů**|-Pro aktuální funkci počet případů, kdy se tato funkce nebo jedna z funkcí, které volal funkci bylo zablokováno provádění. Tento počet sporů:, ke kterým došlo ve funkcích, které byly volány funkce jsou zahrnuty.<br />-Pro volající funkci, počet celkových sporů aktuální funkce, ke které došlo při volání této funkce aktuální funkce.<br />-Pro volaných funkce počet případů, kdy se tato funkce nebo jedna z funkcí, které volal funkci bylo zablokováno spuštěný, když se tato funkce byla volána aktuální funkce. Tento počet sporů:, ke kterým došlo ve funkcích volaných funkcí volaných jsou zahrnuty.|  
|**% Celkových sporů**|Procento všech sporů v profilování, které byly výhradních sporů pro tuto funkci v tomto kontextu.|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje funkci.|  
|**ID procesu**|ID procesu (PID) proces, ve kterém tento počet sporů: došlo.|  
|**Název procesu**|Název procesu.|  
|**Název kořenové funkce**|Název aktuální funkce. Pouze v [VSPerfReport](../profiling/vsperfreport.md) příkazového řádku sestavy.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení volající/volaný](../profiling/caller-callee-view.md)   
 [Zobrazení volající/volaný – vzorkování dat](../profiling/caller-callee-view-sampling-data.md)   
 [Zobrazení volající/volaný – data instrumentace paměti .NET](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Zobrazení volající/volaný – data vzorkování paměti .NET](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Zobrazení volající/volaný – data instrumentace](../profiling/caller-callee-view-instrumentation-data.md)