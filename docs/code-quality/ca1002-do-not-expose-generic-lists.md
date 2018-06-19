---
title: 'CA1002: Nezveřejňujte obecné seznamy'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotExposeGenericLists
- CA1002
helpviewer_keywords:
- CA1002
- DoNotExposeGenericLists
ms.assetid: 5caac810-1a79-47df-a27b-c46c5040bf34
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a2131ef8cb0b8f0ba540d7403d7c5f8dbb8b89df
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31901093"
---
# <a name="ca1002-do-not-expose-generic-lists"></a>CA1002: Nezveřejňujte obecné seznamy
|||
|-|-|
|TypeName|DoNotExposeGenericLists|
|CheckId|CA1002|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ obsahuje externě viditelné člena, který je <xref:System.Collections.Generic.List%601?displayProperty=fullName> typ, vrátí <xref:System.Collections.Generic.List%601?displayProperty=fullName> typu nebo jejichž podpis zahrnuje <xref:System.Collections.Generic.List%601?displayProperty=fullName> parametr.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Collections.Generic.List%601?displayProperty=fullName> je obecná kolekce, která je určená pro výkon a není dědičnosti. <xref:System.Collections.Generic.List%601?displayProperty=fullName> neobsahuje virtuální členy, které usnadňují změnit chování zděděné třídy. Následující obecné kolekce jsou navrženy pro dědičnosti a by měly být vystaveny místo <xref:System.Collections.Generic.List%601?displayProperty=fullName>.

-   <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>

-   <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>

-   <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, změňte <xref:System.Collections.Generic.List%601?displayProperty=fullName> typ na jednu z obecné kolekce, které je určená pro dědičnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud sestavení, které vyvolá toto upozornění by neměl být opakovaně použitelné knihovny není potlačení upozornění od tohoto pravidla. Například je bezpečné potlačit toto upozornění v aplikaci výkonu přizpůsobená kde získané výkonu výhody použití obecné seznamy.

## <a name="related-rules"></a>Související pravidla
 [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Použijte instance obecných obslužných rutin události](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Viz také
 [Obecné typy](/dotnet/csharp/programming-guide/generics/index)