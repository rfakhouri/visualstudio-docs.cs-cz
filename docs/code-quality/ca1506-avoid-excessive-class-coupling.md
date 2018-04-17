---
title: 'CA1506: Vyhněte se nadměrnému párování tříd | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 018abf05181be812bcf01fc9cb910745dc085bcf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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