---
title: "DA0011: Náročná metoda CompareTo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0011
- vs.performance.rules.DAExpensiveCompareTo
- vs.performance.11
- vs.performance.rules.DA0011
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f916fd9bc7be5425f76ec23e6c7dd2fa60d7fb03
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0011-expensive-compareto"></a>DA0011: Náročná metoda CompareTo
|||  
|-|-|  
|Id pravidla|DA0011|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování<br /><br /> Využívání paměti rozhraním .NET|  
|Zpráva|Funkce CompareTo by měl být levných a není přidělit paměť. Pokud je to možné snížit složitost CompareTo funkce.|  
|Typ pravidla|Upozornění|  
  
## <a name="cause"></a>příčina  
 Metoda CompareTo typu je nákladné nebo přidělí paměť.  
  
## <a name="rule-description"></a>Popis pravidla  
 CompareTo metody by měla být efektivní a neměli přidělit paměť.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Metoda CompareTo zjednodušit.