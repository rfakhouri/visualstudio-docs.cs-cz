---
title: 'CA2227: Vlastnosti kolekce by měly být pouze pro čtení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: aa1d8644049f78eccfda7402360bdbc930b61601
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
ms.locfileid: "34447671"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Vlastnosti kolekce by měly být pouze pro čtení

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Ve vlastnosti externě viditelné, s možností zápisu je typ, který implementuje <xref:System.Collections.ICollection?displayProperty=fullName>. Toto pravidlo ignoruje pole, indexery (vlastnosti s názvem 'Item') a sady oprávnění.

## <a name="rule-description"></a>Popis pravidla

Vlastnost zapisovatelné kolekce umožňuje uživateli kolekce nahradit úplně jinou kolekci. Vlastnosti jen pro čtení zastaví kolekci z nahrazují, ale stále umožňuje nastavit jednotlivé členy. Pokud nahrazení kolekce je cílem, je upřednostňovanou vzor patří způsob odebrání všechny elementy z kolekce a způsob, jak znovu vytvořit kolekci. Najdete v článku <xref:System.Collections.ArrayList.Clear%2A> a <xref:System.Collections.ArrayList.AddRange%2A> metody <xref:System.Collections.ArrayList?displayProperty=fullName> třída příklad tohoto vzoru.

Binární i serializace XML podporují jen pro čtení vlastnosti, které jsou kolekce. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Třída má specifické požadavky pro typy, které implementují <xref:System.Collections.ICollection> a <xref:System.Collections.IEnumerable?displayProperty=fullName> Chcete-li být serializovatelný.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení toto pravidlo, zkontrolujte vlastnost jen pro čtení. Pokud to vyžaduje návrh, přidejte metody zrušte a znovu vytvořit kolekci.

## <a name="when-to-suppress-warnings"></a>Při potlačení upozornění

Není potlačení upozornění od tohoto pravidla.

## <a name="example"></a>Příklad

Následující příklad ukazuje typ s možností zápisu kolekce vlastností a jak kolekci lze nahradit přímo. Kromě toho upřednostňovaný způsob nahrazení pomocí vlastnosti jen pro čtení kolekce `Clear` a `AddRange` metody se zobrazí.

[!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
[!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
[!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]

## <a name="related-rules"></a>Související pravidla

[CA1819: Vlastnosti by neměly vracet pole](../code-quality/ca1819-properties-should-not-return-arrays.md)