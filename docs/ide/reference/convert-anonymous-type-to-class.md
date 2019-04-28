---
title: Převést anonymní typ na třídu
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: f29e31fb87d8b18e7f5a46d16f90217ee08d51f6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62968524"
---
# <a name="convert-anonymous-type-to-class"></a>Převedení anonymního typu na třídu

Tento refaktoring platí pro:

- C#

**Co:** Převeďte anonymní typ třídy.

**Kdy:** Máte anonymního typu, který chcete pokračovat v sestavení ve třídě.

**Proč:** Anonymní typy jsou užitečné, používáte pouze jejich místně. S růstem vašeho kódu, je dobré mít snadný způsob, jak je převést na třídu.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor anonymního typu.
2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

   ![Převést anonymní typ na třídu](media/convert-anon-to-class.png)

2. Stisknutím klávesy **Enter** tak, aby přijímal operací refaktoringu.

   ![Převést anonymní typ na třídu přijato](media/convert-anon-to-class-complete.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
