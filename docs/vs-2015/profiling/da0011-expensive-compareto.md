---
title: 'DA0011: Náročná metoda CompareTo | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.DA0011
- vs.performance.rules.DAExpensiveCompareTo
- vs.performance.11
- vs.performance.rules.DA0011
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9958e9ec729591aa89c97d4f1d23a819e7b7eeb6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676927"
---
# <a name="da0011-expensive-compareto"></a>DA0011: Náročná metoda CompareTo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio 2017, najdete v části [DA0011: náročná metoda CompareTo](https://docs.microsoft.com/visualstudio/profiling/da0011-expensive-compareto) na webu docs.microsoft.com.  
  
|||  
|-|-|  
|Id pravidla|DA0011|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování<br /><br /> Paměť .NET|  
|Zpráva|Funkce CompareTo by měly být levné a nepřidělovat paměti. Snižte složitost funkce CompareTo Pokud je to možné.|  
|Typ pravidla|Upozornění|  
  
## <a name="cause"></a>příčina  
 Metoda CompareTo typu je nákladné nebo přidělí paměť.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metoda CompareTo metody by měla být efektivní a by neměl přidělení paměti.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Metoda CompareTo zjednodušit.

