---
title: 'CA1505: Vyhněte se neudržovatelnému kódu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d9d5dc976c27ca2459fa64b95fe0502579a500b8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68191216"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Vyhněte se neudržovatelnému kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Typ nebo metoda má nízkou hodnotu indexu udržovatelnosti.

## <a name="rule-description"></a>Popis pravidla
 Index udržovatelnosti se vypočítává pomocí následující metriky: řádky kódu, program svazku a cyklomatická složitost. Program svazek je míra obtížnost znalost typ nebo metoda, která je založena na počet operátorů a operandů v kódu. Cyklomatická složitost je míra složitosti strukturální typ nebo metodu. Další informace o metriky kódu na [měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md).

 Nízký index udržovatelnosti označuje, že typ nebo metodu je pravděpodobně obtížné udržovat a by být dobrým kandidátem, aby změnit návrh.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud chcete vyřešit toto porušení, změnit návrh typu nebo metodě a zkuste ho rozdělte do menších a přesněji zaměřené typy a metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Vylučte toto upozornění, když se typ nebo metoda je stále považovány za udržovatelného bez ohledu na její velikost nebo typu nebo metodě nelze rozdělit.

## <a name="see-also"></a>Viz také
 [Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md) [měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
