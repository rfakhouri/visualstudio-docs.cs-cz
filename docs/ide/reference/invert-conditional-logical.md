---
title: Invertování podmíněných výrazů a logických operací
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
ms.openlocfilehash: a35f5949bee6cb3c4fbcbf9ba6a9b501d54b2014
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/04/2019
ms.locfileid: "57325255"
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
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)
