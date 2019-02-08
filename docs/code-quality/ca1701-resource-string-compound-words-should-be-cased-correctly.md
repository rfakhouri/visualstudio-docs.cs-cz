---
title: 'CA1701: Malá a velká písmena složených slov řetězců prostředků by měla být použita správně'
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- ResourceStringCompoundWordsShouldBeCasedCorrectly
- CA1701
helpviewer_keywords:
- CA1701
- ResourceStringCompoundWordsShouldBeCasedCorrectly
ms.assetid: 4ddbe09f-24b8-4c47-9373-a06f4487ca0d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8fdae06137586f11de1a30a73894c46c7fb18fa6
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955346"
---
# <a name="ca1701-resource-string-compound-words-should-be-cased-correctly"></a>CA1701: Malá a velká písmena složených slov řetězců prostředků by měla být použita správně

|||
|-|-|
|TypeName|ResourceStringCompoundWordsShouldBeCasedCorrectly|
|CheckId|CA1701|
|Kategorie|Microsoft.Naming|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Zdrojový řetězec obsahuje složené slovo, který zřejmě není správně formátováno.

## <a name="rule-description"></a>Popis pravidla

Každé slovo řetězce zdroje je rozděleno na tokeny, které jsou založeny na velká a malá písmena. Každá kombinace dvou sousedících tokenů je zkontrolována knihovnou kontroly pravopisu společnosti Microsoft. Je-li kombinace rozpoznána, způsobí slovo porušení pravidla. Příklady složených slov, které způsobují porušení: "Kontrolního součtu" a "MultiPart", která by měla být malá a velká použita jako "Kontrolního součtu" a "Multipart", v uvedeném pořadí. Z důvodu předchozí běžné použití několik výjimek jsou integrované do pravidla a jsou označeny několik jednotlivá slova, jako je například "Panel nástrojů" a "Název_souboru", který by měl být malá a velká použita jako dvě různá slova. V tomto příkladu by být označený "Panel nástrojů" a "Název_souboru".

Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Změní celé slovo tak, že je správně formátováno.

## <a name="change-the-dictionary-language"></a>Změnit jazyk slovníku

Ve výchozím nastavení je použít nástroj pro kontrolu pravopisu verze Angličtina (en). Pokud chcete změnit jazyk kontroly pravopisu, může to tak, že přidáte jednu z následujících atributů vaše *AssemblyInfo.cs* nebo *AssemblyInfo.vb* souboru:

- Použití <xref:System.Reflection.AssemblyCultureAttribute> zadat jazykovou verzi, pokud jsou vaše prostředky v satelitní sestavení.
- Použití <xref:System.Resources.NeutralResourcesLanguageAttribute> zadat *neutrální jazykovou verzi* vašeho sestavení, pokud jsou vaše prostředky ve stejném sestavení jako svůj kód.

> [!IMPORTANT]
> Pokud nastavíte jazykovou verzi na jinou hodnotu než jazykovou verzi na základě angličtina, tento pravidel nástroje Analýza kódu je tiše zakázaná.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, je-li obě části složené slovo, které jsou rozpoznány modulem slovníku a cílem je používat dvě slova.

Složených slov můžete také přidat do slovníku pro kontrolu pravopisu. Vlastní slovník nezpůsobí porušení. Další informace najdete v tématu [jak: Přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md).

## <a name="related-rules"></a>Související pravidla

- [CA1702: Složených slov by měla správně formátováno.](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)
- [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708: Identifikátory by se měly lišit o více než velikostí písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

## <a name="see-also"></a>Viz také:

- [Konvence pro malá a velká písmena](/dotnet/standard/design-guidelines/capitalization-conventions)
- [Pokyny pro pojmenování](/dotnet/standard/design-guidelines/naming-guidelines)