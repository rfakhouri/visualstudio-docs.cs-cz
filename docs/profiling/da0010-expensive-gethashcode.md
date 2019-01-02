---
title: 'DA0010: Náročná metoda GetHashCode | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAExpensiveGetHashCode
- vs.performance.DA0010
- vs.performance.rules.DA0010
- vs.performance.10
ms.assetid: 3987e21a-5b4f-45e4-8a33-6b3f0a472c08
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4ddf59bdf6ad356a36a730982b7ac0b681bd66d3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53932337"
---
# <a name="da0010-expensive-gethashcode"></a>DA0010: Náročná metoda GetHashCode

|||  
|-|-|  
|Id pravidla|DA0010|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování<br /><br /> Paměť .NET|  
|Zpráva|Funkce GetHashCode by měly být levné a nepřidělovat paměti. Pokud je to možné snížit složitost funkce hodnoty hash.|  
|Typ zprávy|Upozornění|  

## <a name="cause"></a>příčina  
 Volání metody GetHashCode typu jsou podstatnou část dat profilování nebo metodu přidělí paměť.  

## <a name="rule-description"></a>Popis pravidla  
 Generování hodnoty hash je postup pro rychlé vyhledání určité položky v kolekci velké. Protože zatřiďovacích tabulek mohou být velké a musí podporovat velmi vysoký objem přístup, musí být efektivní zatřiďovacích tabulek. Nepřímo tento požadavek je, že metoda GetHashCode metody v rozhraní .NET Framework by neměl přidělení paměti. Přidělování paměti zvyšuje zatížení systému uvolňování paměti a zpřístupňuje metodu pro potenciální zpoždění, když bude nutné spustit uvolňování paměti jako výsledek požadavku na přidělení.  

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zjednodušit metody.