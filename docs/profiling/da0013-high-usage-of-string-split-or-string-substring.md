---
title: "DA0013: Vysoké použití String.Split nebo String.Substring | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.13
- vs.performance.rules.DAAvoidStringSubstr
- vs.performance.DA0013
- vs.performance.rules.DA0013
helpviewer_keywords:
- vs.performance.13
- vs.performance.rules.DA0013
ms.assetid: f501f423-bef9-4e08-bf96-c9ac9957e5a2
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1101457388b5ba54752f47014c9c389fcb2cb073
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="da0013-high-usage-of-stringsplit-or-stringsubstring"></a>DA0013: Vysoké použití String.Split nebo String.Substring
|||  
|-|-|  
|Id pravidla|DA0013|  
|Kategorie|Pokyny pro používání rozhraní .NET framework|  
|Metod profilace|Vzorkování|  
|Zpráva|Zvažte snížení použití String.Split a String.Substring funkce.|  
|Typ pravidla|Upozornění|  
  
## <a name="cause"></a>příčina  
 Volání metody System.String.Split nebo System.String.Substring jsou podstatnou část data profilování. Zvažte použití System.String.IndexOf nebo System.String.IndexOfAny Pokud testujete existenci substring v řetězci.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metoda rozdělení funguje na objekt řetězce a vrátí nové pole řetězců obsahující dílčích řetězců původního. Funkce přidělí paměť pro objekt vrácený pole a přiděluje nový objekt řetězce pro každý element pole, které najde. Substr – metoda podobně pracuje na objekt řetězce a vrátí nové řetězec, který je ekvivalentní dílčí řetězec, který byl vyžádán.  
  
 Pokud Správa přidělení paměti je rozhodující ve vaší aplikaci, zvažte použití alternativních metod String.Split a String.Substr. Například můžete použít buď IndexOf nebo IndexOfAny metoda najít konkrétní podřetězce v rámci znak řetězec bez vytvoření nové instance třídy String.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [zobrazení podrobností funkce](../profiling/function-details-view.md) odběru data profilu. Zkontrolujte volání funkcí najít v částech programu, které využívají nejčastěji se vyskytující metod System.String.Split nebo System.String.Substr. Pokud je možné, použijte buď IndexOf nebo IndexOfAny metoda najít konkrétní podřetězce v rámci znak řetězec bez vytvoření nové instance třídy String.