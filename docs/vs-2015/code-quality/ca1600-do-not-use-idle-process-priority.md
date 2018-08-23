---
title: 'CA1600: Nepoužívejte prioritu nečinného procesu | Dokumentace Microsoftu'
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
ms.openlocfilehash: fdad25b5b3a6f8942e867cc074ef0fd51a0bdff4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629449"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: Nepoužívejte prioritu nečinného procesu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1600: Nepoužívejte prioritu nečinného procesu](https://docs.microsoft.com/visualstudio/code-quality/ca1600-do-not-use-idle-process-priority).  
  
TypeName | DoNotUseIdleProcessPriority |  
| ID kontroly | CA1600 |  
| Kategorie | Microsoft.Mobility|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Toto pravidlo vyvolá se v případě procesy jsou nastaveny na `ProcessPriorityClass.Idle`.  
  
## <a name="rule-description"></a>Popis pravidla  
 Nenastavujte prioritu procesu na Neaktivní. Procesy, které mají `System.Diagnostics.ProcessPriorityClass.Idle` budou zaměstnávat procesor, když by jinak byl nečinný a budou blokovat úsporný režim.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Nastavte procesy na `ProcessPriorityClass.BelowNormal`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Toto pravidlo má výjimka potlačit pouze v případě, že je vyžadován prioritu nečinného procesu a důležité informace o nastavení mobilních zařízení můžete bezpečně ignorovat.



