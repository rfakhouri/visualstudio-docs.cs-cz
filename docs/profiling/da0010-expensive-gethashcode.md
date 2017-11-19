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
ms.openlocfilehash: 9209d5f02d543cba3dd0dcec8f5492e2f64b9cef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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