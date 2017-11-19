---
title: "CA1600: Nepoužívejte prioritu nečinného procesu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e52a658bd6161542ce909b8294f33d6e4bf140ba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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