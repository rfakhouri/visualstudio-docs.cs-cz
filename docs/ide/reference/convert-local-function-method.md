---
title: Převod místní funkce na metodu
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
ms.openlocfilehash: 96064b16e53081e0456ed43275acd5edf7ead468
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58152951"
---
# <a name="convert-local-function-to-method"></a>Převod místní funkce na metodu

Tento refaktoring platí pro:

- C#
- Visual Basic

**Co:** Převést metodu místní funkce

**Kdy:** Máte místní funkci, kterou chcete definovat mimo aktuální místní kontext.

**Proč:** Můžete chtít převést místní funkci na metodu, takže ho můžete volat mimo místní kontext. Můžete chtít převést na metodu, když lokální funkce je stále příliš dlouhý. Definování v samostatné metodě díky váš kód lépe čitelný.

## <a name="convert-local-function-to-method-refactoring"></a>Převést místní funkci na refaktoring – metoda

1. Umístěte kurzor místní funkci.

    ![Převod místní funkce na metodu](media/convert-local-function-to-method.png)

2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

    ![Převést místní funkci na opravu kódu – metoda](media/convert-local-function-to-method-codefix.png)

2. Stisknutím klávesy **Enter** tak, aby přijímal operací refaktoringu.

    ![Převést na výsledek metody místní funkce](media/convert-local-function-to-method-result.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)
