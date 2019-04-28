---
title: Přesun typu do odpovídajícího souboru refaktoring
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
ms.openlocfilehash: 31e3b12f6a19ea64e43f7a5e00e3c795cc7358e0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62540734"
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>Přesunutí typu do odpovídajícího souboru refaktoring

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje vybraného typu přesuňte do samostatného souboru se stejným názvem.

**Kdy:** Máte ve stejném souboru, který chcete použít k oddělení více tříd, struktur, rozhraní a podobně.

**Proč:** Umístěním více typů ve stejném souboru může ztěžovat vyhledávání těchto typů. Přesunutím typů souborů se stejným názvem, bude kód čitelnější a přehlednější a díky tomu.

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
