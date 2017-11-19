---
title: "CA1601: Nepoužívejte časovače, které zabraňují změně stavu napájení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5fc42c15beda68472f4a980fe96b0055b70a01cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: Nepoužívejte časovače, které zabraňují změně stavu napájení
|||  
|-|-|  
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|  
|CheckId|CA1601|  
|Kategorie|Microsoft.Mobility|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Časovač má intervalu nastavena na dojde k více než jednou za sekundu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Není dotazování častěji než jednou za sekundu, nebo použít časovačů, ke kterým dochází častěji, než jeden čas za sekundu. Vyšší frekvence periodické aktivity budou udržovat procesor zaneprázdněný a ovlivňovat časovače úspory energie nečinnosti, které vypnou zobrazení a pevné disky.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Nastavit intervaly časovače proběhnout menší než jednou za sekundu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Toto pravidlo má být potlačeno pouze v případě, že ohlásí časovač více než jednou za sekundu je povinná a důležité informace o nastavení mobilních zařízení můžete bezpečně ignorovat.