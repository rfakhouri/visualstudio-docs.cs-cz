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
ms.openlocfilehash: 0ce1b620a6d8aba7e4aea767745891dff6d9f869
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62790029"
---
# <a name="generate-usings-in-visual-studio"></a>Generovat direktivy using v sadě Visual Studio

Tato generace kód platí pro:

- C#

**Co:** Umožňuje okamžitě přidat nezbytných importů nebo [příkazy using](/dotnet/csharp/language-reference/keywords/using-statement) pro kopírování a vložení kódu.

**Kdy:** Je běžnou praxí zkopírovat kód z různých míst v projektu nebo jiných zdrojů a vložte ji do nového kódu. Tato rychlá akce vyhledá chybějící importuje příkazy pro kopírování a vložení kódu a potom vás vyzve, abyste je přidat.

**Proč:** Protože rychlá akce automaticky přidá nezbytných importů, není nutné ručně zkopírovat `using` příkazy, které potřebuje váš kód.

## <a name="generate-usings-refactoring"></a>Generovat refaktoring direktivy using

1. Zkopírujte kód ze souboru a vložte ho do nového objektu bez zahrnutí nezbytné `using` příkazy. Výsledná chyba je přiložena opravu kódu, který přidá chybějící `using` příkazy.

    > [!NOTE] 
    > Je nutné povolit tohoto návrhu v **nástroje > Možnosti > textový Editor > C# > Upřesnit > direktivy Using**.

2. Vyberte kombinaci kláves Ctrl +. Chcete-li otevřít **rychlé akce a Refaktoringy** nabídky.

    ![Generování příkazů using](media/generate-using-codefix.png)

3. Vyberte **pomocí \<referenci\>;** přidat chybějící odkaz.

    ![Generovat výsledek direktivy using](media/generate-using-result.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)
