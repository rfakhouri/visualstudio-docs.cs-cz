---
title: Upozornění udržovatelnosti | Dokumentace Microsoftu
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
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 53e4763ecc4e9f36dd402f33bfad30e5795c1814
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666539"
---
# <a name="maintainability-warnings"></a>Upozornění udržovatelnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [upozornění udržovatelnosti](https://docs.microsoft.com/visualstudio/code-quality/maintainability-warnings).  
  
Upozornění udržovatelnosti podporují údržby knihovny a aplikace.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA1500: Názvy proměnných by neměly odpovídat názvům polí](../code-quality/ca1500-variable-names-should-not-match-field-names.md)|Metoda instance deklaruje parametr nebo místní proměnná, jejíž název odpovídá poli instance deklarovaného typu, což vede k chybám.|  
|[CA1501: Vyhněte se nadměrné dědičnosti](../code-quality/ca1501-avoid-excessive-inheritance.md)|Typ je více než čtyři úrovně hluboko v hierarchii dědičnosti. Hluboce vnořené hierarchie typů může být obtížné sledovat, pochopit a udržovat.|  
|[CA1502: Vyhněte se nadměrné složitosti](../code-quality/ca1502-avoid-excessive-complexity.md)|Toto pravidlo měří počet lineárně nezávislých cest skrze metodu, což je určeno počtem a složitostí podmínkových větví.|  
|[CA1504: Revize zavádějících názvů polí](../code-quality/ca1504-review-misleading-field-names.md)|Název pole instance začíná řetězcem "s_", nebo název statické (sdílené v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) pole začíná předponou "m_".|  
|[CA1505: Vyhněte se neudržovatelnému kódu](../code-quality/ca1505-avoid-unmaintainable-code.md)|Typ nebo metoda má nízkou hodnotu indexu udržovatelnosti. Nízký index udržovatelnosti označuje, že typ nebo metodu je pravděpodobně obtížné udržovat a je vhodné ji znovu navrhnout.|  
|[CA1506: Vyhněte se nadměrnému párování tříd](../code-quality/ca1506-avoid-excessive-class-coupling.md)|Toto pravidlo měří párování tříd podle počtu jedinečných odkazů na typ, které typ nebo metoda obsahuje.|  
  
## <a name="see-also"></a>Viz také  
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



