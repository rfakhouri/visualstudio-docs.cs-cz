---
title: Převést smyčku foreach na LINQ
ms.date: 02/20/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: dc0f94d6aa9f13ac038f1af19a1ab1c78158ea14
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/04/2019
ms.locfileid: "57325336"
---
# <a name="convert-foreach-loop-to-linq"></a>Převést smyčku foreach na LINQ

Tento refaktoring platí pro:

- C#

**Co:** Umožňuje snadno převést vaše smyčky foreach pomocí IEnumerables do formuláře volání LINQ (označované také jako LINQ metoda) nebo dotazu LINQ.

**Kdy:** Pokud máte smyčku foreach, která používá IEnumerable, který budete chtít přečíst, protože dotaz LINQ.

**Proč:** Někdy uživatelé možná dáte přednost použití syntaxe LINQ spíše, která smyčku foreach. [LINQ](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq) provede dotaz typů prvotřídní jazykové konstrukce v C#. LINQ můžete snížit množství kódu v souboru, snadněji čitelné a povolit různých zdrojů dat. podobné vzorce výrazu dotazu.

> [!NOTE]
> LINQ syntaxe je výkonné, obvykle během méně než smyčky foreach. Je dobré znát žádné kompromisy výkonu zakážete, bude může způsobit při zlepšení čitelnosti kódu pomocí jazyka LINQ.

## <a name="convert-foreach-loop-to-linq-refactoring"></a>Převést smyčku foreach na refaktoring LINQ

1. Umístěte ukazatel myši v `foreach` – klíčové slovo.

    ![Použití rozhraní IEnumerable foreach](media/convert-foreach-to-LINQ.png)

2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

   ![Převést na nabídku LINQ](media/convert-foreach-to-LINQ-codefix.png)

3. Vyberte **převést na LINQ** nebo **převést na Linq (volání formuláře)**

   ![Výsledku dotazu LINQ](media/convert-foreach-to-LINQ-result.png)
   
   ![Výsledek volání formuláře LINQ](media/convert-foreach-to-LINQ-callform-result.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)