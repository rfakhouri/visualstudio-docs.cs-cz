---
title: 'CA1309: Použijte řadový StringComparison'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ebea0208beddebb82484297eb990baa9b22c58e8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309: Použijte řadový StringComparison
|||
|-|-|
|TypeName|UseOrdinalStringComparison|
|CheckId|CA1309|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Operace porovnání řetězců, které je nonlinguistic nenastaví <xref:System.StringComparison> buď parametr **pořadí** nebo **OrdinalIgnoreCase**.

## <a name="rule-description"></a>Popis pravidla
 Mnoho řetězec operace, nejdůležitější <xref:System.String.Compare%2A?displayProperty=fullName> a <xref:System.String.Equals%2A?displayProperty=fullName> metody, teď poskytují přetížení, které přijímá <xref:System.StringComparison?displayProperty=fullName> hodnota výčtu jako parametr.

 Pokud zadáte buď **StringComparison.Ordinal** nebo **StringComparison.OrdinalIgnoreCase**, porovnání řetězců bude nonlinguistic. To znamená funkce, které jsou specifické pro přirozeného jazyka ignorují při rozhodování porovnání. To znamená, že rozhodnutí, která jsou založená na porovnání jednotlivých bajtů a ignorovat velká a malá písmena nebo ekvivalenční tabulek, které jsou parametry podle jazykové verze. V důsledku toho podle explicitně nastavení parametru na buď **StringComparison.Ordinal** nebo **StringComparison.OrdinalIgnoreCase**, kódu často získá rychlost, zvyšuje správnost a stane spolehlivější.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, změňte metodu porovnání řetězce na přetížení, které přijímá <xref:System.StringComparison?displayProperty=fullName> výčet jako parametr a zadejte buď **pořadí** nebo **OrdinalIgnoreCase**. Můžete například změnit `String.Compare(str1, str2)` k `String.Compare(str1, str2, StringComparison.Ordinal)`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné při knihovny nebo aplikací je určený pro omezené místní cílovou skupinu, nebo pokud sémantiku aktuální jazykové verze slouží potlačit upozornění na toto pravidlo.

## <a name="see-also"></a>Viz také
 [Upozornění globalizace](../code-quality/globalization-warnings.md) [CA1307: Zadejte možnosti StringComparison](../code-quality/ca1307-specify-stringcomparison.md)