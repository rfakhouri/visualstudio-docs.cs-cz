---
title: Princip přidělování paměti a životnosti objektů hodnot | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- Profiling Tools, .NET memory method
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 463bb6510e304de8d9068e1c8d133c4ab331ea4f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54978669"
---
# <a name="understand-memory-allocation-and-object-lifetime-data-values"></a>Vysvětlení paměť přidělení a objekt hodnotám životnosti

*Alokaci paměti .NET* metodu profilace [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů pro profilaci sady shromažďuje informace o velikost a počet objektů, které byly vytvořeny během přidělování nebo zničeny v procesu uvolnění paměti a další informace o funkci *zásobníku volání* kdy došlo k události. A *zásobníku volání* je dynamické strukturu, která uchovává informace o funkcích, které jsou spuštěny na procesor.

Profilování paměti přerušuje procesor počítače při každém přidělení objektu rozhraní .NET Framework v profilované aplikaci. Při shromažďování dat o době životnosti objektu přerušuje profiler procesor po každém uvolnění paměti rozhraní .NET Framework. Pro každou funkci PROFILOVANÉHO a pro každý typ objektu se data agregují.

## <a name="allocation-data"></a>Data o přidělování

Při výskytu události .memory celkové počty a velikosti paměti přidělené nebo zničení objektů jsou zvětšeny.

Při výskytu události přidělení .memory profiler zvýší čítače vzorků pro každou funkci v zásobníku volání. Když se data shromažďují, pouze jedna funkce v zásobníku volání je aktuálně spouští kód v těle jeho funkce. Další funkce v zásobníku jsou nadřazené položky v hierarchii volání funkce, která čekají na funkce, které jsou volána k vrácení.

- Pro události přidělení, profiler přírůstky *exkluzivní* počet funkce, která se právě probíhá jeho pokynů vzorků. Protože exkluzivní ukázky je také součástí celkové (*včetně*) ukázky funkce, včetně ukázkové počet aktuálně aktivních funkce se také zvýší.

- Profiler zvýší počet vzorků včetně všech funkcí v zásobníku volání.

## <a name="lifetime-data"></a>Data o životním cyklu

Uvolňování paměti rozhraní .NET Framework spravuje přidělování a uvolňování paměti pro vaši aplikaci. Za účelem optimalizace výkonu systému uvolňování paměti spravované haldy rozdělen na tři generace: 0, 1 a 2. Doba běhu v systému uvolňování paměti uloží nové objekty 0. generace. Objekty, které byly zachovány při kolekce jsou povýšeny a uloženy v generace 1 a 2.

Získá systém uvolňování paměti podle rušení přidělení celé generace objektů. Pro objekty, které profilovaná aplikace vytvořena zobrazení doba života objektu zobrazí počet a velikost objektů a jeho generaci při jejich převzetí.