---
title: 'CA1027: Označte výčty pomocí FlagsAttribute'
ms.date: 03/11/2019
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: acdb8406d43f90414cf255abae6f1ca5f549e92e
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842473"
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027: Označte výčty pomocí FlagsAttribute

|||
|-|-|
|TypeName|MarkEnumsWithFlags|
|CheckId|CA1027|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Hodnoty výčtu jsou mocniny dvou nebo kombinací jiných hodnot, které jsou definovány ve výčtu, a <xref:System.FlagsAttribute?displayProperty=fullName> atribut není k dispozici. Pokud chcete snížit počet falešně pozitivních výsledků, toto pravidlo sestavu porušení pro výčty, které mají souvislých hodnot.

Ve výchozím nastavení, toto pravidlo pouze prohledá veřejné výčty, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Výčet je typ hodnoty, který definuje množinu souvisejících pojmenovaných konstant. Použít <xref:System.FlagsAttribute> výčtu když mohou být pojmenované konstanty smysluplně kombinovány. Představte si třeba výčet dny v týdnu v aplikaci, která uchovává informace o den, které prostředky jsou k dispozici. Pokud je dostupnost každého prostředku zakódován pomocí výčtu, která má <xref:System.FlagsAttribute> můžou být vyjádřeny současné libovolnou kombinací těchto dnů. Bez atributu může být reprezentován jenom jeden den v týdnu.

U polí, které ukládají combinable – výčty hodnot jednotlivých výčtu jsou považovány za skupin bitů v poli. Proto tato pole jsou někdy označovány jako *bitová pole*. Chcete-li kombinace hodnot výčtu pro úložiště v bitové pole, použijte logická podmíněných operátorů. K otestování bitové pole. k určení, zda hodnota konkrétní výčtu není k dispozici, použijte logické logické operátory. Jednotlivé hodnoty, které je definováno ve výčtu bitové pole k ukládání a načítání hodnot výčtu kombinované správně, musí být mocninou čísla 2. Pokud to není tak logické logické operátory nebude možné extrahovat hodnoty jednotlivých výčtu, které jsou uloženy v poli.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, přidejte <xref:System.FlagsAttribute> do výčtu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačit upozornění tohoto pravidla, pokud nechcete, aby výčtu hodnoty, které mají být kombinovatelných.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1027.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

V následujícím příkladu `DaysEnumNeedsFlags` je výčet, který splňuje požadavky na používání <xref:System.FlagsAttribute> ale není zaškrtnuta. `ColorEnumShouldNotHaveFlag` Výčet nemá žádné hodnoty, které jsou pro mocniny dvou ale nesprávně určuje <xref:System.FlagsAttribute>. To porušuje pravidlo [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md).

[!code-csharp[FxCop.Design.EnumFlags#1](../code-quality/codesnippet/CSharp/ca1027-mark-enums-with-flagsattribute_1.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.FlagsAttribute?displayProperty=fullName>