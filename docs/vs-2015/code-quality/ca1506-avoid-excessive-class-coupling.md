---
title: 'CA1506: Vyhněte se nadměrnému párování tříd | Dokumentace Microsoftu'
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
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1611c1861b9961fd953d63cb4d45a5c4e3b276db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666700"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Vyhněte se nadměrnému párování tříd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1506: Vyhněte se nadměrnému párování tříd](https://docs.microsoft.com/visualstudio/code-quality/ca1506-avoid-excessive-class-coupling).  
  
TypeName | AvoidExcessiveClassCoupling |  
| ID kontroly | CA1506 |  
| Kategorie | Microsoft.Maintainability|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Typ nebo metoda je párována s mnoho jiných typů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo měří párování tříd podle počtu jedinečných odkazů na typ, které typ nebo metoda obsahuje.  
  
 Typy a metody, které mají vysokým stupněm párování tříd může být obtížné udržovat. Je vhodné mít typy a metody, které vykazují nízké párování a vysokou soudržnost.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pokud chcete vyřešit toto porušení, zkuste změnit návrh typu nebo metodě, abyste snížili počet typů, ke kterým je připojen.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Vylučte toto upozornění, když se tento typ nebo metoda je stále považovány za udržovatelného bez ohledu na jeho velký počet závislostí na jiné typy.  
  
## <a name="see-also"></a>Viz také  
 [Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md)   
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



