---
title: "CA1043: Použijte celočíselný nebo řetězcový argument pro indexery | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a75e3cc167f98763cfc0a1747b48e69987a9610b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: Použijte celočíselný nebo řetězcový argument pro indexery
|||  
|-|-|  
|TypeName|UseIntegralOrStringArgumentForIndexers|  
|CheckId|CA1043|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ veřejné nebo chráněného obsahuje veřejný nebo chráněného indexer, jiné než používající typ indexu <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, nebo <xref:System.String?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Indexery, který je indexované vlastnosti, musí používat typy celé číslo nebo řetězec pro index. Tyto typy jsou obvykle používány pro indexování datové struktury a zvýšit použitelnost knihovny. Použití <xref:System.Object> typu by se měly omezit na tyto případy, kdy konkrétní typ celé číslo nebo řetězec nelze zadat v době návrhu. Pokud návrh vyžaduje další typy pro index, znovu, jestli typ představuje logické datové úložiště. Pokud ho nepředstavuje logické datové úložiště, použijte metodu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, změňte index na typ celé číslo nebo řetězec nebo používat metodu místo indexeru.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo až po pečlivě vzhledem k tomu potřeba nestandardní indexeru.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje indexer, který používá <xref:System.Int32> index.  
  
 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1023: Indexery by neměly být multidimenzionální](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)  
  
 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)