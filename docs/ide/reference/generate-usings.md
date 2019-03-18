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
ms.openlocfilehash: f59dceabb076ebce36755c41caa6de00258be883
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160638"
---
# <a name="generate-usings-in-visual-studio"></a>Generovat direktivy using v sadě Visual Studio

Tato generace kód platí pro:

- C#

**Co:** **Co:** Umožňuje okamžitě přidat nezbytných importů nebo [příkazy using](/dotnet/csharp/language-reference/keywords/using-statement) kopírování a vložení kódu.

**Kdy:** Je běžnou praxí zkopírujte a vložte kód z různých míst v projektu nebo jiných zdrojů kódu. Této rychlé akce analyzuje chybějící importy pro kopírování a vložení kódu a potom vás vyzve, abyste je přidat.

**Proč:** Automaticky přidáním nezbytných importů, že uživatel nemusí ručně zkopírovat potřebnou `using` příkazy.

## <a name="generate-usings-refactoring"></a>Generovat refaktoring direktivy using

1. Zkopírujte a vložte kód z jiného souboru bez zahrnutí nezbytné `using` příkazy. Chybu teď doplněny opravu kódu, který přidá chybějící `using` příkazy.

    > [!NOTE] 
    > Tento návrh musí být nastavená na on **nástroje > Možnosti > textový Editor > C# > Upřesnit > direktivy Using**.

2. Stisknutím klávesy **Ctrl**+**.** Chcete-li otevřít **rychlé akce a Refaktoringy** nabídky. 

    ![Generování příkazů using](media/generate-using-codefix.png)

3. Vyberte **pomocí \<referenci\>;** přidat chybějící odkaz.

    ![Generovat výsledek direktivy using](media/generate-using-result.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)