---
title: Převést smyčku foreach na LINQ
descritpion: Convert any foreach loop that uses an IEnumerable to a LINQ query or a LINQ call form (also known as a LINQ method).
ms.date: 02/20/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: baa1f32bb981e6d244555baef2a00d03933cdd6c
ms.sourcegitcommit: 0f5f7955076238742f2071d286ad8e896f3a6cad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2019
ms.locfileid: "68483722"
---
# <a name="convert-a-foreach-loop-to-linq"></a>Převést smyčku foreach na LINQ

Tento refaktoring platí pro:

- C#

**Co:** Umožňuje snadno převést smyčku *foreach* , která používá rozhraní IEnumerable pro dotaz LINQ nebo formulář volání LINQ (označované také jako metoda LINQ).

**Kdy:** Máte smyčku foreach, která používá rozhraní IEnumerable a chcete, aby se tato smyčka četla jako dotaz LINQ.

**Proč:** Dáváte přednost použití syntaxe LINQ spíše než smyčky foreach. [LINQ](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq) provede dotaz do konstrukce jazyka první třídy v C#. LINQ může snížit množství kódu v souboru, usnadnit čtení kódu a umožnit různým zdrojům dat, aby měly podobné vzory výrazů dotazů.

> [!NOTE]
> Syntaxe LINQ je obvykle méně efektivní než smyčka foreach. Je dobré si uvědomit o všech kompromisech s výkonem, které mohou nastat při použití jazyka LINQ ke zlepšení čitelnosti kódu.

## <a name="convert-a-foreach-loop-to-linq-refactoring"></a>Převést smyčku foreach na refaktoring LINQ

1. Umístěte kurzor do `foreach` klíčového slova.

    ![Foreach s použitím ukázky IEnumerable](media/convert-foreach-to-LINQ.png)

2. Stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

   ![Ukázka převodu na nabídku LINQ](media/convert-foreach-to-LINQ-codefix.png)

3. Vyberte možnost **převést na LINQ** nebo **převést na LINQ (formulář volání)** .

   ![Ukázka výsledku dotazu LINQ](media/convert-foreach-to-LINQ-result.png)

   ![Ukázka výsledku formuláře volání LINQ](media/convert-foreach-to-LINQ-callform-result.png)

### <a name="sample-code"></a>Ukázka kódu

```csharp
using System.Collections.Generic;

public class Class1
{
    public void MyMethod()
    {
        var greetings = new List<string>()
            { "hi", "yo", "hello", "howdy" };

        IEnumerable<string> enumerable()
        {
            foreach (var greet in greetings)
            {
                if (greet.Length < 3)
                {
                    yield return greet;
                }
            }

            yield break;
        }
    }
}
```

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Okno Náhled změn](../../ide/preview-changes.md)
- [Tipy pro vývojáře .NET](../csharp-developer-productivity.md)
