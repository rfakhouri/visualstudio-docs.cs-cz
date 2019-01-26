---
title: 'CA1702: Malá a velká písmena složených slov by měla být použita správně'
ms.date: 03/28/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
helpviewer_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
ms.assetid: 05481245-7ad8-48c3-a456-3aa44b6160a6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 67d697ac5c441efaf78fa7382b9efdead647eec8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996503"
---
# <a name="ca1702-compound-words-should-be-cased-correctly"></a>CA1702: Malá a velká písmena složených slov by měla být použita správně

|||
|-|-|
|TypeName|CompoundWordsShouldBeCasedCorrectly|
|CheckId|CA1702|
|Kategorie|Microsoft.Naming|
|Narušující změna|Při ukončování pro sestavení vyvolala.<br /><br /> Bez konce – při vyvolání na parametry typu.|

## <a name="cause"></a>Příčina

Název identifikátoru obsahuje více slov a alespoň jedno ze slov se zdá být složené slovo, které není správně formátováno.

## <a name="rule-description"></a>Popis pravidla

Název identifikátoru je rozdělený do slov, které jsou založeny na velká a malá písmena. Každá kombinace souvislých dvě slova je zaškrtnuté políčko knihovnou kontroly pravopisu společnosti Microsoft. Pokud je rozpoznána, vytvoří identifikátor porušení tohoto pravidla. Příklady složených slov, které způsobují porušení: "Kontrolního součtu" a "MultiPart", která by měla být malá a velká použita jako "Kontrolního součtu" a "Multipart", v uvedeném pořadí. Z důvodu předchozí běžné použití několika výjimkami jsou součástí pravidla a jsou označeny několik jednotlivá slova, jako je například "Panel nástrojů" a "Název_souboru", který by měl být notaci jako dvě různá slova (v tomto případě "Panel nástrojů" a "Název_souboru").

Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Změňte název tak, že je správně formátováno.

## <a name="language"></a>Jazyk

Nástroj pro kontrolu pravopisu aktuálně zkontroluje pouze proti jazykovou verzi na základě angličtina slovníky. Jazyková verze projektu v souboru projektu, můžete změnit tak, že přidáte **CodeAnalysisCulture** elementu.

Příklad:

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> Pokud nastavíte jazykovou verzi na jinou hodnotu než jazykovou verzi na základě angličtina, tento pravidel nástroje Analýza kódu je tiše zakázaná.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, je-li obě části složené slovo, které jsou rozpoznány modulem slovníku a cílem je používat dvě slova.

## <a name="related-rules"></a>Související pravidla

- [CA1701: Složených slov prostředku řetězců by měla správně formátováno.](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708: Identifikátory by se měly lišit o více než velikostí písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

## <a name="see-also"></a>Viz také:

- [Pokyny pro pojmenování](/dotnet/standard/design-guidelines/naming-guidelines)
- [Konvence pro malá a velká písmena](/dotnet/standard/design-guidelines/capitalization-conventions)