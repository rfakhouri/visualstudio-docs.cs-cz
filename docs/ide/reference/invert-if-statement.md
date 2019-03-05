---
title: Invertovat – příkaz
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: a6dd0a3ebdb41243734850cea4f4b43604ebb94b
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/04/2019
ms.locfileid: "57325276"
---
# <a name="invert-if-statement"></a>Invertovat – příkaz

Tento refaktoring platí pro:

- C#
- Visual Basic

**Co:** Umožňuje Invertovat `if` nebo `if else` příkaz beze změny význam kódu.

**Kdy:** Pokud máte `if` nebo `if else` příkaz, který by bylo lepší porozumění při obrácený.

**Proč:** Převrácení `if` nebo `if else` příkaz ručně může trvat déle a potenciálně zavést chyby. Tato oprava kódu umožňuje udělat tento refaktoring automaticky.

## <a name="invert-if-statement-refactoring"></a>Invertovat refaktoring – příkaz

1. Umístěte ukazatel myši v `if` nebo `if else` příkazu.

    ![Invertovat else](media/invert-if.png)

2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

    ![Invertovat else oprava kódu](media/invert-if-codefix.png)

3. Vyberte **Invertovat**.

    ![Invertovat jiný výsledek](media/invert-if-codefix-result.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)
