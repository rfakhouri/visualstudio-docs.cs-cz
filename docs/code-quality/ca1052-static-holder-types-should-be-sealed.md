---
title: 'CA1052: Statické typy vlastníků by měly být zapečetěné'
ms.date: 11/09/2018
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 36bd459f2a9f7300328aadd3509530f4802e71cd
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55922447"
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052: Statické typy vlastníků by měly být zapečetěné

|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Veřejný nebo chráněný, není abstraktní typ obsahuje pouze statické členy a není deklarován [zapečetěné](/dotnet/csharp/language-reference/keywords/sealed) ([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) modifikátor.

## <a name="rule-description"></a>Popis pravidla

CA1052 pravidlo předpokládá, že typ, který obsahuje pouze statické členy nespouští zděděno, protože typ neposkytuje všechny funkce, která může být přepsána v odvozeném typu. Typ, který není určena k dědit by měly být označené `sealed` nebo `NotInheritable` modifikátor zakázat jeho použití jako základního typu. Toto pravidlo se neaktivuje pro abstraktní třídy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, označte typ jako `sealed` nebo `NotInheritable`. Pokud cílíte rozhraní .NET Framework 2.0 nebo novější, je lepším řešením pro označení typu jako `static` nebo `Shared`. Tímto způsobem není nutné deklarovat soukromý konstruktor třídy zabránit vytváří.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačit upozornění tohoto pravidla pouze v případě, že typ je navržen tak, aby se dědila. Chybí `sealed` nebo `NotInheritable` modifikátor naznačuje, že je užitečné jako základní typ typu.

## <a name="example-of-a-violation"></a>Příkladem porušení

Následující příklad ukazuje typ, který porušuje pravidla.

[!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
[!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
[!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>Oprava s statickém modifikátoru

Následující příklad ukazuje, jak opravit porušení tohoto pravidla typu s označením `static` modifikátor v C#.

[!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]

## <a name="related-rules"></a>Související pravidla

[CA1053: Statický vlastník typů by neměly mít konstruktory](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)