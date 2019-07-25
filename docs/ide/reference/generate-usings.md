---
title: Generování příkazů using
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
helpviewer_keywords:
- add missing usings
ms.openlocfilehash: d971bcdaca4efdf587c7e441f1b0b28d21388dee
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416476"
---
# <a name="add-missing-usings-in-visual-studio"></a>Přidat chybějící použití v aplikaci Visual Studio

Tato generace kód platí pro:

- C#

**Co:** Umožňuje okamžitě přidat potřebné importy nebo [příkazy using](/dotnet/csharp/language-reference/keywords/using-statement) pro kód kopírování a vložení.

**Kdy:** Je běžné postup kopírování kódu z různých míst v projektu nebo jiných zdrojů a jejich vložení do nového kódu. Tato rychlá akce najde chybějící příkazy importu pro kód kopírování a vložení a zobrazí výzvu k jejich přidání.

**Proč:** Vzhledem k tomu, že rychlá akce automaticky přidává nezbytné importy, nemusíte `using` ručně kopírovat příkazy, které váš kód potřebuje.

## <a name="add-missing-usings-refactoring"></a>Přidat refaktoring chybějících použití

1. Zkopírujte kód ze souboru a vložte ho do nového bez zahrnutí nezbytných `using` příkazů. Výsledná chyba je doprovázena opravou kódu, která přidá chybějící `using` příkazy.

    > [!NOTE]
    > Tento návrh je nutné povolit v **nabídce nástroje > možnosti > textový Editor > C# > direktivy Pokročilé > Using**.

2. Vyberte CTRL +. Otevřete nabídku **rychlé akce a** refaktoringy.

    ![Generování příkazů using](media/generate-using-codefix.png)

3. Vyberte **možnost \<použít váš\>odkaz;** Chcete-li přidat chybějící odkaz.

    ![Generovat výsledek použití](media/generate-using-result.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
- [Tipy pro vývojáře .NET](../csharp-developer-productivity.md)
