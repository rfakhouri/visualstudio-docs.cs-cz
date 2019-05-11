---
title: Invertování podmíněných výrazů a logických operací
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
ms.openlocfilehash: 3931ae53fc29b0ffd8b8b6e96951a0f4786ff756
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531679"
---
# <a name="invert-conditional-expressions-and-conditional-andor-operators"></a>Invertovat podmíněné výrazy a podmíněné a/nebo operátory

Tento refaktoring platí pro:

- C#
- Visual Basic

**Co:** Umožňuje Invertovat podmíněný výraz nebo s podmínkou a operátorem.

**Kdy:** Podmíněný výraz nebo podmíněné a/nebo operátor, který by se lépe chápat, pokud obrácený.

**Proč:** Převrácení výraz nebo podmíněný nebo operátor ručně může trvat déle a potenciálně zavést chyby. Tato oprava kódu umožňuje udělat tento refaktoring automaticky.

## <a name="invert-conditional-expressions-and-conditional-andor-operators-refactoring"></a>Invertovat podmíněné výrazy a podmíněné nebo refaktoring operátory

1. Umístěte kurzor podmíněný výraz nebo s podmínkou a operátorem.
2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
3. Vyberte **invertování podmíněné** nebo **nahraďte ' & & "s" ||.**

    ![Invertovat podmíněné](media/invert-conditional.png)

    ![Invertovat podmíněné](media/invert-logical-operator.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../csharp-developer-productivity.md)
