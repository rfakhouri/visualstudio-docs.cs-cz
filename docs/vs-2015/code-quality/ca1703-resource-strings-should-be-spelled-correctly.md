---
title: 'CA1703: Řetězce prostředků by měly být zadány správně | Dokumentace Microsoftu'
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
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 017b0d2e12e990c1cb0c056182552983387820af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673226"
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703: Řetězce prostředků by měly být zadány správně
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1703: řetězce prostředků by měly být zadány správně](https://docs.microsoft.com/visualstudio/code-quality/ca1703-resource-strings-should-be-spelled-correctly).  
  
TypeName | ResourceStringsShouldBeSpelledCorrectly |  
| ID kontroly | CA1703 |  
| Kategorie | Microsoft.Naming|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Zdrojový řetězec obsahuje jedno nebo více slov, která knihovna kontroly pravopisu společnosti Microsoft nerozpoznala.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo analyzuje řetězec prostředku do slov (tokenizací složených slov) a zkontroluje pravopis pro každé slovo/token. Informace o analýze algoritmus, najdete v části [CA1704: identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
 Ve výchozím nastavení je použít nástroj pro kontrolu pravopisu verze Angličtina (en).  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, použijte celá slova, které jsou zadány správně nebo je přidat do slovníku. Informace o tom, jak použít vlastní slovníky najdete v tématu [CA1704: identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Správně hláskovaným slova zkrátit čas, který je potřeba další nové knihovny softwaru.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1701: Malá a velká písmena složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
 [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)



