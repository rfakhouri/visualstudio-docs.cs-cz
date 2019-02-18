---
title: Převést anonymní typ na třídu
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e3613f365b2510111f6854087a597df387ab1a4c
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335914"
---
# <a name="convert-anonymous-type-to-class"></a>Převést anonymní typ na třídu

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
