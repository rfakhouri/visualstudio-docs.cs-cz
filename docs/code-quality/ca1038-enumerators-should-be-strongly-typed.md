---
title: 'CA1038: Enumerátory by měly být silného typu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
helpviewer_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
ms.assetid: 8919f526-d487-42a4-87dc-2b2ee25260c4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 426dbcd4116ee4ff52befbcbd8e9beea62e8cb72
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53954001"
---
# <a name="ca1038-enumerators-should-be-strongly-typed"></a>CA1038: Enumerátory by měly být silného typu

|||
|-|-|
|TypeName|EnumeratorsShouldBeStronglyTyped|
|CheckId|CA1038|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nebo chráněný typ implementuje <xref:System.Collections.IEnumerator?displayProperty=fullName> neposkytuje verzi silného typu, ale <xref:System.Collections.IEnumerator.Current%2A?displayProperty=fullName> vlastnost. Z tohoto pravidla vyjmuty jsou typy, které jsou odvozeny z následujících typů:

- <xref:System.Collections.CollectionBase?displayProperty=fullName>

- <xref:System.Collections.DictionaryBase?displayProperty=fullName>

- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo vyžaduje <xref:System.Collections.IEnumerator> implementace také poskytnout verzi silného typu <xref:System.Collections.IEnumerator.Current%2A> vlastnost tak, aby uživatelé nemusí při použití funkčnosti poskytované rozhraním přetypovávat návratovou hodnotu silného typu. Toto pravidlo předpokládá, že tento typ, který implementuje <xref:System.Collections.IEnumerator> obsahuje kolekci instancí typu silnějšího než <xref:System.Object>.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, implementovat rozhraní vlastnost explicitně (deklarujte ho jako `IEnumerator.Current`). Přidejte veřejnou verzi silného typu vlastnosti, které jsou deklarovány jako `Current`, a vrátí silně typovaných objektů.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, Pokud implementujete enumerátor založenou na objektech pro použití s kolekcí založenou na objektech, jako je například binární strom. Typy, které rozšiřují nová kolekce bude definovat silného typu výčtu a zpřístupnit vlastnost silného typu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje správný způsob implementace silného typu <xref:System.Collections.IEnumerator> typu.

 [!code-csharp[FxCop.Design.IEnumeratorStrongTypes#1](../code-quality/codesnippet/CSharp/ca1038-enumerators-should-be-strongly-typed_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1035: Implementace ICollection mají členy silného typu](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

 [CA1039: Seznamy jsou silného typu](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Collections.IEnumerator?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>