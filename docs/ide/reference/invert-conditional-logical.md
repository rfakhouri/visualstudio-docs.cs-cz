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
ms.openlocfilehash: 7d59b61cff622a9ba305ebfa86f7c0ebe3c00fe3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62422208"
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
