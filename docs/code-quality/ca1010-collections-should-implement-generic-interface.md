---
title: 'CA1010: Kolekce musí implementovat obecné rozhraní'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cb43481b80726171414fab6b6a65fee8a5e29cb0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010: Kolekce musí implementovat obecné rozhraní
|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Implementuje externě viditelného typu <xref:System.Collections.IEnumerable?displayProperty=fullName> rozhraní, ale neimplementuje <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> rozhraní a obsahující sestavení cílů [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]. Toto pravidlo ignoruje typy, které implementují <xref:System.Collections.IDictionary?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 Použitelnost kolekce lze rozšířit implementací jednoho z rozhraní obecné kolekce. Potom kolekce slouží k naplnění obecné typy kolekcí například následující:

-   <xref:System.Collections.Generic.List%601?displayProperty=fullName>

-   <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>

-   <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, implementujte jednu z následujících rozhraní pro obecné kolekce:

-   <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>

-   <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>

-   <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo; kolekce však bude mít více omezené použití.

## <a name="example-violation"></a>Příklad porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje třídu (odkaz), která pochází z neobecnou `CollectionBase` třídy, která porušuje toto pravidlo.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

### <a name="comments"></a>Komentáře
 Opravit porušení tento porušení, si implementovat obecné rozhraní nebo změňte základní třídy na typ, který již implementuje obou obecné a neobecné rozhraní, například `Collection<T>` třídy.

## <a name="fix-by-base-class-change"></a>Opravte změnou základní třída

### <a name="description"></a>Popis
 Následující příklad opraví porušení změnou základní třídu kolekce z neobecnou `CollectionBase` třídy obecná `Collection<T>` (`Collection(Of T)` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) třída.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

### <a name="comments"></a>Komentáře
 Změna základní třídy již vydaných třídy považuje za zásadní změnu existující příjemce.

## <a name="fix-by-interface-implementation"></a>Opravit implementace rozhraní

### <a name="description"></a>Popis
 Následující příklad opraví porušení implementací těchto obecná rozhraní: `IEnumerable<T>`, `ICollection<T>`, a `IList<T>` (`IEnumerable(Of T)`, `ICollection(Of T)`, a `IList(Of T)` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Nezveřejňujte obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Použijte instance obecných obslužných rutin události](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Viz také
 [Obecné typy](/dotnet/csharp/programming-guide/generics/index)