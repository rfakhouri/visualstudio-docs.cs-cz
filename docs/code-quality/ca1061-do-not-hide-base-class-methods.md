---
title: 'CA1061: Neskrývejte metody třídy base'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3fc3be40a81d29da27e9a44d72cca4e78b37abbf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: Neskrývejte metody třídy base
|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Odvozený typ deklaruje metodu se stejným názvem a stejný počet parametrů jako jedna z jeho základní metody; jeden nebo více parametrů je základní typ odpovídající parametr v metodě základní; a všechny ostatní parametry mají typy, které jsou stejné jako odpovídající parametry v základní metody.

## <a name="rule-description"></a>Popis pravidla
 Metoda v základním typu skrytý stejně jako s názvem metodou v odvozeném typu, pokud parametr podpis odvozené metoda se liší pouze podle typů, které jsou více slabě odvozené než odpovídající typy v parametru podpis základní metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, odebrat nebo přejmenovat metodu nebo změňte parametr podpis tak, aby metoda není skrýt základní metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která porušuje pravidlo.

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]