---
title: 'CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93cc4b36372d1e5ef6c81f16dc74285c336d08cc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31914572"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle
|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název externě viditelné výčet končí v množném čísle aplikaci word a výčtu není označen atributem <xref:System.FlagsAttribute?displayProperty=fullName> atribut.

## <a name="rule-description"></a>Popis pravidla
 Zásady vytváření názvů určují, že množném čísle název pro výčet udává, že více než jednu hodnotu výčtu lze zadat současně. <xref:System.FlagsAttribute> Kompilátory informuje, že výčtu má být použit jako pole bit, který umožňuje bitové operace na výčtu.

 Pokud jen jedna hodnota výčtu lze najednou, název výčtu by měl být singulární aplikace word. Například výčet, který definuje dny v týdnu, může být určena pro použití v aplikaci, kde můžete určit více dní. Tento výčet by měl mít <xref:System.FlagsAttribute> a může být volána 'dny. Podobně jako výčet, který umožňuje zadat pouze jeden den by mít atribut a může být volána "Den".

 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje čas, který je potřeba další nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Nastavit název výčtu singulární slovo nebo přidat <xref:System.FlagsAttribute>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na pravidlo, je-li název končí v jednotném čísle aplikace word.

## <a name="related-rules"></a>Související pravidla
 [CA1714: Výčty příznaků by neměly mít názvy v množném čísle](../code-quality/ca1714-flags-enums-should-have-plural-names.md)

 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také
 <xref:System.FlagsAttribute?displayProperty=fullName> [Návrh výčtu](/dotnet/standard/design-guidelines/enum)