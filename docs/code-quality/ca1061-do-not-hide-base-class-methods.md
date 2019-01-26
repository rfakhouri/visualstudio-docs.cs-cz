---
title: 'CA1061: Neskrývejte metody základní třídy'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 57da84c7109826ff08a60ca5f2b808facaaa5ce9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54995607"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: Neskrývejte metody základní třídy

|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Odvozený typ deklaruje metodu se stejným názvem a číslem stejné parametry jako jeden z jeho základních metod; jeden nebo více parametrů je základní typ odpovídající parametr v základní metoda; a všechny zbývající parametry mají typy, které jsou stejné pro odpovídající parametry v základní metodě.

## <a name="rule-description"></a>Popis pravidla
 Metodu v základním typu je skryta identicky pojmenovanou metodou v odvozeném typu při předpis parametrů odvozené metody se liší jenom podle typů, které jsou více slabě odvozený než odpovídající typy v podpisu parametr základní metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odebrat nebo přejmenovat metodu nebo změnit předpis parametrů, takže metoda neskryje základní metoda.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která porušuje pravidlo.

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]