---
title: 'CA1309: Použijte řadový StringComparison'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b00accdbdb08e4267bbca2b7e5fab8002f539f1d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546476"
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309: Použijte řadový StringComparison

|||
|-|-|
|TypeName|UseOrdinalStringComparison|
|CheckId|CA1309|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Který je nelingvistická operace porovnání řetězců nemá nastaven <xref:System.StringComparison> buď parametr **pořadí** nebo **OrdinalIgnoreCase**.

## <a name="rule-description"></a>Popis pravidla
 Mnoho operací, řetězec je nejdůležitější <xref:System.String.Compare%2A?displayProperty=fullName> a <xref:System.String.Equals%2A?displayProperty=fullName> metody, teď poskytují přetížení přijímající <xref:System.StringComparison?displayProperty=fullName> hodnotu výčet jako parametr.

 Pokud zadáte buď **StringComparison.Ordinal** nebo **StringComparison.OrdinalIgnoreCase**, je nejazyková porovnání řetězců. To znamená funkce, které jsou specifické pro přirozený jazyk se ignorují porovnání se při rozhodování. Ignorování funkcí přirozeného jazyka znamená, že rozhodnutí, která jsou založené na porovnání jednotlivých bajtů a ne na malých a velkých písmen nebo ekvivalence tabulky, které jsou parametrizovány podle jazykové verze. V důsledku toho podle explicitním nastavením parametru na buď **StringComparison.Ordinal** nebo **StringComparison.OrdinalIgnoreCase**, váš kód často získá rychlost, zvyšuje správnosti a změní spolehlivější.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte metodu porovnání řetězce na přetížení přijímající <xref:System.StringComparison?displayProperty=fullName> výčet jako parametr a zadat buď **pořadí** nebo **OrdinalIgnoreCase**. Například změnit `String.Compare(str1, str2)` k `String.Compare(str1, str2, StringComparison.Ordinal)`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, když aplikace a knihovny je určená pro omezené místní cílové skupiny, nebo když sémantiku aktuální jazyková verze by měla sloužit.

## <a name="see-also"></a>Viz také:

- [Upozornění globalizace](../code-quality/globalization-warnings.md)
- [CA1307: Zadejte možnosti StringComparison](../code-quality/ca1307-specify-stringcomparison.md)