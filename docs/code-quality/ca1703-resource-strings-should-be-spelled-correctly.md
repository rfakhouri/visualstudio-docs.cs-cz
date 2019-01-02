---
title: 'CA1703: Řetězce prostředků by měly být zadány správně'
ms.date: 03/28/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0458fa33413023fe9ae2b693a9bf75ffacda706c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53890586"
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703: Řetězce prostředků by měly být zadány správně

|||
|-|-|
|TypeName|ResourceStringsShouldBeSpelledCorrectly|
|CheckId|CA1703|
|Kategorie|Microsoft.Naming|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Zdrojový řetězec obsahuje jedno nebo více slov, která knihovna kontroly pravopisu společnosti Microsoft nerozpoznala.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo analyzuje řetězec prostředku do slov (tokenizací složených slov) a zkontroluje pravopis pro každé slovo/token. Informace o analýze algoritmus, najdete v části [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, použijte celá slova, které jsou zadány správně nebo je přidat do slovníku. Informace o tom, jak použít vlastní slovníky najdete v tématu [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

## <a name="change-the-dictionary-language"></a>Změnit jazyk slovníku

Ve výchozím nastavení je použít nástroj pro kontrolu pravopisu verze Angličtina (en). Pokud chcete změnit jazyk kontroly pravopisu, může to tak, že přidáte jednu z následujících atributů vaše *AssemblyInfo.cs* nebo *AssemblyInfo.vb* souboru:

- Použití <xref:System.Reflection.AssemblyCultureAttribute> zadat jazykovou verzi, pokud jsou vaše prostředky v satelitní sestavení.
- Použití <xref:System.Resources.NeutralResourcesLanguageAttribute> zadat *neutrální jazykovou verzi* vašeho sestavení, pokud jsou vaše prostředky ve stejném sestavení jako svůj kód.

> [!IMPORTANT]
> Pokud nastavíte jazykovou verzi na jinou hodnotu než jazykovou verzi na základě angličtina, tento pravidel nástroje Analýza kódu je tiše zakázaná.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Správně hláskovaným slova zkrátit čas, který je potřeba další nové knihovny softwaru.

## <a name="related-rules"></a>Související pravidla

- [CA1701: Složených slov prostředku řetězců by měla správně formátováno.](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)