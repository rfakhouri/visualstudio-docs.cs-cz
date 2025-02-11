---
title: 'CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle'
ms.date: 03/11/2019
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
ms.openlocfilehash: 2d760802422773b3713fa7ea08ce0ce7a191f418
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547113"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle

|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Název výčtu končí v množném slově a výčet není označen <xref:System.FlagsAttribute?displayProperty=fullName> atributem.

Ve výchozím nastavení toto pravidlo vypadá pouze v externě viditelných výčtech, ale to je [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Zásady vytváření názvů určují, že plurální název pro výčet označuje, že lze zadat více než jednu hodnotu výčtu současně. <xref:System.FlagsAttribute> Říká kompilátorům, že by měl být výčet zpracován jako bitové pole, které umožňuje bitové operace na výčtu.

Pokud lze současně zadat pouze jednu hodnotu výčtu, název výčtu by měl být jednotné slovo. Například výčet, který definuje dny v týdnu, může být určen pro použití v aplikaci, kde můžete zadat více dní. Tento výčet by měl mít <xref:System.FlagsAttribute> operátor a mohl by být pojmenovaný ' days '. Podobný výčet, který umožňuje zadat pouze jeden den, by neměl mít atribut a mohl by být označován za "Day".

Zásady vytváření názvů poskytují běžný vzhled pro knihovny, které cílí na modul CLR (Common Language Runtime). Tím se zkracuje čas potřebný k učení nové softwarové knihovny a zvyšuje se důvěra zákazníků, že knihovna byla vyvinutá někým, kdo má zkušenosti s vývojem spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Nastavte název výčtu na jednotné slovo nebo přidejte <xref:System.FlagsAttribute>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění z pravidla, pokud název končí v jednotném slově.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1717.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (pojmenování). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="related-rules"></a>Související pravidla

- [CA1714: Výčty příznaků by měly mít názvy v množném čísle.](../code-quality/ca1714-flags-enums-should-have-plural-names.md)
- [CA1027: Označení výčtů pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [Návrh výčtu](/dotnet/standard/design-guidelines/enum)