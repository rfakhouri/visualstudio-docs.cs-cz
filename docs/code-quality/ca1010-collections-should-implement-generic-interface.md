---
title: 'CA1010: Kolekce musí implementovat obecné rozhraní'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
helpviewer_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c71912fdd70226e1b4be3c14be7c4e0bac26259d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779843"
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010: Kolekce musí implementovat obecné rozhraní

|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Typ implementuje <xref:System.Collections.IEnumerable?displayProperty=fullName> rozhraní, ale neimplementuje <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> rozhraní a obsahující .NET cíle sestavení. Toto pravidlo ignoruje typy, které implementují <xref:System.Collections.IDictionary?displayProperty=fullName>.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné typy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Použitelnost kolekce lze rozšířit implementací jednoho z rozhraní obecné kolekce. Potom kolekci lze použít k zaplnění typů obecných kolekcí, jako je následující:

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, implementujte jednu z následujících rozhraní obecné kolekce:

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>
- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>
- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla; použijte kolekci však budou omezenější.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1010.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example-violation"></a>Příklad porušení

Následující příklad ukazuje třídu (odkaz), která je odvozena z neobecné `CollectionBase` třídu, která poruší toto pravidlo.

[!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

Chcete-li opravit porušení tohoto pravidla, proveďte jednu z následujících akcí:

- Implementujte obecné rozhraní.
- Změňte základní třídy na typ, který již implementuje oba obecných a neobecných rozhraní, jako `Collection<T>` třídy.

## <a name="fix-by-base-class-change"></a>Opravit změnou základní třídy

V následujícím příkladu řeší porušení změnou základní třídy kolekce z neobecné `CollectionBase` třídy obecného `Collection<T>` (`Collection(Of T)` v jazyce Visual Basic) třídy.

[!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

Změna základní třídy již vydané třídy se považuje za rozbíjející změny stávajícím příjemcům.

## <a name="fix-by-interface-implementation"></a>Vyřešit tím, že implementace rozhraní

V následujícím příkladu řeší porušení implementací těmito obecnými rozhraními: `IEnumerable<T>`, `ICollection<T>`, a `IList<T>` (`IEnumerable(Of T)`, `ICollection(Of T)`, a `IList(Of T)` v jazyce Visual Basic).

[!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002: Nezveřejňujte obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1003: Použijte instance obecných události obslužné rutiny](../code-quality/ca1003-use-generic-event-handler-instances.md)
- [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Viz také:

- [Obecné typy](/dotnet/csharp/programming-guide/generics/index)