---
title: 'CA1307: Zadejte možnosti StringComparison | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 292e174feeb123c640306bc8ef3ffedd7e8847f6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68200348"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: Určete StringComparison
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Operace porovnání řetězců používá přetížení metody, které nenastavuje <xref:System.StringComparison> parametru.

## <a name="rule-description"></a>Popis pravidla
 Mnoho řetězec operace, nejdůležitější <xref:System.String.Compare%2A> a <xref:System.String.Equals%2A> metody, poskytují přetížení přijímající <xref:System.StringComparison> hodnotu výčet jako parametr.

 Vždy, když existuje přetížení této přijímá <xref:System.StringComparison> parametr, by mělo být používáno namísto přetížení, které tento parametr nepřijímá. Explicitním nastavením tohoto parametru, váš kód je často vytvořené podřazenými a jednodušší správu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte na přetížení metod pro porovnávání řetězců <xref:System.StringComparison> výčet jako parametr. Příklad: Změna `String.Compare(str1, str2)` k `String.Compare(str1, str2, StringComparison.Ordinal)`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, když aplikace a knihovny je určená pro omezené místní cílovou skupinu a nebude proto být lokalizována.

## <a name="see-also"></a>Viz také
 [Upozornění globalizace](../code-quality/globalization-warnings.md) [CA1309: Použijte Řadový StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)
