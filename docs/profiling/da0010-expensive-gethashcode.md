---
title: "DA0010: Náročná metoda GetHashCode | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DAExpensiveGetHashCode
- vs.performance.DA0010
- vs.performance.rules.DA0010
- vs.performance.10
ms.assetid: 3987e21a-5b4f-45e4-8a33-6b3f0a472c08
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ff2dbc1d98375b7199ab710412639fe4333c342d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0010-expensive-gethashcode"></a>DA0010: Náročná metoda GetHashCode
|||  
|-|-|  
|Id pravidla|DA0010|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování<br /><br /> Využívání paměti rozhraním .NET|  
|Zpráva|Funkce GetHashCode by měl být levných a není přidělit paměť. Pokud je to možné snížit složitost kódu funkce hash.|  
|Typ zprávy|Upozornění|  
  
## <a name="cause"></a>příčina  
 Volání metody GetHashCode typu jsou podstatnou část data profilování nebo metodu přidělí paměť.  
  
## <a name="rule-description"></a>Popis pravidla  
 Použití algoritmu hash je technika pro rychlé vyhledávání konkrétní položky v kolekci velké. Protože hash – tabulky může být velmi velké a nepotřebujete podporovat velké objemy přístup, musí být velmi efektivní zatřiďovacích tabulkách. Vyplývá tento požadavek je, že GetHashCode metody v rozhraní .NET Framework by neměla přidělit paměť. Přidělování paměti zvyšuje zatížení systému uvolňování paměti a zpřístupní metodu potenciální způsobuje prodlevy, pokud se stát, že bude nutné spustit uvolňování paměti v důsledku požadavek na přidělení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Snížit složitost metody.