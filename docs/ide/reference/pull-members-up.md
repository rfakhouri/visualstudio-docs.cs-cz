---
title: Dotyčného členy
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 2d1f7deb7aca1fed7b75b66b17ce2e4d63768a0d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58156070"
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
