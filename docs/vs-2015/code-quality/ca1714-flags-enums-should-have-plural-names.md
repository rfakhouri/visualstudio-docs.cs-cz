---
title: 'CA1714: Výčty příznaků by neměly mít názvy v množném čísle | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: bf0e75596bfc2b274f12d9b58d2718881931b7df
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65700515"
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714: Výčty příznaků by neměly mít názvy v množném čísle
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|FlagsEnumsShouldHavePluralNames|
|CheckId|CA1714|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Veřejný výčet má <xref:System.FlagsAttribute?displayProperty=fullName> a jeho název nekončí v prvku ".

## <a name="rule-description"></a>Popis pravidla
 Typy, které jsou označené <xref:System.FlagsAttribute> mít názvy, které jsou v množném čísle, protože tento atribut označuje, že lze zadat více než jednu hodnotu. Například výčet, který definuje dny v týdnu může být určena pro použití v aplikaci ve kterém můžete zadat více dní. By měl mít tento výčet <xref:System.FlagsAttribute> a může mít název "dny. Podobně jako výčet, který umožňuje zadat pouze jeden den by obsahovat atribut a může být volána "Den".

 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vytvořit název výčtu množném čísle slova nebo odebrat <xref:System.FlagsAttribute> atribut, pokud by neměla současně zadat více hodnot výčtu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit narušení, je-li název množném čísle slovo ale nekončí na ". Například pokud několik dní výčtu, která byla popsána dříve byly s názvem "DaysOfTheWeek", to by mohla narušit logice pravidla, ale ne jeho záměr. Tato porušení by měl být suppressd.

## <a name="related-rules"></a>Související pravidla
 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také
 <xref:System.FlagsAttribute?displayProperty=fullName> [Návrh výčtu](https://msdn.microsoft.com/library/dd53c952-9d9a-4736-86ff-9540e815d545)
