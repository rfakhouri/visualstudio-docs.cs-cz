---
title: "Přesunout deklarace proměnné téměř odkaz v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: ghogen
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: d19a348ff21abce181f971c798d61cde393f4689
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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
     - Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přesunout deklarace téměř odkaz** z okna náhledu – místní nabídka.
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

[Refactoring](../refactoring-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)