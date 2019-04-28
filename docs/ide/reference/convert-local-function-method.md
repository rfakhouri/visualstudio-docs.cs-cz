---
title: Převést metodu místní funkce
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
ms.openlocfilehash: a580077528c87e62f81e840ed6dee76ff1eac57f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62968271"
---
# <a name="convert-a-local-function-to-a-method"></a>Převést metodu místní funkce

Tento refaktoring platí pro:

- C#
- Visual Basic

**Co:** Lokální funkce převeďte na metodu.

**Kdy:** Máte místní funkci, kterou chcete definovat mimo aktuální místní kontext.

**Proč:** Má být převeden místní funkci do metody tak, aby při volání mimo místní kontext. Můžete chtít převést na metodu, když lokální funkce je stále příliš dlouhý. Při definici funkce v samostatné metodě, je váš kód lépe čitelný.

## <a name="convert-local-function-to-method-refactoring"></a>Převést místní funkci na refaktoring – metoda

1. Umístěte kurzor místní funkci.

    ![Převést místní funkci na ukázku kódu – metoda](media/convert-local-function-to-method.png)

2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

    ![Převést místní funkci na ukázku opravu kódu – metoda](media/convert-local-function-to-method-codefix.png)

2. Stisknutím klávesy Enter můžete potvrdit přijetí operací refaktoringu.

    ![Místní funkce CONVERT ukázku výsledek – metoda](media/convert-local-function-to-method-result.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)
