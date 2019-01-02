---
title: 'CA1701: Složených slov prostředku řetězců by měla být správně formátováno | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ResourceStringCompoundWordsShouldBeCasedCorrectly
- CA1701
helpviewer_keywords:
- CA1701
- ResourceStringCompoundWordsShouldBeCasedCorrectly
ms.assetid: 4ddbe09f-24b8-4c47-9373-a06f4487ca0d
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 664ffcfafe45bd8572b16b286cd8844f481d8821
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53832561"
---
# <a name="ca1701-resource-string-compound-words-should-be-cased-correctly"></a>CA1701: Složených slov prostředku řetězců by měla správně formátováno.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, je-li obě části složené slovo, které jsou rozpoznány modulem slovníku a cílem je používat dvě slova.

 Složených slov můžete také přidat do slovníku pro kontrolu pravopisu. Vlastní slovník nezpůsobí porušení. Další informace najdete v tématu [jak: Přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md).

## <a name="related-rules"></a>Související pravidla
 [CA1702: Složených slov by měla správně formátováno.](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)

 [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708: Identifikátory by se měly lišit o více než velikostí písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

## <a name="see-also"></a>Viz také
 [Konvence pro malá a velká písmena](http://msdn.microsoft.com/library/4c4ea526-9203-486f-b72d-29d61c5b3c6d) [pokyny pro pojmenování](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3)
