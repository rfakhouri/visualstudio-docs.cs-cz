---
title: Odebrání nedosažitelného kódu refaktoringu
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: b1c88fbeb9daf293df868a835247098e2ce999e3
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55912518"
---
# <a name="remove-unreachable-code-refactoring"></a>Odebrání nedosažitelného kódu refaktoringu

Tento refaktoring platí pro:

- C#

**Co:** Odebere kód, který se nikdy proveden.

**Kdy:** Program neobsahuje žádné cestu k fragmentu kódu, provádění zbytečné tento fragment kódu.

**Proč:** Zlepšit čitelnost a udržovatelnosti odebráním kód, který je nadbytečný a nikdy se spustí.

## <a name="how-to"></a>Postupy

1. Umístíte kurzor kamkoliv v vyblednout si kód, který nedostupný:

![Vyblednout nedosažitelný kód](media/unreachablecode-faded-cs.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **odebrání nedosažitelného kódu** z automaticky otevíraného okna okno náhledu.
   - **Myši**
      - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **odebrání nedosažitelného kódu** z automaticky otevíraného okna okno náhledu.

1. Až budete spokojení s změny, stiskněte klávesu **Enter** nebo klikněte na opravit v nabídce a změny budou potvrzeny.

Příklad:

```csharp
// Before
private void Method()
{
    throw new Exception(nameof(Method));
    Console.WriteLine($"Exception for method {nameof(Method)}");
}

// Remove unreachable code

// After
private void Method()
{
    throw new Exception(nameof(Method));
}
```

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)