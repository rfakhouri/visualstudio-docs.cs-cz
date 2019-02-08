---
title: 'CA2217: Neoznačujte výčty pomocí FlagsAttribute'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
helpviewer_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
dev_langs:
- VB
- CSharp
- CPP
ms.assetid: 1b6f626c-66bf-45b0-a3e2-7c41ee9ceda7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce4036ef3c0c9ea177ea4225ed10ca7cfe128697
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55926811"
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217: Neoznačujte výčty pomocí FlagsAttribute

|||
|-|-|
|TypeName|DoNotMarkEnumsWithFlags|
|CheckId|CA2217|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina

Externě viditelný výčet je označen pomocí <xref:System.FlagsAttribute>a má jednu nebo více hodnot, které nejsou mocninami dvou nebo kombinací druhé definované hodnoty výčtu.

## <a name="rule-description"></a>Popis pravidla

Výčet by měl mít <xref:System.FlagsAttribute> k dispozici pouze v případě, že každá hodnota definované ve výčtu je mocninou dvou nebo kombinací definované hodnoty.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.FlagsAttribute> z výčtu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="example-that-should-not-have-the-attribute"></a>Příklad, který by neměl mít atribut

Následující příklad ukazuje výčet, `Color`, který obsahuje hodnotu 3. 3 není mocninou dvou nebo kombinací jiných definovaných hodnot. `Color` Výčtu by neměly být označeny atributem <xref:System.FlagsAttribute>.

[!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]

## <a name="example-that-should-have-the-attribute"></a>Příklad, který by měl mít atribut

Následující příklad ukazuje výčet, `Days`, který splňuje požadavky na právě označené <xref:System.FlagsAttribute>.

[!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]

## <a name="related-rules"></a>Související pravidla

[CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.FlagsAttribute?displayProperty=fullName>
