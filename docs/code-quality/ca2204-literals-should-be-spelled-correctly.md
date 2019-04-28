---
title: 'CA2204: Literály by měly být zadány správně'
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 82146c2ac997a0202c20e15492becb89a293f427
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541920"
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204: Literály by měly být zadány správně

|||
|-|-|
|TypeName|LiteralsShouldBeSpelledCorrectly|
|CheckId|CA2204|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Řetězcový literál je předán jako argument pro parametr lokalizovatelné nebo lokalizovatelné vlastnosti a řetězec obsahuje jedno nebo více slov, která knihovna kontroly pravopisu společnosti Microsoft nerozpoznala.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo zkontroluje řetězcový literál, který je předán jako hodnotu parametru nebo vlastnost, pokud jeden nebo více z následujících případech má hodnotu true:

- <xref:System.ComponentModel.LocalizableAttribute> Atribut parametru nebo vlastnosti je nastaven na hodnotu true.

- Název parametru nebo vlastnosti obsahuje "Text", "Zpráva" nebo "Popisu".

- Název proměnné řetězec, který je předán <xref:System.Console.Write%2A> nebo <xref:System.Console.WriteLine> metoda je "value" nebo "format".

Toto pravidlo analyzuje řetězcový literál do slov, tokenizací složených slov a zkontroluje pravopis pro každé slovo nebo token. Informace o analýze algoritmus, najdete v části [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

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

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, opravte pravopis slova nebo přidejte slovo do vlastního slovníku. Informace o tom, jak použít vlastní slovníky najdete v tématu [jak: Přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Správně hláskovaným slov snížit učit se vyžaduje pro nové knihovny softwaru.

## <a name="related-rules"></a>Související pravidla

- [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)