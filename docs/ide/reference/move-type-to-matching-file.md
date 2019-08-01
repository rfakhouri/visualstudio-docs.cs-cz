---
title: Přesun typu do odpovídajícího souboru refaktoring
description: Přesuňte typ do samostatného souboru se stejným názvem. Klikněte pravým tlačítkem na typ, vyberte rychlé akce a refaktoring a vyberte přesunout typ do <TypeName>. cs.
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 3021e08d3cfb601a67f51e53c97d2eba60c397a5
ms.sourcegitcommit: 0f5f7955076238742f2071d286ad8e896f3a6cad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2019
ms.locfileid: "68483657"
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>Přesunutí typu do odpovídajícího souboru refaktoring

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje přesunout vybraný typ do samostatného souboru se stejným názvem.

**Kdy:** Máte více tříd, struktur, rozhraní atd. ve stejném souboru, který chcete oddělit.

**Proč:** Umístěním více typů do stejného souboru může být obtížné tyto typy najít. Přesunutím typů souborů se stejným názvem, bude kód čitelnější a přehlednější a díky tomu.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor mezi název typu, kde je definován. Příklad:

   ```csharp
   class Person
   ```

   ```vb
   Class Person
   ```

2. Dále proveďte jednu z následujících akcí:

   - Stisknutím klávesy **Ctrl**+ **.**
   - Klikněte pravým tlačítkem na název typu a vyberte **rychlé akce a Refaktoringy**

1. Vyberte **přesunutí typu do *TypeName*.cs** z nabídky kde *TypeName* je název typu, který jste vybrali.

   Typ se přesune do nového souboru v projektu, který má stejný název jako typ.

   - C#:

      ![Výsledek inline-C#](media/movetype-result-cs.png)

   - Visual Basic:

      ![Výsledek inline - jazyka Visual Basic](media/movetype-result-vb.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
