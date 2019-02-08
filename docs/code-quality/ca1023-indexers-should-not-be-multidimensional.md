---
title: 'CA1023: Indexery by neměly být multidimenzionální'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ef3afd9dda70d02698abec5459b36e6acc2c5ed0
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55924541"
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023: Indexery by neměly být multidimenzionální

|||
|-|-|
|TypeName|IndexersShouldNotBeMultidimensional|
|CheckId|CA1023|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nebo chráněný typ obsahuje veřejná nebo chráněná indexer, který používá více než jeden index.

## <a name="rule-description"></a>Popis pravidla
 Indexery, tj. indexované vlastnosti, by měly používat jediný index. Vícerozměrné indexery mohou výrazně snížit použitelnost knihovny. Pokud návrhu vyžaduje více indexů, zvažte, zda typ představuje logické datové úložiště. Pokud ne, použijte metodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte návrhu a použít jedinou celé číslo nebo řetězec indexu nebo použijte metodu místo indexeru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla až po pečlivého zvážení potřebu nestandardní indexeru.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, `DayOfWeek03`, pomocí multidimenzionální indexeru, který porušuje pravidla. Indexer se dají považovat za typ převodu a proto je více správně vystavena jako metoda. Typ je upraveno `RedesignedDayOfWeek03` splňovat pravidla.

 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/VisualBasic/ca1023-indexers-should-not-be-multidimensional_1.vb)]
 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CPP/ca1023-indexers-should-not-be-multidimensional_1.cpp)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CSharp/ca1023-indexers-should-not-be-multidimensional_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1043: Použijte celočíselný nebo řetězcový argument pro indexery](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)

 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)