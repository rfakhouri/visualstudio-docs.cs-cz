---
title: 'DA0010: Náročná metoda GetHashCode | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DAExpensiveGetHashCode
- vs.performance.DA0010
- vs.performance.rules.DA0010
- vs.performance.10
ms.assetid: 3987e21a-5b4f-45e4-8a33-6b3f0a472c08
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1055136562d59412a6187524dc6023c55ef2dc3c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59659030"
---
# <a name="da0010-expensive-gethashcode"></a>DA0010: Náročná funkce GetHashCode
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio, naleznete v tématu [DA0010: Náročná metoda GetHashCode](https://docs.microsoft.com/visualstudio/profiling/da0010-expensive-gethashcode).  

|||  
|-|-|  
|Id pravidla|DA0010|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování<br /><br /> Paměť .NET|  
|Zpráva|Funkce GetHashCode by měly být levné a nepřidělovat paměti. Pokud je to možné snížit složitost funkce hodnoty hash.|  
|Typ zprávy|Upozornění|  
  
## <a name="cause"></a>Příčina  
 Volání metody GetHashCode typu jsou podstatnou část dat profilování nebo metodu přidělí paměť.  
  
## <a name="rule-description"></a>Popis pravidla  
 Generování hodnoty hash je postup pro rychlé vyhledání určité položky v kolekci velké. Protože zatřiďovacích tabulek můžou být hodně velké a musí podporovat vysoký objem přístup, musí být velmi efektivní zatřiďovacích tabulek. Nepřímo tento požadavek je, že metoda GetHashCode metody v rozhraní .NET Framework by neměl přidělení paměti. Přidělování paměti zvyšuje zatížení systému uvolňování paměti a zpřístupňuje metodu pro potenciální zpoždění, když bude nutné spustit uvolňování paměti jako výsledek požadavku na přidělení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zjednodušit metody.
