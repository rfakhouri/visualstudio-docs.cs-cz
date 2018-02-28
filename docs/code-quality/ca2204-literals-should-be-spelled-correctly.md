---
title: "CA2204: Literály by měly být zadány správně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ad1fb951f17d223f248c678738070d1c5b70ae7d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204: Literály by měly být zadány správně
|||  
|-|-|  
|TypeName|LiteralsShouldBeSpelledCorrectly|  
|CheckId|CA2204|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Metoda předává řetězcový literál, na který se používá v parametru nebo vlastnost, která vyžaduje lokalizovaný řetězec a řetězcového literálu obsahuje jeden nebo více slova, která nerozpoznal kontrola pravopisu knihovně společnosti Microsoft.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo zkontroluje řetězcový literál, který je předán jako hodnotu parametru nebo vlastnost, pokud jeden nebo více následujících případech platí:  
  
-   <xref:System.ComponentModel.LocalizableAttribute> Atribut parametru nebo vlastnosti je nastaven na hodnotu true.  
  
-   Název parametru nebo vlastnost obsahuje "Text", "Zpráva" nebo "Titulek".  
  
-   Název parametru řetězce, který je předaný metodě Console.Write nebo Console.WriteLine je "value" nebo "format".  
  
 Toto pravidlo analyzuje řetězcového literálu do slova, tokenizaci složených slov a kontroluje, zda každý word/token. Informace o analýzy algoritmus najdete v tématu [CA1704: identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
 Ve výchozím nastavení se používá verze Angličtina (en) nástroj pro kontrolu pravopisu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, opravte pravopis aplikace word nebo přidat slovo do slovníku. Informace o tom, jak používat vlastní slovník najdete v tématu [postupy: přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Správně hláskovaným slova redukovat křivku vyžaduje nové knihovny softwaru.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)