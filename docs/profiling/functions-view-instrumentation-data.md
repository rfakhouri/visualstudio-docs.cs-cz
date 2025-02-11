---
title: Zobrazení funkcí – Data instrumentace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Function view
ms.assetid: 595d91c8-a42b-4644-85b8-39e8140a5dfe
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 34585e212acfd52186e12e8b38293178cc77c585
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62969690"
---
# <a name="functions-view---instrumentation-data"></a>Zobrazení funkcí – data instrumentace
Zobrazení sestav funkce uvádí data profilování podle názvu funkce.

## <a name="general"></a>Obecné
 Obecné sloupce rozpoznat funkci zobrazení řádku.

|Sloupec|Popis|
|------------|-----------------|
|**Název funkce**|Název funkce.|
|**Adresa funkce**|Adresa funkce.|
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|
|**Počet volání**|Celkový počet volání provedených touto funkcí.|
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|
|**Název modulu**|Název modulu, který obsahuje funkci.|
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje funkci.|
|**ID procesu**|ID procesu (PID) běhu profilování.|
|**Název procesu**|Název procesu.|
|**Výhradní čas režie**|Časová náročnost této funkce, která způsobuje instrumentace. Ve funkcích, které volal funkci neobsahoval režijní náklady. Režie byla odečtena od vylučuje všechny časy.|
|**Celkový čas režie**|Časová náročnost této funkce a její podřízené funkce, jež je způsobena instrumentace. To zahrnuje režijní náklady na ve funkcích, které byly volány funkce. Test zatížení byla odečtena od fiskálního (včetně).|

## <a name="elapsed-inclusive-values"></a>Uplynulý včetně hodnoty
 Uplynulý včetně hodnoty označuje datum a čas, který funkce byla v zásobníku volání. Čas zahrnují čas, který byl stráven ve funkcích, které byly volány tak, že funkce a čas, který byl stráven voláními do operačního systému, například vstupně výstupní operace a přepnutí kontextu.

|Sloupec|Popis|
|------------|-----------------|
|**Uplynulý celkový čas**|Celkový uplynulý celkový čas všechna volání této funkce.|
|**% Uplynulého celkového času**|Procento celkového uplynulý celkový čas, který byl stráven v uplynulý celkový čas této funkce spuštění profilování.|
|**Průměrný uplynulý celkový čas**|Průměr uplynulý celkový čas volání této funkce.|
|**Maximální uplynulý celkový čas**|Maximální uplynulý celkový čas volání této funkce.|
|**Minimální uplynulý celkový čas**|Minimální uplynulý celkový čas volání této funkce.|

## <a name="elapsed-exclusive-values"></a>Uplynulý výhradní hodnoty
 Uplynulý výhradní hodnoty označuje datum a čas, že funkce byla provádění kódu v těle funkce, to znamená, když funkce byla v horní části zásobníku volání. Čas zahrnují čas, který byl stráven ve volání do operačního systému, jako jsou přepínače kontextu a vstupně výstupní operace, ale nezahrnuje čas, který byl stráven ve funkcích, které byly volány funkce.

|Sloupec|Popis|
|------------|-----------------|
|**Uplynulý výhradní čas**|Celkový uplynulý výhradní čas všechna volání této funkce.|
|**% Uplynulého výhradního času**|Procentuální podíl celkového počtu uplynulý výhradní čas spuštění profilování, která se využilo na celkový uplynulý výhradní čas této funkce.|
|**Průměrný uplynulý výhradní čas**|Průměr uplynulý výhradní čas volání této funkce.|
|**Maximální uplynulý výhradní čas**|Maximální uplynulý výhradní čas volání této funkce.|
|**Minimální uplynulý výhradní čas**|Minimální uplynulý výhradní čas volání této funkce.|

## <a name="application-inclusive-values"></a>Aplikace (včetně) hodnot
 Aplikace (včetně) hodnot označuje datum a čas, který funkce byla v zásobníku volání. Čas nezahrnuje čas, který byl stráven ve volání do operačního systému, jako jsou přepínače kontextu a vstupně výstupní operace, ale čas, který byl stráven zahrnovat ve funkcích, které byly volány funkce.

|Sloupec|Popis|
|------------|-----------------|
|**Celkový čas aplikace**|Celkový čas aplikace celkový počet všech volání této funkce.|
|**% Celkového času aplikace**|Procento celkového uplynulý celkový čas, který byl stráven v celkový čas celkový aplikace této funkce spuštění profilování.|
|**Průměrný celkový čas aplikace**|Celkový čas průměrná aplikace volání této funkce.|
|**Maximální celkový čas aplikace**|Celkový čas aplikace maximální volání této funkce.|
|**Minimální celkový čas aplikace**|Celkový čas aplikace minimální volání této funkce.|

## <a name="application-exclusive-values"></a>Výhradní hodnoty aplikace
 Výhradní hodnoty, které aplikaci označuje datum a čas, který funkce byla spuštěna přímo v horní části zásobníku volání. Čas nezahrnuje čas, který byl stráven ve volání do operačního systému, například přepnutí kontextu a vstupně výstupní operace a nezahrnuje čas, který byl stráven ve funkcích, které byly volány funkce.

|Sloupec|Popis|
|------------|-----------------|
|**Výhradní čas aplikace**|Výhradní čas aplikace celkový počet všech volání této funkce.|
|**% Výhradního času aplikace**|Procentuální podíl celkového počtu uplynulý výhradní čas spuštění profilování, který byl stráven v výhradní čas aplikace celkový této funkce.|
|**Průměrný výhradní čas aplikace**|Výhradní čas aplikace průměrné volání této funkce.|
|**Maximální výhradní čas aplikace**|Výhradní čas aplikace maximální volání této funkce.|
|**Minimální výhradní čas aplikace**|Výhradní čas aplikace minimální volání této funkce.|

## <a name="see-also"></a>Viz také:
- [Postupy: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)
- [Zobrazení funkcí](../profiling/functions-view-sampling-data.md)
- [Zobrazení funkcí – vzorkování](../profiling/functions-view-dotnet-memory-sampling-data.md)
- [Zobrazení funkcí – instrumentace](../profiling/functions-view-dotnet-memory-instrumentation-data.md)