---
title: 'CA1700: Nepojmenovávejte hodnoty výčtu &#39;vyhrazena&#39;'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1700
- DoNotNameEnumValuesReserved
helpviewer_keywords:
- DoNotNameEnumValuesReserved
- CA1700
ms.assetid: 7a7e01c3-ae7d-4c82-a646-91b58864a749
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d2e7b501019ed2891a30d1f0359aee6405c4444
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1700-do-not-name-enum-values-39reserved39"></a>CA1700: Nepojmenovávejte hodnoty výčtu &#39;vyhrazena&#39;
|||
|-|-|
|TypeName|DoNotNameEnumValuesReserved|
|CheckId|CA1700|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název člena výčtu obsahuje slovo "vyhrazené".

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo předpokládá, že člen výčtu, který má název obsahující výraz „reserved“, není aktuálně používán, ale je zástupným symbolem k přejmenování nebo odstranění v budoucí verzi. Přejmenování nebo odstranění členu je narušující změna. Není pravděpodobné, že uživatelům ignorovat členem právě, protože její název obsahuje "vyhrazené" ani můžete byste tedy spoléhat na uživatelé pro čtení nebo dodržováním dokumentaci. Navíc vzhledem vyhrazené členy se zobrazí v prohlížeči objektů a inteligentní integrované vývojové prostředí, se může způsobit nejasnosti o tom, které jsou členy ve skutečnosti používány.

 Místo použití vyhrazené člena, přidejte nový člen výčtu v budoucí verzi. Ve většině případů není přidání nového člena narušující změně, tak dlouho, dokud nedojde k přidání hodnoty z původní členů a změnit.

 V některých případech je přidání člena narušující změně i v případě, že původní členy zachovat původní hodnoty. Především se stává, nejde vrátit nového člena z existující cesty kódu, aniž by vás volající, které používají `switch` (`Select` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) příkaz na návratovou hodnotu seznamu celý člen, který zahrnuje a které způsobí výjimku výchozí případu. Sekundární problém je, že kód klienta, jako nemusí zpracovat změny v chování z metody reflexe <xref:System.Enum.IsDefined%2A?displayProperty=fullName>. Podle toho, pokud nového člena musí být vrácená z existující metody nebo nekompatibilita známé aplikace k tomu dochází kvůli využití reflexe nízký, jenom pevných řešení je:

1.  Přidáte nový výčet, který obsahuje původní a nové členy.

2.  Označit původní výčet s <xref:System.ObsoleteAttribute?displayProperty=fullName> atribut.

 Postupujte stejným způsobem pro všechny externě viditelné typy a členy, které zveřejňují původní výčtu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, odebrat nebo člen.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné pro potlačení upozornění od tohoto pravidla pro člena, který je aktuálně používána nebo knihovny, které byly dříve součástí.

## <a name="related-rules"></a>Související pravidla
 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1712: Nezačínejte hodnoty výčtu s názvem typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

 [CA1028: Úložiště výčtu by měl být Int32](../code-quality/ca1028-enum-storage-should-be-int32.md)

 [CA1008: Výčty by měly mít nulovou hodnotu](../code-quality/ca1008-enums-should-have-zero-value.md)

 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)