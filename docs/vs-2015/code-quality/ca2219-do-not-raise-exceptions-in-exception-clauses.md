---
title: 'CA2219: Nevyvolávejte výjimky v klauzulích výjimky | Dokumentace Microsoftu'
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
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: dc951b8cfcefefe473eb7f5b19648da298b40792
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669358"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: Nevyvolávejte výjimky v klauzulích výjimky
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2219: nevyvolávejte výjimky v klauzulích výjimky](https://docs.microsoft.com/visualstudio/code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses).  
  
TypeName | DoNotRaiseExceptionsInExceptionClauses |  
| ID kontroly | CA2219 |  
| Kategorie | Microsoft.Usage|  
| Zásadní změna | Není zásadní, zásadní |  
  
## <a name="cause"></a>příčina  
 Z je vyvolána výjimka `finally`, filtr nebo klauzule fault.  
  
## <a name="rule-description"></a>Popis pravidla  
 Když v klauzuli výjimka je vyvolána výjimka, výrazně zvyšuje obtížnost ladění.  
  
 Když je výjimka vyvolána v `finally` nebo klauzule fault, nová výjimka skryje aktivní výjimku, pokud jsou k dispozici. To díky obtížné rozpoznání a ladění původní chyby.  
  
 Pokud je v klauzuli filtru vyvolána výjimka, modul runtime bezobslužně zachytí výjimku a způsobí, že byl filtr vyhodnocen na hodnotu false. Neexistuje žádný způsob, jak zjistit rozdíl mezi vyhodnocení filtru na hodnotu false a výjimky se vyvolat z filtru. Tím je obtížné rozpoznat a ladit chyby v logice filtru.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li vyřešit porušení tohoto pravidla, nevyvolávejte explicitně výjimky z `finally`, filtr nebo klauzule fault.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění tohoto pravidla. Nejsou žádné scénáře, kdy výjimka vyvolána v klauzuli výjimek poskytuje výhoda pro provádění kódu.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1065: Nevyvolávejte výjimky v neočekávaných umístěních](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)  
  
## <a name="see-also"></a>Viz také  
 [Upozornění ohledně návrhu](../code-quality/design-warnings.md)



