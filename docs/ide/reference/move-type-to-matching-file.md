---
title: Přesun typu do odpovídajícího souboru refaktoring v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 73e1d9d67d905fed5eb37e29c1be1ba7677da3e8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49884144"
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>Přesunutí typu do odpovídajícího souboru refaktoring

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje vybraného typu přesuňte do samostatného souboru se stejným názvem.

**Kdy:** mít více tříd, struktur, rozhraní a podobně ve stejném souboru, který chcete oddělit.

**Důvod, proč:** umístěním více typů ve stejném souboru může být obtížné najít tyto typy. Přesunutím typů souborů se stejným názvem, bude kód čitelnější a přehlednější a díky tomu.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor mezi název typu, kde je definován. Příklad:

   ```csharp
   class Person
   ```

   ```vb
   Class Person
   ```

2. Dále proveďte jednu z následujících akcí:

   - Stisknutím klávesy **Ctrl**+**.**
   - Klikněte pravým tlačítkem na název typu a vyberte **rychlé akce a Refaktoringy**

1. Vyberte **přesunutí typu do *TypeName*.cs** z nabídky kde *TypeName* je název typu, který jste vybrali.

   Typ se přesune do nového souboru v projektu, který má stejný název jako typ.

   - C#:

      ![Výsledek inline-C#](media/movetype-result-cs.png)

   - Visual Basic:

      ![Výsledek inline - jazyka Visual Basic](media/movetype-result-vb.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
