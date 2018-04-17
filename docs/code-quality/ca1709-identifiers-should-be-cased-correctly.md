---
title: 'CA1709: Identifikátory by měla být použita správně | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- IdentifiersShouldBeCasedCorrectly
- CA1709
helpviewer_keywords:
- CA1709
- IdentifiersShouldBeCasedCorrectly
ms.assetid: f633d1a7-4ca4-40ae-b207-ec571c5fb083
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c010019c2ae5d1044d11c02c22428dda4197fcd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1709-identifiers-should-be-cased-correctly"></a>CA1709: Malá a velká písmena identifikátorů by měla být použita správně
|||  
|-|-|  
|TypeName|IdentifiersShouldBeCasedCorrectly|  
|CheckId|CA1709|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Ukončování řádků - při sestavení, obory názvů, typy, členů a parametry.<br /><br /> Non narušující - při vyvolání na parametry obecného typu.|  
  
## <a name="cause"></a>příčina  
 Název identifikátoru není použita správně.  
  
 \- nebo –  
  
 Název identifikátoru obsahuje zkratku dvoupísmenným a druhé písmeno je malá písmena.  
  
 \- nebo –  
  
 Název identifikátoru obsahuje zkratka tři nebo více velkých písmen.  
  
## <a name="rule-description"></a>Popis pravidla  
 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje křivky learning, který je vyžadován pro nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.  
  
 Podle konvence použijte názvy parametrů camelCase; obor názvů, typ a člen názvy použít Pascal velká a malá písmena. V názvu ve formátu camelCase první písmeno je malá písmena a je první písmeno všechny zbývající slova v názvu na velká písmena. Příklady ve formátu camelCase názvů jsou "packetSniffer", "ioFile" a "fatalErrorCode". V názvu použita Pascal je první písmeno velké a první písmeno všechny zbývající slova v názvu je na velká písmena. Příkladem použita Pascal názvy jsou "PacketSniffer", "IOFile" a "FatalErrorCode".  
  
 Toto pravidlo rozdělí název na slova založené na malá a velká písmena a kontroluje všechny dvoupísmenným slova proti seznam běžných dvoupísmenným slova, jako jsou "V" nebo "Moje". Pokud není nalezena shoda, předpokládá se jako zkratka slovo. Kromě toho toto pravidlo předpokládá, že nalezl zkratka, pokud název obsahuje buď čtyři velká písmena v řádku, nebo v řádku na konci názvu tři velká písmena.  
  
 Podle konvence, použijte dva znaky velkými písmeny a režim tři nebo více znaků pomocí Pascal velká a malá písmena. Následující příklady používají tyto zásady vytváření názvů: "DB", "Vy", "Cpa" a 'Ecma'. Následující příklady porušují konvence: "Io" ", 'XML' a 'DoD' a pro názvy nonparameter, 'xp' a 'panelu'.  
  
 'ID, je použita zvláštní způsobit narušení tohoto pravidla. 'Id' není zkratka, ale je zkratkou pro "Identifikace".  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Změňte název tak, aby je použita správně.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit toto upozornění, pokud máte vlastní zásady vytváření názvů, nebo pokud identifikátor představuje názvu, třeba název společnosti nebo technologii.  
  
 Můžete také přidat konkrétní podmínky, zkratky a zkratky to vlastní slovník analýzy kódu. Podmínky zadané ve slovníku vlastní nezpůsobí porušení toto pravidlo. Další informace najdete v tématu [postupy: přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)