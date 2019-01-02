---
title: 'CA2200: Znovu vyvolejte pro zachování podrobností zásobníku'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 6b52d6d9081827de764e47399dc09159d29ad149
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53915770"
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: Znovu vyvolejte pro zachování podrobností zásobníku

|||
|-|-|
|TypeName|RethrowToPreserveStackDetails|
|CheckId|CA2200|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina

Výjimka je znovu vyvolána a výjimky je jednoznačně uvedena v `throw` příkazu.

## <a name="rule-description"></a>Popis pravidla

Jakmile je vyvolána výjimka, je součástí informace, které vykonává trasování zásobníku. Trasování zásobníku je seznam hierarchii volání metody, který začíná metody, která vyvolá výjimku a končí u metody, která zachytí výjimku. Pokud výjimka je znovu vyvolána zadáním výjimky v `throw` prohlášení, trasování zásobníku se restartuje v aktuální metodě a dojde ke ztrátě seznam volání metody mezi původní metodou, která vyvolala výjimku a aktuální metoda. Chcete-li zachovat původní informace o trasování zásobníku s tím rozdílem, použijte `throw` příkaz bez zadání výjimku.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, výjimka znovu vyvolána bez explicitním zadáním výjimky.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad

Následující příklad ukazuje metodu, `CatchAndRethrowExplicitly`, který porušuje pravidla a metodu, `CatchAndRethrowImplicitly`, který splňuje pravidlo.

[!code-csharp[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/CSharp/ca2200-rethrow-to-preserve-stack-details_1.cs)]
[!code-vb[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/VisualBasic/ca2200-rethrow-to-preserve-stack-details_1.vb)]