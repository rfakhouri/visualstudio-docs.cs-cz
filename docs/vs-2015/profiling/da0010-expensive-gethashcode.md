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
ms.openlocfilehash: 111e3204224f1124476ab2a324df7be2b6ef2525
ms.sourcegitcommit: 3201da3499051768ab59f492699a9049cbc5c3c6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58354827"
---
# <a name="da0010-expensive-gethashcode"></a>DA0010: Náročná funkce GetHashCode
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio, naleznete v tématu [DA0010: Náročná metoda GetHashCode](https://docs.microsoft.com/visualstudio/profiling/da0010-expensive-gethashcode) na webu docs.microsoft.com.  

  

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
 Generování hodnoty hash je postup pro rychlé vyhledání určité položky v kolekci velké. Protože zatřiďovacích tabulek můžou být hodně velké a musí podporovat velmi vysoký objem přístup, musí být velmi efektivní zatřiďovacích tabulek. Nepřímo tento požadavek je, že metoda GetHashCode metody v rozhraní .NET Framework by neměl přidělení paměti. Přidělování paměti zvyšuje zatížení systému uvolňování paměti a zpřístupňuje metodu na potenciální zpoždění, pokud je nutné spustit uvolňování paměti jako výsledek požadavku na přidělení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zjednodušit metody.
