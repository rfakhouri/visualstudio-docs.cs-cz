---
title: Převedení příkazu switch na výraz switch
ms.date: 06/19/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: cc13cffe8352d9fb57f5bb991c3af615eddb2a14
ms.sourcegitcommit: b56dc6fadc6c924beed36bb4c2ccc16cf6bcfa1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/02/2019
ms.locfileid: "68740064"
---
# <a name="convert-switch-statement-to-switch-expression"></a>Převedení příkazu switch na výraz switch

Tento refaktoring platí pro:

- C#

**Co:** Převod [příkazu switch](/dotnet/csharp/language-reference/keywords/switch) na C# [výraz přepínače](/dotnet/csharp/whats-new/csharp-8#switch-expressions)8,0.

**Kdy:** Chcete převést `switch` příkaz `switch` na výraz a naopak. 

**Proč:** Pokud používáte pouze výrazy, tento refaktoring umožňuje snadnou přechod z tradičních `switch` příkazů.

## <a name="how-to"></a>Postupy

1. V souboru projektu [nastavte jazykovou verzi Preview](/dotnet/csharp/language-reference/configure-language-version#edit-the-project-file) , protože `switch` výrazy jsou novou C# funkcí 8,0.
2. Umístěte kurzor `switch` do klíčového slova a stiskněte klávesu **CTRL**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
3. Vyberte **převést příkaz switch na výraz**.

   ![Převedení příkazu switch na výraz switch](media/convert-switch-statement-to-switch-expression.png) 

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
