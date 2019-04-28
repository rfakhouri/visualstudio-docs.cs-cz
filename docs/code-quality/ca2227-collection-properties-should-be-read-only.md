---
title: 'CA2227: Vlastnosti kolekce by měly být pouze pro čtení'
ms.date: 09/28/2018
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
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 8a6ced277aa442450418ce55f4e1db56ad5d8af1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806534"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Vlastnosti kolekce by měly být pouze pro čtení

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Externě viditelný, Zapisovat vlastnosti je typu, který implementuje <xref:System.Collections.ICollection?displayProperty=fullName>. Toto pravidlo ignoruje pole, indexery (vlastnosti s názvem "Položka") a sady oprávnění.

## <a name="rule-description"></a>Popis pravidla

Zapisovatelná vlastnost kolekce umožňuje uživateli nahradit kolekci zcela jinou kolekci. Vlastnost jen pro čtení neumožňuje kolekci nahradit, ale stále umožňuje nastavit jednotlivé členy. Pokud nahrazující kolekce je cíl, vzor upřednostňovaný návrh je metoda odebrání všechny elementy z kolekce a způsob, jak znovu vytvořit kolekci. Najdete v článku <xref:System.Collections.ArrayList.Clear%2A> a <xref:System.Collections.ArrayList.AddRange%2A> metody <xref:System.Collections.ArrayList?displayProperty=fullName> třídy příklad tohoto modelu.

Binární soubor a serializace XML podporují jen pro čtení vlastnosti, které jsou kolekce. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Třída má specifické požadavky na typy, které implementují <xref:System.Collections.ICollection> a <xref:System.Collections.IEnumerable?displayProperty=fullName> -li být serializovatelný.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, nastavte vlastnost jen pro čtení. Pokud to vyžaduje návrh, přidejte metody, zrušte a znovu vytvořit kolekci.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Upozornění můžete potlačit, pokud vlastnost je součástí [objekt pro přenos dat (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) třídy.

V opačném případě nepotlačujte upozornění tohoto pravidla.

## <a name="example"></a>Příklad

Následující příklad ukazuje typ s zapisovatelná vlastnost kolekce a jak kolekce se dá nahradit přímo. Kromě toho ukazuje upřednostňovaný způsob nahrazení vlastnost kolekce jenom pro čtení pomocí `Clear` a `AddRange` metody.

[!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
[!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
[!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]

## <a name="related-rules"></a>Související pravidla

- [CA1819: Vlastnosti by neměly vracet pole](../code-quality/ca1819-properties-should-not-return-arrays.md)