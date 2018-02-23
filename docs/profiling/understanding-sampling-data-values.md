---
title: "Porozumění hodnotám dat vzorkování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sampling profiling method
- Profiling Tools, sampling
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5793fea089bd5efa53bdb356597fd7f176aa4ba0
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="understanding-sampling-data-values"></a>Porozumění hodnotám dat vzorkování

*Vzorkování* metoda Visual Studio Tools profilace profilace přerušují procesor počítače v nastavených intervalech a shromažďuje zásobníku volání funkce. A *zásobník volání* je dynamická struktura, která ukládá informace o funkcích, které jsou prováděny na procesor.

Analýza profileru určí, jestli je procesor provádění kódu v tento cílový proces. Pokud procesor není spuštěním kódu v procesu cíl, ukázce se zahodí.

Pokud procesor spouští cílový kód, profileru zvýší počet ukázka pro jednotlivé funkce v zásobníku volání. V době, vzorku jenom jednu funkci v zásobníku volání je aktuálně provádění kódu. Jiných funkcí v zásobníku jsou rodičů v hierarchii volání funkce, které čekají na jejich podřízené vrátit.

Pro událost vzorku, profileru zvýší *výhradní* počet funkce, která právě probíhá jeho pokyny vzorků. Protože výhradní ukázka je také součástí celkové (*včetně*) se taky zvýší ukázky funkce, včetně ukázkové počet aktuálně aktivních funkce.

 Profileru zvýší počet vzorků včetně všech funkcí v zásobníku volání.

## <a name="inclusive-samples"></a>Ukázky (včetně).

Celkový počet vzorků, které byly shromážděny během provádění funkce cíl.

To zahrnuje vzorků, které byly shromážděny během přímé provádění kódu funkce a ukázky, které byly shromážděny během provádění podřízené funkce, které se nazývají funkcí cíl.

## <a name="exclusive-samples"></a>Výhradní ukázky

Počet vzorků, které byly shromážděny během přímé provádění pokynů funkce cíl.

Výhradní ukázky nezahrnují vzorků, které byly shromážděny během provádění funkcí, které se nazývají funkcí cíl.

## <a name="inclusive-percent"></a>V procentech (včetně).

Procento celkového počtu v profilaci spustit včetně vzorků, které jsou včetně ukázky rozsahu funkce nebo data.

## <a name="exclusive-percent"></a>Výhradní procent

Procento celkového počtu v profilaci spustit výhradní vzorků, které jsou výhradní ukázky rozsahu funkce nebo data.

## <a name="see-also"></a>Viz také

[Postupy: výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)  
[Analýza výkonu nástrojů pro Data](../profiling/analyzing-performance-tools-data.md)