---
title: 'CA1600: Nepoužívejte prioritu nečinného procesu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a1774b3feb2da4939420bf75506892aac6dedd72
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955788"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: Nepoužívejte prioritu nečinného procesu

|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|Kategorie|Microsoft.Mobility|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Toto pravidlo vyvolá se v případě procesy jsou nastaveny na `ProcessPriorityClass.Idle`.

## <a name="rule-description"></a>Popis pravidla
 Nenastavujte prioritu procesu na Neaktivní. Procesy, které mají `System.Diagnostics.ProcessPriorityClass.Idle` budou zaměstnávat procesor, když by jinak byl nečinný a budou blokovat úsporný režim.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Nastavte procesy na `ProcessPriorityClass.BelowNormal`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto pravidlo má výjimka potlačit pouze v případě, že je vyžadován prioritu nečinného procesu a důležité informace o nastavení mobilních zařízení můžete bezpečně ignorovat.