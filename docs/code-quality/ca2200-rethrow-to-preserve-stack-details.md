---
title: "CA2200: Znovu vyvolejte pro zachování podrobností zásobníku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ca2e6e61b88d4d8aaccd4784e1b521e0cbb48bd4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: Znovu vyvolejte pro zachování podrobností zásobníku
|||  
|-|-|  
|TypeName|RethrowToPreserveStackDetails|  
|CheckId|CA2200|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Výjimkou je znovu a výjimka je výslovně uveden v `throw` příkaz.  
  
## <a name="rule-description"></a>Popis pravidla  
 Jakmile je vyvolána výjimka, je součástí informací o krokem trasování zásobníku. Trasování zásobníku je seznam hierarchie volání metoda, která začíná metodu, která vyvolala výjimku a končí metodu, která zachytí výjimky. Pokud je tak, že zadáte výjimka v znovu vyvolána výjimka `throw` prohlášení, trasování zásobníku se restartuje v aktuální metoda a dojde ke ztrátě seznam volání metod mezi původní metoda, která vrátila výjimku a aktuální metoda. Chcete-li zachovat původní informace trasování zásobníku s tou výjimkou, použijte `throw` příkaz bez zadání výjimku.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, znovu bez zadání výjimka explicitně vyvolání výjimky.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, `CatchAndRethrowExplicitly`, která porušuje pravidlo a metodu, `CatchAndRethrowImplicitly`, který splňuje pravidlo.  
  
 [!code-csharp[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/CSharp/ca2200-rethrow-to-preserve-stack-details_1.cs)]
 [!code-vb[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/VisualBasic/ca2200-rethrow-to-preserve-stack-details_1.vb)]