---
title: 'CA1307: Zadejte možnosti StringComparison'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ef2f8dbb265f0e5c82f2ea0adefc35d0721b4bd
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: Zadejte možnosti StringComparison
|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Operace porovnání řetězců používá přetížení metody, která není nastavena <xref:System.StringComparison> parametr.

## <a name="rule-description"></a>Popis pravidla
 Mnoho řetězec operace, nejdůležitější <xref:System.String.Compare%2A> a <xref:System.String.Equals%2A> metody, poskytují přetížení, které přijímá <xref:System.StringComparison> hodnota výčtu jako parametr.

 Vždy, když existuje přetížení této trvá <xref:System.StringComparison> parametr místo přetížení, které nevyžaduje tento parametr by použít. Tento parametr explicitně nastavením, váš kód je často učiněna umožní přehlednější a jednodušší správu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, změňte metody porovnávání řetězců na přetížení, které přijímají <xref:System.StringComparison> výčet jako parametr. Příklad: Změna `String.Compare(str1, str2)` k `String.Compare(str1, str2, StringComparison.Ordinal)`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné při do knihovny nebo aplikací je určen pro omezené místní cílovou skupinu a nebude proto lokalizované potlačit upozornění na toto pravidlo.

## <a name="see-also"></a>Viz také
 [Upozornění globalizace](../code-quality/globalization-warnings.md) [CA1309: použijte Řadový StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)