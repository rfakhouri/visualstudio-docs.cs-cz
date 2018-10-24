---
title: Odebrání nedosažitelného kódu, refaktoring v sadě Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: dd06fb7cd7b0e31df777a488c34a59e5a036e3b8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49836382"
---
# <a name="remove-unreachable-code-refactoring"></a>Odebrání nedosažitelného kódu refaktoringu

Tento refaktoring platí pro:

- C#

**Co:** odebere kód, který se nikdy proveden.

**Kdy:** program neobsahuje žádné cestu k fragmentu kódu, provádění zbytečné tento fragment kódu.

**Důvod, proč:** zlepšit čitelnost a udržovatelnosti odebráním kód, který je nadbytečný a nikdy se spustí.

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