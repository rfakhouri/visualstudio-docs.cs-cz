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
ms.openlocfilehash: 9a253e54dd3da4ddc2d9c7788582f145605cc527
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632471"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: Zadejte možnosti StringComparison
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1307: Zadejte StringComparison](https://docs.microsoft.com/visualstudio/code-quality/ca1307-specify-stringcomparison).  
  
TypeName | SpecifyStringComparison |  
| ID kontroly | CA1307 |  
| Kategorie | Microsoft.Globalization|  
| Zásadní změna | Ukončování bez |  
  
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
 [Upozornění globalizace](../code-quality/globalization-warnings.md)   
 [CA1309: Použijte řadový StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)



