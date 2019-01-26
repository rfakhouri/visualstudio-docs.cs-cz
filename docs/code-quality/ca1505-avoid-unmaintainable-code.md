---
title: 'CA1505: Vyhněte se neudržovatelnému kódu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 085f3b5ad38e846880d39e813550301a81066745
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957179"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Vyhněte se neudržovatelnému kódu

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Typ nebo metoda má nízkou hodnotu indexu udržovatelnosti.

## <a name="rule-description"></a>Popis pravidla
 Index udržovatelnosti se vypočítává pomocí následující metriky: řádky kódu, program svazku a cyklomatická složitost. Program svazek je míra obtížnost znalost typ nebo metoda, která je založena na počet operátorů a operandů v kódu. Cyklomatická složitost je míra složitosti strukturální typ nebo metodu. Další informace o metriky kódu na [měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/code-metrics-values.md).

 Nízký index udržovatelnosti označuje, že typ nebo metodu je pravděpodobně obtížné udržovat a by být dobrým kandidátem, aby změnit návrh.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud chcete vyřešit toto porušení, změnit návrh typu nebo metodě a zkuste ho rozdělte do menších a přesněji zaměřené typy a metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Vylučte toto upozornění, když se typ nebo metoda je stále považovány za udržovatelného bez ohledu na její velikost nebo typu nebo metodě nelze rozdělit.

## <a name="see-also"></a>Viz také:

- [Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md)
- [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/code-metrics-values.md)