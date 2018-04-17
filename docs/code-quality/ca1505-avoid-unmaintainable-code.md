---
title: 'CA1505: Vyhněte se neudržovatelnému kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4338b73aab38b1d63f4d4015c3a1fe1e1d292932
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Vyhněte se neudržovatelnému kódu
|||  
|-|-|  
|TypeName|AvoidUnmantainableCode|  
|CheckId|CA1505|  
|Kategorie|Microsoft.Maintainability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Typ nebo metoda má nízkou hodnotu indexu udržovatelnosti.  
  
## <a name="rule-description"></a>Popis pravidla  
 Index udržovatelnosti se vypočítává pomocí následující metriky: řádky kódu, program svazku a složitost cyclomatic. Program svazek je míra potíže se Principy typ nebo metoda, která je založena na počtu operátory a operandy v kódu. Složitost Cyclomatic se rozumí míra složitosti strukturální typ nebo metoda. Další informace o kódu metriky [měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md).  
  
 Index nízkou udržovatelnosti označuje, že typ nebo metoda je pravděpodobně poměrně složitá a může být vhodným kandidátem změnit návrh.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li odstranit tento porušení, přepracovat typ nebo metoda a pokuste se ho rozdělit na menší a zaměřují se více typů nebo metody.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Vylučte toto upozornění, když typ nebo metoda se přesto považuje za udržovatelného ohledu na jeho velké nebo typ nebo metoda nelze rozdělit.  
  
## <a name="see-also"></a>Viz také  
 [Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md)   
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)