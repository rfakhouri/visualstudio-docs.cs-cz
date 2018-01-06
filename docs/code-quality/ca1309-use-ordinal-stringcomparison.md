---
title: "CA1309: Použijte Řadový StringComparison | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cf913eea3f156595c9b9194b3d8a74e71b848367
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 [Upozornění globalizace](../code-quality/globalization-warnings.md)   
 [CA1307: Zadejte možnosti StringComparison](../code-quality/ca1307-specify-stringcomparison.md)