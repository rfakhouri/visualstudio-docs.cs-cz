---
title: Použití výrazu lambda nebo textu bloku
ms.date: 02/14/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 5c46506e81e5334efea9060e957269e92e9d49cc
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531914"
---
# <a name="use-expression-body-or-block-body-for-lambda-expressions"></a>Používat text výrazu nebo blok textu pro výrazy lambda

Tento refaktoring platí pro:

- C#

**Co:** Umožňuje Refaktorovat výraz lambda definoval se použít tělo výrazu nebo bloku textu.

**Kdy:** Dáváte přednost výrazy lambda použít tělo výrazu nebo bloku textu.

**Proč:** Výrazy lambda je možné Refaktorovat pro lepší čitelnost podle vašich potřeb uživatelů.

## <a name="lambda-expression-body-or-block-body-refactoring"></a>Hlavní část výrazu lambda výrazu nebo refaktoring text bloku

1. Umístěte kurzor na pravé straně operátoru lambda.
2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

  ![Použít hlavní část výrazu lambda výraz/blokování](media/block-body-lambda.png)

3. Vyberte **text použití bloku pro výrazy lambda** nebo **používat text výrazu lambda výrazy**.

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../csharp-developer-productivity.md)