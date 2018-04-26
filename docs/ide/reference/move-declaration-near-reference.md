---
title: Deklarace proměnné přesunutí téměř odkaz v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: douge
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: e98f7b7e9df0a1df3482257c70a661aa22d5980a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="move-declaration-near-reference-refactoring"></a>Přesuňte deklaraci téměř refaktoring odkaz

Tato refaktoring platí pro:

- C#

**Co:** můžete přesouvat deklarace proměnných blíže k jejich využití.

**Kdy:** máte deklarace proměnných, které se dají v užší oboru.

**Důvod:** může nechat, jak je, ale které může způsobit problémy čitelnost nebo skrytí informace. Toto je možnost refactor ke zlepšení čitelnosti.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor deklarace proměnné.

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přesunout deklarace téměř odkaz** z okna náhledu – místní nabídka.
   - **Myš**
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **přesunout deklarace téměř odkaz** z okna náhledu – místní nabídka.

1. Když budete spokojeni se změnami, stiskněte **Enter** nebo klikněte na opravit v nabídce a změny budou potvrzeny.

Příklad:

```csharp
// Before
int x;
if (condition)
{
    x = 1;
    Console.WriteLine(x);
}

// Move declaration near reference

// After
if (condition)
{
    int x = 1;
    Console.WriteLine(x);
}
```

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)