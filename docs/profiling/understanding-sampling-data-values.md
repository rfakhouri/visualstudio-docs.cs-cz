---
title: Porozumění hodnotám dat vzorkování | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method
- Profiling Tools, sampling
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: db8230c393ad18d72ff4d4d186d916c0e938996d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54978578"
---
# <a name="understand-sampling-data-values"></a>Vysvětlení hodnotám dat vzorkování

*Vzorkování* metoda profilování nástroje sady Visual Studio profilace přerušuje procesor počítače v nastavených intervalech a shromažďuje zásobník volání funkce. A *zásobníku volání* je dynamické strukturu, která uchovává informace o funkcích, které jsou spuštěny na procesor.

Profiler analýza určí, zda procesor spouští kód v cílovém procesu. Pokud procesor není spouštění kódu v cílovém procesu, se zahodí vzorku.

Pokud procesor spouští cílový kód, profiler zvýší čítače vzorků pro každou funkci v zásobníku volání. V době, která je vzorek odebírán jenom jednu funkci v zásobníku volání je právě spouští kód. Další funkce v zásobníku jsou nadřazené položky v hierarchii volání funkce, která čekají na své děti se vraťte.

Pro událost vzorku, profiler přírůstky *exkluzivní* počet funkce, která se právě probíhá jeho pokynů vzorků. Protože exkluzivní ukázky je také součástí celkové (*včetně*) ukázky funkce, včetně ukázkové počet aktuálně aktivních funkce se také zvýší.

 Profiler zvýší počet vzorků včetně všech funkcí v zásobníku volání.

## <a name="inclusive-samples"></a>Celkových vzorků

Celkový počet vzorků, které byly shromážděny během spuštění funkce cíl.

To zahrnuje ukázky, které byly shromážděny během přímé provádění kódu funkce a ukázky, které byly shromážděny během spuštění funkce podřízený, které jsou volány cílová funkce.

## <a name="exclusive-samples"></a>Výhradní vzorky

Počet vzorků, které byly shromážděny během spouštění s přímým přístupem pokyny cílová funkce.

Výhradní vzorky nezahrnují ukázky, které byly shromážděny během spuštění funkce, které jsou volány cílová funkce.

## <a name="inclusive-percent"></a>Celkové procento

Procento celkový počet celkových vzorků při spuštění profilace, které jsou celkových vzorků rozsah funkce nebo data.

## <a name="exclusive-percent"></a>Výhradní procent

Procento z celkového počtu výhradních vzorků při spuštění profilace, které jsou exkluzivní vzorky rozsah funkce nebo data.

## <a name="see-also"></a>Viz také:

[Postupy: Výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)  
[Analýza dat nástrojů pro měření výkonu](../profiling/analyzing-performance-tools-data.md)