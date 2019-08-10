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
ms.openlocfilehash: c37affc585653807912d00c1cfe365853fd6260b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921814"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: Nepoužívejte prioritu nečinného procesu

|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|Kategorie|Microsoft.Mobility|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Toto pravidlo nastane, pokud jsou procesy nastaveny `ProcessPriorityClass.Idle`na.

## <a name="rule-description"></a>Popis pravidla
Nenastavujte prioritu procesu na Neaktivní. Procesy, které `System.Diagnostics.ProcessPriorityClass.Idle` budou zabírat procesor, pokud by jinak byly nečinné, a zablokují proto pohotovostní režim.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Nastavte procesy na `ProcessPriorityClass.BelowNormal`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Toto pravidlo by mělo být potlačeno pouze v případě, že je vyžadována priorita nečinného procesu a je možné bezpečně ignorovat požadavky na mobilitu.