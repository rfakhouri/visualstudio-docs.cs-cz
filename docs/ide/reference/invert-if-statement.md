---
title: Invertování příkazů if
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: a0419100cbc5fcd543eb250fa85cbfe2ebd1c97f
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531592"
---
# <a name="invert-if-statement"></a>Invertování příkazů if

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

    ![Invertovat jiného kódu pro opravu](media/invert-if-codefix.png)

3. Vyberte **Invertovat**.

    ![Invertovat jiný výsledek](media/invert-if-codefix-result.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../csharp-developer-productivity.md)
