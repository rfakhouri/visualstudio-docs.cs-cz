---
title: "CA1506: Vyhněte se nadměrnému párování tříd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8192868aa7c5d79039a5e94a2aa13c47ada5d47c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Vyhněte se nadměrnému párování tříd
|||  
|-|-|  
|TypeName|AvoidExcessiveClassCoupling|  
|CheckId|CA1506|  
|Kategorie|Microsoft.Maintainability|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ nebo metoda je spolu s mnoho dalších typů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo měří párování tříd podle počtu jedinečných odkazů na typ, které typ nebo metoda obsahuje.  
  
 Typy a metody, které mají vysoký stupeň párování tříd může být obtížné. Je dobrým zvykem typy a metody, které vykazují nízkou párování a vysokou soudržnost.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li odstranit tento porušení, zkuste změnit návrh typ nebo metoda a snížit počet typů, ke kterým je připojen.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Vylučte toto upozornění, když typ nebo metoda se přesto považuje za udržovatelného ohledu na jeho velký počet závislostí na jiné typy.  
  
## <a name="see-also"></a>Viz také  
 [Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md)   
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)