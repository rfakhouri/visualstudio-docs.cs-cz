---
title: 'CA1027: Označte výčty pomocí FlagsAttribute'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkEnumsWithFlags
- CA1027
helpviewer_keywords:
- CA1027
- MarkEnumsWithFlags
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b11b64ffbf6245357cccd04c0e67cf8791f6351f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027: Označte výčty pomocí FlagsAttribute
|||
|-|-|
|TypeName|MarkEnumsWithFlags|
|CheckId|CA1027|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Hodnoty veřejný výčet jsou zajišťuje dva nebo kombinace jiné hodnoty, které jsou definovány ve výčtu, a <xref:System.FlagsAttribute?displayProperty=fullName> atribut není k dispozici. Toto pravidlo na snížil počet falešných poplachů, nehlásí porušení pro výčty, které mají souvislý hodnoty.

## <a name="rule-description"></a>Popis pravidla
 Výčet je typ hodnoty, který definuje množinu souvisejících pojmenovaných konstant. Použít <xref:System.FlagsAttribute> pro výčet může být jeho pojmenované konstanty srozumitelně kombinaci. Představte si třeba výčet dny v týdnu v aplikaci, která uchovává informace o který den prostředky jsou k dispozici. Pokud je dostupnost každého prostředku zakódován pomocí výčet, který má <xref:System.FlagsAttribute> může být reprezentován přítomen, libovolnou kombinaci dnů. Atribut ID může být reprezentován pouze jeden den v týdnu.

 Pro pole, které ukládají combinable výčty jsou hodnoty jednotlivých výčtu považovány za skupin bitů v poli. Proto tato pole jsou někdy označovány jako *bit pole*. Chcete-li kombinace hodnot výčtu pro úložiště v poli bit, použijte Boolean podmíněné operátory. K otestování bitová pole, které chcete určit, zda je hodnota konkrétní výčtu existuje, použijte Boolean logické operátory. Každou hodnotu, která je definována ve výčtu bitové pole k ukládání a načítání hodnot výčtu kombinované správně, musí být násobek dvou. Pokud tomu tak je, logická hodnota logické operátory nebude možné extrahovat jednotlivé výčtové hodnoty, které jsou uložené v poli.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, přidejte <xref:System.FlagsAttribute> výčtu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačíte upozornění na toto pravidlo, pokud nechcete, aby hodnoty výčtu, které mají být combinable.

## <a name="example"></a>Příklad
 V následujícím příkladu `DaysEnumNeedsFlags` je výčet, který splňuje požadavky pro používání <xref:System.FlagsAttribute>, ale nechcete ho. `ColorEnumShouldNotHaveFlag` Výčet nemá hodnoty, které jsou zajišťuje dva, ale nesprávně určuje <xref:System.FlagsAttribute>. To porušuje pravidlo [CA2217: neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md).

 [!code-csharp[FxCop.Design.EnumFlags#1](../code-quality/codesnippet/CSharp/ca1027-mark-enums-with-flagsattribute_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také
 <xref:System.FlagsAttribute?displayProperty=fullName>