---
title: "CA2219: Není vyvolání výjimky v klauzulích výjimky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: da4b337ad0efb3a4876857bd07efb391dc040405
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: Nevyvolávejte výjimky v klauzulích výjimky
|||  
|-|-|  
|TypeName|DoNotRaiseExceptionsInExceptionClauses|  
|CheckId|CA2219|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Pevné dopadem na dřívější kód|  
  
## <a name="cause"></a>příčina  
 K výjimce `finally`, filtr nebo selhání klauzule.  
  
## <a name="rule-description"></a>Popis pravidla  
 Když dojde k výjimce v klauzuli výjimky, výrazně zvyšuje je obtížné ladění.  
  
 Pokud je vyvolána výjimka v `finally` nebo selhání klauzule novou výjimku skryje active výjimka, pokud je k dispozici. Díky tomu původní chyba obtížné zjistit a ladění.  
  
 Pokud v klauzuli filtru je vyvolána výjimka, modul runtime bezobslužně zachytí výjimky a způsobí, že filtr vyhodnotit na hodnotu false. Neexistuje žádný způsob, jak určit rozdíl mezi filtr vyhodnocení na hodnotu false a výjimku se výjimku z filtru. Díky tomu je obtížné zjistit a ladění chyby v jeho logiku.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li odstranit tento porušení toto pravidlo, není vyvolat explicitně výjimku z `finally`, filtr nebo selhání klauzule.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Není potlačení upozornění pro toto pravidlo. Neexistují žádné situací, za kterých výjimka vyvolána v klauzuli výjimka výhoda provádění kódu.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1065: Není vyvolání výjimky v neočekávaných umístěních](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)  
  
## <a name="see-also"></a>Viz také  
 [Upozornění ohledně návrhu](../code-quality/design-warnings.md)