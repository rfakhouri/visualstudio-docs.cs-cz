---
title: 'CA1701: Složených slov prostředku řetězců by měla být správně formátováno | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
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
ms.openlocfilehash: ccffe6561d461e52eb15f94a97a04c633d37abff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633565"
---
# <a name="ca1701-resource-string-compound-words-should-be-cased-correctly"></a>CA1701: Malá a velká písmena složených slov prostředku řetězců by měla být použita správně
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1701: složených slov prostředku řetězců by měla být správně formátováno](https://docs.microsoft.com/visualstudio/code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly).  
  
TypeName | ResourceStringCompoundWordsShouldBeCasedCorrectly |  
| ID kontroly | CA1701 |  
| Kategorie | Microsoft.Naming|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Zdrojový řetězec obsahuje složené slovo, který zřejmě není správně formátováno.  
  
## <a name="rule-description"></a>Popis pravidla  
 Každé slovo řetězce zdroje je rozděleno na tokeny, které jsou založeny na velká a malá písmena. Každá kombinace dvou sousedících tokenů je zkontrolována knihovnou kontroly pravopisu společnosti Microsoft. Je-li kombinace rozpoznána, způsobí slovo porušení pravidla. Příklady složených slov, které způsobují porušení: "Kontrolního součtu" a "MultiPart", která by měla být malá a velká použita jako "Kontrolního součtu" a "Multipart", v uvedeném pořadí. Z důvodu předchozí běžné použití několik výjimek jsou integrované do pravidla a jsou označeny několik jednotlivá slova, jako je například "Panel nástrojů" a "Název_souboru", který by měl být malá a velká použita jako dvě různá slova. V tomto příkladu by být označený "Panel nástrojů" a "Název_souboru".  
  
 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Změní celé slovo tak, že je správně formátováno.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění tohoto pravidla, je-li obě části složené slovo, které jsou rozpoznány modulem slovníku a cílem je používat dvě slova.  
  
 Složených slov můžete také přidat do slovníku pro kontrolu pravopisu. Vlastní slovník nezpůsobí porušení. Další informace najdete v tématu [postupy: přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md).  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1702: Malá a velká písmena složených slov by měla být použita správně](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
 [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
## <a name="see-also"></a>Viz také  
 [Konvence pro malá a velká písmena](http://msdn.microsoft.com/library/4c4ea526-9203-486f-b72d-29d61c5b3c6d)   
 [Pokyny pro pojmenování](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3)



