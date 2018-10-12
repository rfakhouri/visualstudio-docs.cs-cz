---
title: 'DA0011: Náročná metoda CompareTo | Dokumentace Microsoftu'
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
- vs.performance.DA0011
- vs.performance.rules.DAExpensiveCompareTo
- vs.performance.11
- vs.performance.rules.DA0011
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0726ef4eb93d3e962e5fa39fe9cc7acbdbfbe8ca
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49210441"
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

