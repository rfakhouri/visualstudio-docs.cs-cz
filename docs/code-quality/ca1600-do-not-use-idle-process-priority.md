---
title: 'CA1600: Nepoužívejte prioritu nečinného procesu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f3dcac11312b15049c743d596914b06819000801
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: Nepoužívejte prioritu nečinného procesu
|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|Kategorie|Microsoft.Mobility|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Toto pravidlo nastane, když procesy, které jsou nastaveny na `ProcessPriorityClass.Idle`.

## <a name="rule-description"></a>Popis pravidla
 Nenastavujte prioritu procesu na Neaktivní. Procesy, které mají `System.Diagnostics.ProcessPriorityClass.Idle` bude zabírat procesoru, pokud by se jinak mohly nečinnosti a proto bude blokovat pohotovostní režim.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Nastavit procesy na `ProcessPriorityClass.BelowNormal`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto pravidlo má být potlačeno jenom v případě, že prioritu nečinného procesu je povinná a důležité informace o nastavení mobilních zařízení můžete bezpečně ignorovat.