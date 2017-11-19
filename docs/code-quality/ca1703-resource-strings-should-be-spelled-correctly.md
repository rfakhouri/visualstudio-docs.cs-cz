---
title: "CA1703: Řetězce prostředků by měly být zadány správně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9c7828aa218933208408a285510e998921d6f032
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 Toto pravidlo analyzuje řetězec prostředku do slova (tokenizaci složených slov) a kontroluje, zda každý word/token. Informace o analýzy algoritmus najdete v tématu [CA1704: identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
 Ve výchozím nastavení se používá verze Angličtina (en) nástroj pro kontrolu pravopisu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, použijte dokončení slova, která jsou správně napsán, nebo přidejte slova do slovníku. Informace o tom, jak používat vlastní slovník najdete v tématu [CA1704: identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Správně hláskovaným slova zkrátit čas, který je potřeba další nové knihovny softwaru.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1701: Složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
 [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)