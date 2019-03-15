---
title: 'CA1714: Výčty příznaků by neměly mít názvy v množném čísle'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f5a1532b67fdaeb2a44663db77cfc8a1056004e4
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867797"
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714: Výčty příznaků by neměly mít názvy v množném čísle

|||
|-|-|
|TypeName|FlagsEnumsShouldHavePluralNames|
|CheckId|CA1714|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Výčet má <xref:System.FlagsAttribute?displayProperty=fullName> a jeho název nekončí v prvku ".

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné výčtů, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Typy, které jsou označené <xref:System.FlagsAttribute> mít názvy, které jsou v množném čísle, protože tento atribut označuje, že lze zadat více než jednu hodnotu. Například výčet, který definuje dny v týdnu může být určena pro použití v aplikaci ve kterém můžete zadat více dní. By měl mít tento výčet <xref:System.FlagsAttribute> a může mít název "dny. Podobně jako výčet, který umožňuje zadat pouze jeden den by obsahovat atribut a může být volána "Den".

Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Vytvořit název výčtu množném čísle slova nebo odebrat <xref:System.FlagsAttribute> atribut, pokud by neměla současně zadat více hodnot výčtu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit narušení, je-li název množném čísle slovo ale nekončí na ". Například pokud několik dní výčtu, která byla popsána dříve byly s názvem "DaysOfTheWeek", to by mohla narušit logice pravidla, ale ne jeho záměr. Má být potlačeno těchto porušení.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1714.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="related-rules"></a>Související pravidla

- [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [Návrh výčtu](/dotnet/standard/design-guidelines/enum)