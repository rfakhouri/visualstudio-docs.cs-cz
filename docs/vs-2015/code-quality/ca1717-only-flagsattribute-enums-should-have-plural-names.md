---
title: 'CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: aa0c51eaa10503a92c21960dc3dd074aa7541f5c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65694961"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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

## <a name="see-also"></a>Viz také
 <xref:System.FlagsAttribute?displayProperty=fullName> [Návrh výčtu](https://msdn.microsoft.com/library/dd53c952-9d9a-4736-86ff-9540e815d545)
