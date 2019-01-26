---
title: 'CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f8fa009c93f049938a198eabd1a5dcc86a45caa7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957244"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle

|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Název externě viditelný výčet končí v množném čísle aplikace word a výčet není označen atributem <xref:System.FlagsAttribute?displayProperty=fullName> atribut.

## <a name="rule-description"></a>Popis pravidla
 Zásady vytváření názvů diktovat, že název v množném čísle pro výčet udává, že více než jednu hodnotu výčtu lze zadat současně. <xref:System.FlagsAttribute> Říká kompilátoru, že výčet mají být považována za bitové pole, který umožňuje bitové operace výčtu.

 Pokud pouze najednou můžete zadat jednu hodnotu výčtu, název výčtu by měl být singulární aplikace word. Například výčet, který definuje dny v týdnu může být určena pro použití v aplikaci ve kterém můžete zadat více dní. By měl mít tento výčet <xref:System.FlagsAttribute> a může mít název "dny. Podobně jako výčet, který umožňuje zadat pouze jeden den by obsahovat atribut a může být volána "Den".

 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje čas, který se vyžaduje další nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Nastavit název výčtu singulární slova nebo přidat <xref:System.FlagsAttribute>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění pravidla, je-li název končí v jednotném čísle aplikace word.

## <a name="related-rules"></a>Související pravidla
 [CA1714: Výčty příznaků by neměly mít názvy v množném čísle](../code-quality/ca1714-flags-enums-should-have-plural-names.md)

 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [Návrh výčtu](/dotnet/standard/design-guidelines/enum)