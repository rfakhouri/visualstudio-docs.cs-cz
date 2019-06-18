---
title: Dělení a slučování příkazů if
ms.date: 06/12/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 405ccd4bc0197ce06aa14982a16dc02f6d13a537
ms.sourcegitcommit: d4920babfc3d24a3fe1d4bf446ed3fe73b344467
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/17/2019
ms.locfileid: "67160720"
---
# <a name="split-or-merge-if-statements"></a>Dělení a slučování příkazů if

Tento refaktoring platí pro:

- C#

**Co:** **Co:** Dělené tunelové propojení nebo sloučení [Pokud](/dotnet/csharp/language-reference/keywords/if-else) příkazy.

**Kdy:** Chcete rozdělit `if` příkaz, který se používá `&&` nebo `||` operátory do vnořený `if` příkazu nebo sloučení `if` příkaz s vnějším `if` příkaz.

**Proč:** Je na vás předvolby stylu.  

## <a name="how-to"></a>Postupy

Pokud chcete rozdělit `if` – příkaz:

1. Umístěte ukazatel myši v `if` prohlášení `&&` nebo `||` operátor.

2. Stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

    ![Rozdělení If – příkaz](../media/split-if-statement.png)

3. Vyberte **rozdělit na if vnořené příkazy**.

    ![Rozdělení If kompletní – příkaz](../media/split-if-statement-complete.png)

Pokud chcete sloučit vnitřní `if` příkaz s vnější `if` – příkaz: 

1. Umístěte kurzor vnitřní `if` – klíčové slovo.

2. Stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

    ![Sloučit, pokud – příkaz](../media/merge-if-statement.png)

3. Vyberte **sloučit s vnější if – příkaz**.

    ![Sloučit, pokud příkaz dokončení](../media/merge-if-statement-complete.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)