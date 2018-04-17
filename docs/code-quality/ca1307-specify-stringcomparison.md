---
title: 'CA1307: Zadejte možnosti StringComparison | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: b8d51d55c1528af38c142c115165278503bc50fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 [Upozornění globalizace](../code-quality/globalization-warnings.md)   
 [CA1309: Použijte řadový StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)