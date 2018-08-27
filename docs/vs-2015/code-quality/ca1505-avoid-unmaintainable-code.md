---
title: 'CA1505: Vyhněte se neudržovatelnému kódu | Dokumentace Microsoftu'
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
ms.openlocfilehash: ee836af1ee0030c3eea56e12ea5fe767c4b7255b
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902003"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Vyhněte se neudržovatelnému kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1505: Vyhněte se neudržovatelnému kódu](https://docs.microsoft.com/visualstudio/code-quality/ca1505-avoid-unmaintainable-code).

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



