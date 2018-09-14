---
title: 'CA1052: Statický vlastník typů by měl být zapečetěný'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bc264b9e47fe9169c0b1ad9d3257323c437620f7
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550424"
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052: Statický vlastník typů by měl být zapečetěný

|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nebo chráněný typ obsahuje pouze statické členy a není deklarován [zapečetěné](/dotnet/csharp/language-reference/keywords/sealed) ([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) modifikátor.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo předpokládá, že typ, který obsahuje pouze statické členy nespouští zděděno, protože typ neposkytuje všechny funkce, která může být přepsána v odvozeném typu. Typ, který není určena k dědit by měly být označené `sealed` modifikátor zakázat jeho použití jako základního typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, označte typ jako `sealed`. Pokud cílíte [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 nebo novější, lepším řešením je označte typ jako `static`. Tímto způsobem se vyhnete nutnosti soukromý konstruktor zabránit vytváří třídu deklarovat.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla pouze v případě, že typ je navržen tak, aby se dědila. Chybí `sealed` modifikátor naznačuje, že je užitečné jako základní typ typu.

## <a name="example-of-a-violation"></a>Příkladem porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje typ, který porušuje pravidla.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
 [!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
 [!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>Oprava s statickém modifikátoru

### <a name="description"></a>Popis
 Následující příklad ukazuje, jak opravit porušení tohoto pravidla typu s označením `static` modifikátor.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1053: Statický vlastník typů by neměl mít konstruktory](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)
