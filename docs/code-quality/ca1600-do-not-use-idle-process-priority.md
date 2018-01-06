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
ms.workload: multiple
ms.openlocfilehash: 2d1646cd587295f2854399cfc24603ce1f1910e6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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