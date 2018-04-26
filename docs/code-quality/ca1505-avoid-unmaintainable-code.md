---
title: 'CA1505: Vyhněte se neudržovatelnému kódu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: 41600d40091ed2c656ab189a257a0ef2db6e0271
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
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
 [Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md) [měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)