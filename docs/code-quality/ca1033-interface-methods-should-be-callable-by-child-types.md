---
title: 'CA1033: Metody rozhraní by měly být volatelné podřízenými typy'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 10db644fe4cf65a7336ef8bd50dcf62e072e1c46
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922958"
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033: Metody rozhraní by měly být volatelné podřízenými typy

|||
|-|-|
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|
|CheckId|CA1033|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
Nezapečetěný externě viditelný typ poskytuje explicitní implementaci metod veřejného rozhraní a neposkytuje alternativní externě viditelnou metodu stejného názvu.

## <a name="rule-description"></a>Popis pravidla
Vezměte v úvahu základní typ, který explicitně implementuje metodu veřejného rozhraní. Typ, který je odvozen od základního typu, má přístup k zděděné metodě rozhraní pouze prostřednictvím odkazu na aktuální instanci (`this` v C#), která je převedena na rozhraní. Pokud odvozený typ znovu implementuje (explicitně) zděděnou metodu rozhraní, k základní implementaci již nelze přivodit. Volání prostřednictvím aktuální reference instance vyvolá odvozenou implementaci; To způsobí rekurzi a případné přetečení zásobníku.

Toto pravidlo neoznamuje porušení explicitní implementace, <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> Pokud je k dispozici externě viditelný `Close()` nebo `System.IDisposable.Dispose(Boolean)` metoda.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, implementujte novou metodu, která zveřejňuje stejnou funkci a je viditelná pro odvozené typy nebo se změní na neexplicitní implementaci. V případě, že je zásadní změna přijatelné, alternativou je vytvořit zapečetěný typ.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Je bezpečné potlačit upozornění z tohoto pravidla, pokud je k dispozici externě viditelná metoda, která má stejnou funkci, ale jiný název než explicitně implementovaná metoda.

## <a name="example"></a>Příklad
Následující příklad ukazuje typ, `ViolatingBase`, který porušuje pravidlo a typ, `FixedBase`,, který ukazuje opravu pro porušení.

[!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../code-quality/codesnippet/CSharp/ca1033-interface-methods-should-be-callable-by-child-types_1.cs)]

## <a name="see-also"></a>Viz také:
[Rozhraní](/dotnet/csharp/programming-guide/interfaces/index)