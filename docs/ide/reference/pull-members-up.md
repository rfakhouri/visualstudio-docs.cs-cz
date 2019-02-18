---
title: Dotyčného členy
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 65ce1b44063fd6152fc300e32e7dd075fa8afcbf
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335930"
---
# <a name="pull-members-up"></a>Dotyčného členy

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje, aby si vyžádat členové základního typu.

**Kdy:** Jste implementovali rozhraní a chcete přesunout člen základního typu.

**Proč:** Stahování členů umožňuje jiným implementacím rozhraní dědit i ty členy.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor žádný člen implementovaného rozhraní.
2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

   ![Dotyčného členy](media/pull-members-up.png)

2. Vyberte **o přijetí změn členové základní typ**.

3. V dialogovém okně vyberte co mohou členové, které chcete přidat do vybraného rozhraní.

   ![Člen dotyčného](media/pull-members-up-dialog.png)

4. Zvolte **OK**. Vybraní členové se berou do rozhraní.

   ![Dotyčného člen dokončené](media/pull-members-up-completed.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
