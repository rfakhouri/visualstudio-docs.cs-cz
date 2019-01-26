---
title: 'CA1007: Použijte obecné typy, kde je to vhodné'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1007
- UseGenericsWhereAppropriate
helpviewer_keywords:
- CA1007
- UseGenericsWhereAppropriate
ms.assetid: eab780ea-3b1f-4d32-b15a-5d48da2df46b
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d886877531deb6526e6d8c6421d1e3285c5e109a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55006265"
---
# <a name="ca1007-use-generics-where-appropriate"></a>CA1007: Použijte obecné typy, kde je to vhodné

|||
|-|-|
|TypeName|UseGenericsWhereAppropriate|
|CheckId|CA1007|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Externě viditelná metoda obsahuje referenční parametr typu <xref:System.Object?displayProperty=fullName>a obsahující cíle sestavení [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].

## <a name="rule-description"></a>Popis pravidla
 Odkaz na parametr je parametr, který je upraven pomocí `ref` (`ByRef` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) – klíčové slovo. Typ argumentu, který je zadán pro referenční parametr musí přesně odpovídat na referenční typ parametru. Pokud chcete použít typ, který je odvozen z parametrů typu odkazu, typ musí nejprve být přetypování a přiřazen proměnné typu odkazu, parametr. Použití generické metody umožňuje všechny typy v souladu s omezením, které se mají předat metodě bez předchozího přetypování typu na referenční typ parametru.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, ujistěte se, metoda obecný a nahraďte <xref:System.Object> parametru pomocí typu parametru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje rutinu prohození pro obecné účely, která je implementována jako neobecné a obecné metody. Všimněte si, jak efektivní jsou přehozeny řetězců s použitím ve srovnání s neobecnou metodu obecnou metodu.

 [!code-vb[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/VisualBasic/ca1007-use-generics-where-appropriate_1.vb)]
 [!code-csharp[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/CSharp/ca1007-use-generics-where-appropriate_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Nezveřejňujte obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Použijte instance obecných události obslužné rutiny](../code-quality/ca1003-use-generic-event-handler-instances.md)

## <a name="see-also"></a>Viz také:
 [Obecné typy](/dotnet/csharp/programming-guide/generics/index)