---
title: 'DA0011: Náročná metoda CompareTo | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0011
- vs.performance.rules.DAExpensiveCompareTo
- vs.performance.11
- vs.performance.rules.DA0011
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e3a1d51f66050837c05f81315f4f368749cea1b4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53872430"
---
# <a name="da0011-expensive-compareto"></a>DA0011: Náročná metoda CompareTo

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