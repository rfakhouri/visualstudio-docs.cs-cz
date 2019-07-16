---
title: 'CA1600: Nepoužívejte prioritu nečinného procesu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 4002e17e3988ca3b449e141394ce762f95ffc78b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189299"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: Nepoužívejte prioritu nečinného procesu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
