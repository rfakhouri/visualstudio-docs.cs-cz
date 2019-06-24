---
title: Převést příkaz switch pro výraz switch
ms.date: 06/19/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: ecb7750301101a2607c17e68b5e919623a03caba
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2019
ms.locfileid: "67329095"
---
# <a name="convert-switch-statement-to-switch-expression"></a>Převést příkaz switch pro výraz switch

Tento refaktoring platí pro:

- C#

**Co:** Převést [switch – příkaz](/dotnet/csharp/language-reference/keywords/switch) k C# 8.0 [výraz switch](/dotnet/csharp/whats-new/csharp-8#switch-expressions).

**Kdy:** Má být převeden `switch` příkazu `switch` výraz a naopak. 

**Proč:** Pokud používáte pouze výrazy, tomuto refaktoringu umožňuje snadný přechod od tradiční `switch` příkazy.

## <a name="how-to"></a>Postupy

1. V souboru projektu [nastavit jazykovou verzi pro náhled](/dotnet/csharp/language-reference/configure-language-version#set-the-language-version-in-visual-studio) protože `switch` výrazy jsou novou C# 8.0 funkce.
2. Umístěte ukazatel myši v `switch` – klíčové slovo a stiskněte klávesu **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
3. Vyberte **příkazu switch převést na výraz**.

   ![Převést příkaz switch pro výraz switch](media/convert-switch-statement-to-switch-expression.png) 

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
