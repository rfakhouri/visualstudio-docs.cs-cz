---
title: 'CA1023: Indexery by neměly být multidimenzionální'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3864cbef5a5ba6c013d05112af46d641aa3c1634
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023: Indexery by neměly být multidimenzionální
|||
|-|-|
|TypeName|IndexersShouldNotBeMultidimensional|
|CheckId|CA1023|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ veřejné nebo chráněného obsahuje veřejný nebo chráněného indexer, který používá více než jeden index.

## <a name="rule-description"></a>Popis pravidla
 Indexery, který je indexované vlastnosti, měli používat jeden index. Multidimenzionální indexery může výrazně snížit použitelnost knihovny. Pokud návrh vyžaduje více indexů, znovu, jestli typ představuje logické datové úložiště. Pokud ne, použijte metodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, změnit návrh používat jedinou celé číslo nebo řetězec index nebo používat metodu místo indexeru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačíte upozornění na toto pravidlo až po pečlivě vzhledem k tomu potřeba nestandardní indexeru.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typu, `DayOfWeek03`, s vícerozměrných indexeru, která porušuje pravidlo. Indexer se dají považovat za typ převodu a proto je více správně viditelné jako metodu. Typ je nově navržený tak v `RedesignedDayOfWeek03` vyhovět pravidlo.

 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/VisualBasic/ca1023-indexers-should-not-be-multidimensional_1.vb)]
 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CPP/ca1023-indexers-should-not-be-multidimensional_1.cpp)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CSharp/ca1023-indexers-should-not-be-multidimensional_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1043: Použijte celočíselný nebo řetězcový argument pro indexery](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)

 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)