---
title: 'CA1307: Zadejte možnosti StringComparison | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
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
ms.openlocfilehash: 2c96b8c895106337a8578b6662c0e61830b38f55
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902948"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: Zadejte možnosti StringComparison
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1307: Zadejte StringComparison](https://docs.microsoft.com/visualstudio/code-quality/ca1307-specify-stringcomparison).

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
 [Upozornění globalizace](../code-quality/globalization-warnings.md) [CA1309: použijte Řadový StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)



