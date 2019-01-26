---
title: 'DA0013: Vysoké použití String.Split nebo String.Substring | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.13
- vs.performance.rules.DAAvoidStringSubstr
- vs.performance.DA0013
- vs.performance.rules.DA0013
helpviewer_keywords:
- vs.performance.13
- vs.performance.rules.DA0013
ms.assetid: f501f423-bef9-4e08-bf96-c9ac9957e5a2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e261a0822622ec7a2c404539c3cd53f5daf9b67a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54989910"
---
# <a name="da0013-high-usage-of-stringsplit-or-stringsubstring"></a>DA0013: Vysoké použití String.Split nebo String.Substring

|||  
|-|-|  
|Id pravidla|DA0013|  
|Kategorie|Informace o používání rozhraní .NET framework|  
|Metod profilace|Vzorkování|  
|Zpráva|Zvažte snížení použití funkcí String.Split a String.Substring.|  
|Typ pravidla|Upozornění|  

## <a name="cause"></a>Příčina  
 Volání metody System.String.Split nebo System.String.Substring jsou podstatnou část dat profilování. Zvažte použití System.String.IndexOf nebo System.String.IndexOfAny Pokud testujete existenci podřetězce v řetězci.  

## <a name="rule-description"></a>Popis pravidla  
 Metoda Split funguje na objekt řetězce a vrátí nové pole řetězců obsahující podřetězců původní. Funkce přiděluje paměť pro vrácený objekt pole a přiděluje nový objekt řetězce pro každý prvek pole, které nalezne. Substr – metoda podobně funguje na objekt řetězce a vrátí nový řetězec, který je ekvivalentní k požadovaný dílčí řetězec.  

 Pokud Správa přidělování paměti je velmi důležité ve vaší aplikaci, zvažte použití metody String.Split a String.Substr alternativy. Metoda IndexOf nebo IndexOfAny například můžete použít k vyhledání konkrétní podřetězce v rámci znak řetězec bez vytvoření nové instance třídy řetězec.  

## <a name="how-to-investigate-a-warning"></a>Zkoumání upozornění  
 Dvakrát klikněte na tuto zprávu najdete v **seznam chyb** okno a přejděte [zobrazení podrobností funkce](../profiling/function-details-view.md) odběru vzorků data profilu. Zkontrolujte volání funkcí najít v částech programu, které se používají nejvíce často System.String.Split nebo System.String.Substr metody. Pokud je to možné použijte metodu IndexOf nebo IndexOfAny vyhledání konkrétní podřetězce v rámci znak řetězec bez vytvoření nové instance třídy řetězec.