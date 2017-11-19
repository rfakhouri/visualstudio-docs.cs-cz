---
title: "CA1702: Složených slov by měla být použita správně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
helpviewer_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
ms.assetid: 05481245-7ad8-48c3-a456-3aa44b6160a6
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9c8606656b7ffe5f64c4c162b85d24bdbd9b1de0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1702-compound-words-should-be-cased-correctly"></a>CA1702: Malá a velká písmena složených slov by měla být použita správně
|||  
|-|-|  
|TypeName|CompoundWordsShouldBeCasedCorrectly|  
|CheckId|CA1702|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Při ukončování aktivováno u sestavení.<br /><br /> Non narušující - při vyvolání parametrů typů.|  
  
## <a name="cause"></a>příčina  
 Název identifikátoru obsahuje více slov a alespoň jeden z slova se zdá být složené slovo, které není použita správně.  
  
## <a name="rule-description"></a>Popis pravidla  
 Název identifikátoru je rozdělení do slova, které jsou založeny na malá a velká písmena. Každý souvislý dva slovní spojení je ve kontrola pravopisu knihovně společnosti Microsoft. Pokud je rozpoznána, vytvoří identifikátor narušení pravidla. Příklady složených slov, které způsobí narušení jsou "Kontrolního součtu" a "MultiPart", která by měla být použita jako "Kontrolního součtu" a "Multipart", v uvedeném pořadí. Z důvodu předchozí běžné použití několika výjimkami je součástí pravidlo, a jsou označeny několik jednoho slova, jako je například "Nástrojů" a "Název souboru", která by měla být použita jako dvě různá slova (v tomto případě "Nástrojů" a "Název").  
  
 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje křivky learning, který je vyžadován pro nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Změňte název tak, aby je použita správně.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud jsou obě části složené slovo rozpoznáno slovníku a je použít dvě slova.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1701: Složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
 [CA1709: Identifikátory by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit o více než případu](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
## <a name="see-also"></a>Viz také  
 [Pokyny pro pojmenování](/dotnet/standard/design-guidelines/naming-guidelines)   
 [Konvence malá a velká písmena](/dotnet/standard/design-guidelines/capitalization-conventions)