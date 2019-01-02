---
title: Zobrazení modulů – Data vzorkování paměti .NET | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Modules view
ms.assetid: 9c05b51a-8382-44cf-a8f7-3fabdd2e8f1b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: a099a30b0a87db8ebae46543528d9af9f28f497a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53823021"
---
# <a name="modules-view---net-memory-sampling-data"></a>Zobrazení modulů – data vzorkování paměti .NET
Moduly zobrazení data o přidělování paměti .NET, která jsou shromážděna pomocí metody vzorkování seskupuje data paměti moduly, které byly spuštěny během spuštění profilování. Každý modul je kořen hierarchického stromu. Funkce modulu jsou uvedené pod uzel modulu.  
  
 Čísla řádků zdrojového souboru příkazů, které přidělují paměť jsou uvedeny pod uzlem funkce a adresy pokynů, které provedl přidělení jsou uvedeny pod uzlem řádku. Zahrnuté a výhradní hodnoty jsou vždy stejné pro řádek dat a dat instrukce.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Název**|Název modulu, funkce, číslo řádku nebo adresa instrukce.|  
|**ID procesu**|ID procesu (PID) běhu profilování.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta modulu**|Cesta modulu.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Celkově přidělení**|-Pro funkci, celkový počet objektů, které se vytvořily ve funkci. Číslo obsahuje objekty, které byly vytvořeny ve funkcích, které byly volány touto funkcí.<br />-Pro modul počet objektů během spuštění profilování, které byly přiděleny při alespoň jednu funkci z modulu provádění. Číslo obsahuje objekty, které byly vytvořeny ve funkcích, které byly volány funkce modulu.<br />-Pro řádek nebo instrukce, celkový počet objektů, které byly přiděleny řádku nebo instrukci.|  
|**% Celkových přidělení**|Procento všech objektů, které byly přiděleny v profilování, která se celkově přidělení modulu, funkce, řádek nebo instrukci.|  
|**Výhradní přidělení**|-Pro funkci aktuální počet objektů, které se vytvořily při provádění funkce kódu těle funkce (to znamená, když funkce byla v horní části zásobníku volání). Číslo nezahrnuje objekty, které byly vytvořeny ve funkcích, které byly volány touto funkcí.<br />-Pro modul, součet výhradních přidělení funkce v modulu.<br />-Pro řádek nebo instrukce, celkový počet objektů, které byly vytvořeny podle tohoto řádku nebo instrukci.|  
|**% Výhradních přidělení**|Procento všech objektů, které byly přiděleny v profilování, které byly výhradních přidělení modulu, funkce, řádek nebo instrukci.|  
|**Celkově bajtů**|-Pro funkci, počet bajtů, které byly přiděleny funkcí. Číslo obsahuje počet bajtů, které byly přiděleny ve funkcích, které byly volány touto funkcí.<br />-Pro modul počet bajtů, které byly přiděleny během spuštění profilování, které byly přiděleny při alespoň jednu funkci z modulu provádění. Číslo obsahuje objekty, které byly vytvořeny ve všech funkcí, které byly volány funkce modulu.<br />-Pro řádek nebo instrukce, celkový počet objektů, které byly vytvořeny podle pokynů nebo řádku.|  
|**% Celkových bajtů**|Procento všech bajtů, které byly přiděleny v profilování, která se celkově bajtů modulu, funkce, řádek nebo instrukci.|  
|**Výhradní bajty**|-Pro funkci, celkový počet bajtů, které byly přiděleny funkcí. Číslo nezahrnuje bajtů, které byly přiděleny ve funkcích, které byly volány touto funkcí.<br />-Pro modul, součet výhradních bajtů, které byly přiděleny pomocí funkcí v modulu.<br />-Pro řádek nebo instrukce, celkový počet objektů, které byly přiděleny tento řádek nebo instrukci.|  
|**% Výhradních bajtů**|Procento všech bajtů, které byly přiděleny v profilování, které byly výhradních bajtů modulu, funkce, řádek nebo instrukci.|  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení modulů – instrumentace](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [Zobrazení modulů](../profiling/modules-view-sampling-data.md)   
 [Zobrazení modulů](../profiling/modules-view-instrumentation-data.md)