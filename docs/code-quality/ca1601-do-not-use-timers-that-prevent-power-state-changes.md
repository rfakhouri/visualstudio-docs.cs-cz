---
title: 'CA1601: Nepoužívejte časovače, které zabraňují změně stavu napájení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 033c7a73c404a2bd5146a17a1a7b4f2fa8b9c540
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45545710"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: Nepoužívejte časovače, které zabraňují změně stavu napájení
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