---
title: Převést smyčku foreach na LINQ
ms.date: 02/20/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 7893ed676372cce94d883353139de91ef639aeb0
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531850"
---
# <a name="convert-a-foreach-loop-to-linq"></a>Převést smyčku foreach na LINQ

Tento refaktoring platí pro:

- C#

**Co:** Umožňuje snadno převést vaše *foreach* smyčku, která se používá hodnota IEnumerable dotazu LINQ nebo formuláře volání LINQ (označované také jako LINQ metoda).

**Kdy:** Máte smyčku foreach, která používá použití rozhraní IEnumerable, a chcete smyčky číst jako dotaz LINQ.

**Proč:** Chcete použít syntaxi LINQ spíše než smyčku foreach. [LINQ](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq) zadá dotaz do typů prvotřídní jazykové konstrukce v C#. LINQ můžete snížit množství kódu v souboru, aby byl kód lépe čitelný a povolit různých zdrojů dat. podobné vzorce výrazu dotazu.

> [!NOTE]
> Syntaxi LINQ je obvykle méně efektivní než smyčku foreach. Je dobré znát žádné úkor výkonu, které může dojít při použití LINQ pro lepší čitelnost kódu.

## <a name="convert-a-foreach-loop-to-linq-refactoring"></a>Převést smyčku foreach na refaktoring LINQ

1. Umístěte ukazatel myši v `foreach` – klíčové slovo.

    ![Ukázka IEnumerable foreach](media/convert-foreach-to-LINQ.png)

2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

   ![Převést na nabídku ukázky LINQ](media/convert-foreach-to-LINQ-codefix.png)

3. Vyberte **převést na LINQ** nebo **převést na Linq (volání formulář)**.

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
- [Okno předchozích změn](../../ide/preview-changes.md)
- [Tipy pro vývojáře .NET](../csharp-developer-productivity.md)
