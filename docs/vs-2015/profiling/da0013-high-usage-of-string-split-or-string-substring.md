---
title: 'DA0013: Vysoké použití String.Split nebo String.Substring | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06e738444b2a8e3e888da406097e94fbc9e10a28
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49198689"
---
# <a name="da0013-high-usage-of-stringsplit-or-stringsubstring"></a>DA0013: Vysoké použití String.Split nebo String.Substring
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id pravidla | DA0013 |  
| Kategorie |. Informace o používání .NET Framework |  
| Metod profilace | Vzorkování |  
| Zpráva | Zvažte snížení použití funkcí String.Split a String.Substring. |  
| Typ pravidla | Upozornění |  
  
## <a name="cause"></a>příčina  
 Volání metody System.String.Split nebo System.String.Substring jsou podstatnou část dat profilování. Zvažte použití System.String.IndexOf nebo System.String.IndexOfAny Pokud testujete existenci podřetězce v řetězci.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metoda Split funguje na objekt řetězce a vrátí nové pole řetězců obsahující podřetězců původní. Funkce přiděluje paměť pro vrácený objekt pole a přiděluje nový objekt řetězce pro každý prvek pole, které nalezne. Substr – metoda podobně funguje na objekt řetězce a vrátí nový řetězec, který je ekvivalentní k dílčí řetězec, který byl vyžádán.  
  
 Pokud Správa přidělování paměti je velmi důležité ve vaší aplikaci, zvažte použití metody String.Split a String.Substr alternativy. Například můžete použít metoda IndexOf nebo IndexOfAny vyhledání konkrétní podřetězce v rámci znak řetězec bez vytvoření nové instance třídy řetězec.  
  
## <a name="how-to-investigate-a-warning"></a>Zkoumání upozornění  
 Dvakrát klikněte na zprávu v okně Seznam chyb, přejděte [zobrazení podrobností funkce](../profiling/function-details-view.md) odběru vzorků data profilu. Zkontrolujte volání funkcí najít v částech programu, které se používají nejvíce často System.String.Split nebo System.String.Substr metody. Pokud je to možné, použijte metoda IndexOf nebo IndexOfAny vyhledání konkrétní podřetězce v rámci znak řetězec bez vytvoření nové instance třídy řetězec.



