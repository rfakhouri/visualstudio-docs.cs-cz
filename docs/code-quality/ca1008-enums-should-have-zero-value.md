---
title: 'CA1008: Výčty by měly mít nulovou hodnotu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9264b37992885ff3d93aba4802d8d7f0cee535aa
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54992903"
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: Výčty by měly mít nulovou hodnotu

|||
|-|-|
|TypeName|EnumsShouldHaveZeroValue|
|CheckId|CA1008|
|Kategorie|Microsoft.Design|
|Narušující změna|Bez konce – po zobrazení výzvy k přidání **žádný** hodnotu výčtu bez příznaku. Zásadní – po zobrazení výzvy k přejmenujte nebo odeberte všechny hodnoty výčtu.|

## <a name="cause"></a>Příčina

Výčet bez použité <xref:System.FlagsAttribute?displayProperty=fullName> nedefinuje člena, který má hodnotu nula; nebo výčet, který má použité <xref:System.FlagsAttribute> definuje člen s hodnotou nula, ale jeho název není 'None' nebo výčet definuje více s nulovou hodnotou členy.

## <a name="rule-description"></a>Popis pravidla

Výchozí hodnota neinicializovaného výčtu je stejně jako jiné hodnotové typy, je nula. Výčet bez příznaků atributů by měl definovat člen, který má hodnotu nula, tak, aby výchozí hodnota je platná hodnota výčtu. V případě potřeby, název člena 'None'. V opačném případě přiřadíte nulový nejčastěji používané člena. Ve výchozím nastavení Pokud hodnota první člen výčtu není nastavená v deklaraci, jeho hodnota je nula.

Pokud výčet, který má <xref:System.FlagsAttribute> použít definuje člen s nulovou hodnotou, její název by měl být "Žádný" k označení, že ve výčtu byly nastaveny žádné hodnoty. Použití člena s nulovou hodnotou pro jakékoli jiné účely bylo v rozporu s použití <xref:System.FlagsAttribute> , AND a bitové operátory jsou zbytečné s členem. Z toho vyplývá, že pouze jednoho člena by měla být přiřazena hodnota nula. Pokud dojde k více členů, které mají nulovou hodnotu ve výčtu s atributy příznaky `Enum.ToString()` vrátí nesprávné výsledky pro členy, kteří nejsou nula.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla pro výčty bez příznaků atributů, definujte člen, který má hodnotu nula; Jedná se o změnu pevné. Pro výčty příznaků s atributy, které definovat člen s hodnotou nula název tohoto člena 'None' a odstranit všechny členy, které mají hodnotu nula; Toto je zásadní změnu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění tohoto pravidla s výjimkou s atributy příznaky výčty, které byly dříve součástí.

## <a name="example"></a>Příklad

Následující příklad ukazuje dva výčty, které splňují pravidla a výčet, `BadTraceOptions`, který porušuje pravidla.

[!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
[!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
[!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]

## <a name="related-rules"></a>Související pravidla

- [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700: Nepojmenovávejte výčtu hodnoty 'Reserved'](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA1712: Nezačínejte hodnoty výčtu s názvem typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)
- [CA1028: Úložiště výčtu by měl být Int32](../code-quality/ca1028-enum-storage-should-be-int32.md)
- [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Enum?displayProperty=fullName>