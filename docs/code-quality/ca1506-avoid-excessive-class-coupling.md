---
title: 'CA1506: Vyhněte se nadměrnému párování tříd'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b655609548d3de293abe2adc0ec3fb5c6fcf297b
ms.sourcegitcommit: 36f5ffd6ae3215fe31837f4366158bf0d871f7a9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/08/2019
ms.locfileid: "59232480"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Vyhněte se nadměrnému párování tříd

|||
|-|-|
|TypeName|AvoidExcessiveClassCoupling|
|CheckId|CA1506|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Typ nebo metoda je párována s mnoho jiných typů.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo měří párování tříd podle počtu jedinečných odkazů na typ, které typ nebo metoda obsahuje.

Typy a metody, které mají vysokým stupněm párování tříd může být obtížné udržovat. Je vhodné mít typy a metody, které vykazují nízké párování a vysokou soudržnost.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Pokud chcete vyřešit toto porušení, zkuste změnit návrh typu nebo metodě, abyste snížili počet typů, ke kterým je připojen.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Vylučte toto upozornění, když se tento typ nebo metoda je považován za udržovatelného bez ohledu na jeho velký počet závislostí na jiné typy.

## <a name="see-also"></a>Viz také:

- [Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md)
- [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/code-metrics-values.md)