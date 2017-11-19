---
title: "CA1502: Vyhněte se nadměrné složitosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidExcessiveComplexity
- CA1502
helpviewer_keywords:
- CA1502
- AvoidExcessiveComplexity
ms.assetid: d735454b-2f8f-47ce-907d-f7a5a5391221
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3c45ca232b555af1441502586a38c80f43c41edc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1502-avoid-excessive-complexity"></a>CA1502: Vyhněte se nadměrné složitosti
|||  
|-|-|  
|TypeName|AvoidExcessiveComplexity|  
|CheckId|CA1502|  
|Kategorie|Microsoft.Maintainability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Metoda má nadměrnému cyclomatic složitost.  
  
## <a name="rule-description"></a>Popis pravidla  
 *Složitost Cyclomatic* měří počet lineárně nezávislé cesty prostřednictvím metody, které je určen podle počtu a složitost podmíněného větve. Složitost nízkou cyclomatic obvykle označuje metodu, která je snadno pochopit, testování a údržbu. Složitost cyclomatic se počítá z grafu toku řízení metody a je zadána v následujícím způsobem:  
  
 složitost cyclomatic = počet okraje - počet uzlů + 1  
  
 kde uzel představuje bod větve logiku a okraj představuje řádek mezi uzly.  
  
 Pravidlo hlásí narušení složitost cyclomatic po více než 25.  
  
 Další informace o kódu metriky [měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md),  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, Refaktorovat metodu ke snížení jeho složitost cyclomatic.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné upozornění toto pravidlo potlačit, pokud nelze snadno snížit složitost a metoda je snadno pochopit, testování a údržbu. Konkrétně, metodu, která obsahuje velké `switch` (`Select` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) příkaz je kandidátem pro vyloučení. Riziko destabilizing kód základní pozdní v cyklu vývoje nebo představení nečekaným změnám v chování za běhu v dříve dodané kódu může pomocí převažují nad přínosy udržovatelnosti refaktoring kódu.  
  
## <a name="how-cyclomatic-complexity-is-calculated"></a>Jak se počítá Cyclomatic složitost  
 Složitost cyclomatic se počítá přidáním 1 takto:  
  
-   Počet větví (například `if`, `while`, a `do`)  
  
-   Počet `case` příkazy v`switch`  
  
 Následující příklady ukazují metody, které mají různou cyclomatic složité kroky.  
  
## <a name="example"></a>Příklad  
 **Složitost Cyclomatic 1**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_1.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_1.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_1.cs)]  
  
## <a name="example"></a>Příklad  
 **Složitost Cyclomatic 2**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_2.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_2.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_2.cs)]  
  
## <a name="example"></a>Příklad  
 **Složitost Cyclomatic 3**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_3.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_3.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_3.cs)]  
  
## <a name="example"></a>Příklad  
 **Složitost Cyclomatic 8**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_4.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_4.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_4.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1501: Vyhněte se nadměrné dědičnosti](../code-quality/ca1501-avoid-excessive-inheritance.md)  
  
## <a name="see-also"></a>Viz také  
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)