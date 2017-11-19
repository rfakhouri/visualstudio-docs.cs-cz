---
title: "Volající - zobrazení volaný – Data kolizí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Caller/Callee view
ms.assetid: a18a1b1b-9b39-43c7-b1f3-708fd20376f6
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4ea2f63d3e1ee4b4c694fdc025484d85fad9d739
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="caller--callee-view----contention-data"></a>Volající / volaný – zobrazení – Data kolizí
Zobrazení volající/volaný zobrazí kolizí informace o vybrané funkce a její nadřazené a podřízené funkce. Zobrazení volající/volaný obsahuje tři mřížky.  
  
 **Funkci Current** se zobrazí v mřížce střední a zobrazuje informace o kolizí pro vybrané funkce. Hodnoty zahrnují všechny blokující kolizí pro funkci.  
  
 **Funkce, které volá funkci current** se zobrazí v horní mřížky, a zobrazuje jednotlivé příspěvky volajícího (nadřazené) funkce na hodnoty vybrané funkce (aktuální).  
  
 **Funkce, které byly volá funkci current** se zobrazí v mřížce dole, a zobrazuje informace o kolizí pro volaný (podřízená) funkce vybrané funkce při volání funkce podřízené aktuální funkcí.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Typ**|Kontext funkce:<br /><br /> -   **0** -aktuální funkce<br />-   **1** -funkci, která volá funkci current<br />-   **2** -funkci, která volá funkci current<br /><br /> Pouze v [vsperfreport –](../profiling/vsperfreport.md) příkazového řádku sestavy.|  
|**Výhradní blokované čas**|-Pro aktuální funkci čas, který tuto funkci byl zablokován spuštěním kódu v těle funkce. Blokované čas v funkce volané funkce není součástí.<br />-Pro volající funkce část výhradní blokované době aktuální funkci, která došlo k chybě při volání této funkce aktuální funkce.<br />-Pro volaný funkce, době, provádění vlastní kód, když tato funkce byla zavolána funkce aktuální tuto funkci byl zablokován. Blokované čas v podřízené funkce volané funkce volaný není součástí.|  
|**Výhradní blokované čas: %**|Procento všech blokovaných času v profilaci spuštění, který byl výhradní blokované čas pro tuto funkci v tomto kontextu.|  
|**Výhradní kolizí**|-Pro aktuální funkci Počet pokusů, které tuto funkci byl zablokován spuštěním kódu v těle funkce. Kolizí, k nimž došlo v funkce, které byly volá funkci nejsou zahrnuty.<br />-Pro volající funkce počet výhradní kolizí aktuální funkci, která došlo k chybě při volání této funkce aktuální funkce.<br />-Pro funkci volaný, počet pokusů, které tuto funkci byl zablokován spuštěním kódu v těle funkce, když tato funkce byla zavolána funkce aktuální. Kolizí, k nimž došlo v funkce volané funkce volaný nejsou zahrnuty.|  
|**% Výhradní kolizí**|Procento všech kolizí v profilaci spuštění, které byly výhradní kolizí pro tuto funkci v tomto kontextu.|  
|**Adresa funkce**|Adresa funkce nebo token.|  
|**Název funkce**|Plně kvalifikovaný název funkce.|  
|**Blokované čas (včetně).**|-Pro aktuální funkci čas, který tuto funkci nebo jedna z funkcí, které byly volá tuto funkci byl zablokován provádění. Blokované čas v funkce, které byly volá funkci current je zahrnuta.<br />-Pro volající funkci část včetně blokována čas aktuální funkci, která došlo k chybě při volání této funkce aktuální funkce.<br />-Pro funkci volaný čas, který tuto funkci nebo jedna z funkcí, které byla zavolána funkce byl zablokován prováděny, kdy tato funkce byla zavolána aktuální fungovat. Blokované čas v funkce, které byly volá funkci volaný je zahrnuta.|  
|**Včetně blokované čas: %**|Procento všech blokovaných času v profilaci spuštění, který byl včetně blokované čas pro tuto funkci v tomto kontextu.|  
|**Kolizí (včetně).**|-Pro aktuální funkci Počet pokusů, které tuto funkci nebo jedna z funkcí, které byly volá funkci byl zablokován provádění. Kolizí, k nimž došlo v funkce, které byly volá funkci jsou zahrnuty.<br />-Pro volající funkce počet včetně kolizí aktuální funkci, která došlo k chybě při volání této funkce aktuální funkce.<br />-Pro funkci volaný, počet pokusů, které tuto funkci nebo jeden z funkcí, které byly volá funkci byl zablokován prováděny, kdy tato funkce byla zavolána funkce aktuální. Kolizí, k nimž došlo v funkce volané funkce volaný jsou zahrnuty.|  
|**% Kolizí (včetně).**|Procento všech kolizí v profilaci spuštění, které byly výhradní kolizí pro tuto funkci v tomto kontextu.|  
|**Číslo řádku – funkce**|Číslo řádku spuštění této funkce ve zdrojovém souboru.|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta modulu**|Cesta modul, který obsahuje funkce.|  
|**ID procesu**|ID procesu (PID) procesu, ve kterém kolizí došlo.|  
|**Název procesu**|Název procesu.|  
|**Název kořenové – funkce**|Název aktuální funkce. Pouze v [vsperfreport –](../profiling/vsperfreport.md) příkazového řádku sestavy.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Volající/volaný – zobrazení](../profiling/caller-callee-view.md)   
 [Volající / volaný – zobrazení – Data vzorkování](../profiling/caller-callee-view-sampling-data.md)   
 [Zobrazení volající/volaný – Data instrumentace paměti NET](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Zobrazení volající/volaný – Data vzorkování paměti .NET](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Zobrazení volající/volaný – Data instrumentace](../profiling/caller-callee-view-instrumentation-data.md)