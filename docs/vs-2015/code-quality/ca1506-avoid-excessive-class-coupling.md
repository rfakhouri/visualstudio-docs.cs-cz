---
title: 'CA1506: Vyhněte se nadměrnému párování tříd | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: 1c5a5e070892f7efc096b0f8e24952bb9d139969
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189290"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Vyhněte se nadměrnému párování tříd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidExcessiveClassCoupling|
|CheckId|CA1506|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Narušující|

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
 [Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md) [měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
