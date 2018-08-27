---
title: 'CA1601: Nepoužívejte časovače, které zabraňují změně stavu napájení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: de1b5e943274b80d8a46d05dcd0cdb8fe8b2b82a
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900558"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: Nepoužívejte časovače, které zabraňují změně stavu napájení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1601: Nepoužívejte časovače, které zabraňují změně stavu napájení](https://docs.microsoft.com/visualstudio/code-quality/ca1601-do-not-use-timers-that-prevent-power-state-changes).

|||
|-|-|
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|
|CheckId|CA1601|
|Kategorie|Microsoft.Mobility|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Časovač se interval je nastavená na dojít k více než jednou za sekundu.

## <a name="rule-description"></a>Popis pravidla
 Nedotazuje častěji než jednou za sekundu nebo použití časovače, ke kterým dochází častěji, než jeden čas za sekundu. Vyšší frekvence periodické aktivity budou udržovat procesor zaneprázdněný a ovlivňovat časovače úspory energie nečinnosti, které vypnou zobrazení a pevné disky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Nastavte časovač intervalech, dojde k nejméně jednou za sekundu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto pravidlo má výjimka potlačit pouze v případě aktivaci časovače více než jednou za sekundu je povinný a důležité informace o nastavení mobilních zařízení můžete bezpečně ignorovat.



