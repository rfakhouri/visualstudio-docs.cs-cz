---
title: Přesunutí proměnné deklarace do blízkosti odkazu
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e23c5c8d6ea0895f9e5a78e726bb7a7cede071bb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62540593"
---
# <a name="move-declaration-near-reference-refactoring"></a>Přesunutí deklarace do blízkosti odkazu refaktoring

Tento refaktoring platí pro:

- C#

**Co:** Umožňuje přechod deklarace proměnných blíž k jejich využití.

**Kdy:** Deklarace proměnných, které mohou být v užší máte.

**Proč:** To může nechte, jak je, ale mohou způsobit problémy čitelnost nebo skrytí informace. Toto je příležitost dobře se Refaktorovat pro lepší čitelnost.

## <a name="how-to"></a>Postupy

1. Umístěte ukazatel myši v deklaraci proměnné.

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **přesunutí deklarace do blízkosti odkazu** z automaticky otevíraného okna okno náhledu.
   - **Myši**
      - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **přesunutí deklarace do blízkosti odkazu** z automaticky otevíraného okna okno náhledu.

1. Až budete spokojení s změny, stiskněte klávesu **Enter** nebo klikněte na opravit v nabídce a změny budou potvrzeny.

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

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)