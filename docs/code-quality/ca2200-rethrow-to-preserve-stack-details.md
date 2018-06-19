---
title: 'CA2200: Znovu vyvolejte pro zachování podrobností zásobníku'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 688c10802b144c619b22b06309cec6dee5efc52e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919773"
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