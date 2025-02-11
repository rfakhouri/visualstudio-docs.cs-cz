---
title: 'CA2217: Neoznačujte výčty pomocí FlagsAttribute'
ms.date: 03/11/2019
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
ms.openlocfilehash: 377188183acdaa9aa86ae3344c8f6d5727b82ccc
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546847"
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217: Neoznačujte výčty pomocí FlagsAttribute

|||
|-|-|
|TypeName|DoNotMarkEnumsWithFlags|
|CheckId|CA2217|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina

Výčet je označen atributem <xref:System.FlagsAttribute> a obsahuje jednu nebo více hodnot, které nejsou mocninou dvou nebo kombinací jiných definovaných hodnot výčtu.

Ve výchozím nastavení toto pravidlo vypadá pouze v externě viditelných výčtech, ale to je [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Výčet by měl být <xref:System.FlagsAttribute> přítomen pouze v případě, že je každá hodnota definovaná ve výčtu mocninou dvou nebo kombinací definovaných hodnot.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.FlagsAttribute> z výčtu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca2217.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (použití). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="examples"></a>Příklady

Následující kód ukazuje výčet, `Color`, který obsahuje hodnotu 3. 3 není mocninou dvou nebo kombinací žádné z definovaných hodnot. Výčet by neměl být <xref:System.FlagsAttribute>označený jako. `Color`

[!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]

Následující kód ukazuje výčet, `Days`který splňuje požadavky pro označení pomocí: <xref:System.FlagsAttribute>

[!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]

## <a name="related-rules"></a>Související pravidla

[CA1027: Označení výčtů pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.FlagsAttribute?displayProperty=fullName>
