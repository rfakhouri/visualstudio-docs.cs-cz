---
title: 'CA1035: Implementace ICollection mají členy silného typu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ICollectionImplementationsHaveStronglyTypedMembers
- CA1035
helpviewer_keywords:
- CA1035
- ICollectionImplementationsHaveStronglyTypedMembers
ms.assetid: ad404eb5-cf6a-44b7-b78a-8ebfb654bc7f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a20feb514b87f2906fd4db32dfb38d3d9b661999
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922833"
---
# <a name="ca1035-icollection-implementations-have-strongly-typed-members"></a>CA1035: Implementace ICollection mají členy silného typu

|||
|-|-|
|TypeName|ICollectionImplementationsHaveStronglyTypedMembers|
|CheckId|CA1035|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Veřejný nebo chráněný typ implementuje <xref:System.Collections.ICollection?displayProperty=fullName> , ale neposkytuje metodu se silným typem pro. <xref:System.Collections.ICollection.CopyTo%2A?displayProperty=fullName> Verze <xref:System.Collections.ICollection.CopyTo%2A> silného typu musí přijmout dva parametry a nemůže <xref:System.Array?displayProperty=fullName> mít ani pole <xref:System.Object?displayProperty=fullName> jako první parametr.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo vyžaduje <xref:System.Collections.ICollection> , aby implementace poskytovaly členy se silnými typy, aby uživatelé nemuseli přetypování argumentů <xref:System.Object> na typ při použití funkcí poskytovaných rozhraním. Toto pravidlo předpokládá, že typ, který <xref:System.Collections.ICollection> implementuje, tak, aby spravoval kolekci instancí typu, který je silnější než. <xref:System.Object>

 <xref:System.Collections.ICollection><xref:System.Collections.IEnumerable?displayProperty=fullName> implementuje rozhraní. Pokud se objekty v kolekci rozšiřují <xref:System.ValueType?displayProperty=fullName>, je nutné poskytnout <xref:System.Collections.IEnumerable.GetEnumerator%2A> člen silně typovaného typu, aby se zabránilo poklesu výkonu, který je způsoben zabalením. To není vyžadováno, pokud jsou objekty kolekce typu odkaz.

Chcete-li implementovat verzi silného typu člena rozhraní, implementujte členy rozhraní explicitně pomocí názvů ve formuláři `InterfaceName.InterfaceMemberName`, <xref:System.Collections.ICollection.CopyTo%2A>jako je například. Explicitní členové rozhraní používají datové typy, které jsou deklarovány rozhraním. Implementujte členy silného typu pomocí názvu člena rozhraní, například <xref:System.Collections.ICollection.CopyTo%2A>. Deklarovat členy silného typu jako veřejné a deklarovat parametry a návratové hodnoty, aby byly silného typu, který je spravován kolekcí. Silné typy nahrazují slabší typy <xref:System.Object> jako a <xref:System.Array> , které jsou deklarovány rozhraním.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, implementujte člen rozhraní explicitně (deklarujete jako <xref:System.Collections.ICollection.CopyTo%2A>). Přidejte veřejného člena silného typu deklarovaného `CopyTo`jako a pokaždé, když jako první parametr převezme pole silného typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačí upozornění z tohoto pravidla, Pokud implementujete novou kolekci založenou na objektech, jako je například binární strom, kde typy, které rozšiřuje novou kolekci, určují silný typ. Tyto typy by měly dodržovat toto pravidlo a zveřejnit členy silného typu.

## <a name="example"></a>Příklad
Následující příklad ukazuje správný způsob implementace <xref:System.Collections.ICollection>.

[!code-csharp[FxCop.Design.ICollectionStrongTypes#1](../code-quality/codesnippet/CSharp/ca1035-icollection-implementations-have-strongly-typed-members_1.cs)]

## <a name="related-rules"></a>Související pravidla
[CA1038: Enumerátory by měly být silného typu](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

[CA1039: Seznamy jsou silného typu](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Array?displayProperty=fullName>
- <xref:System.Collections.IEnumerable?displayProperty=fullName>
- <xref:System.Collections.ICollection?displayProperty=fullName>
- <xref:System.Object?displayProperty=fullName>