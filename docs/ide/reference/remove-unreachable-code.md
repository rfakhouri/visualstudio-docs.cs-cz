---
title: Odebrat nedostupný kód refaktoring v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: douge
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: 2c4e142582e4ee3a3e0308c5368c58fac79f8c6f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="remove-unreachable-code-refactoring"></a>Odebrat refaktoring nedostupný kódu

Tato refaktoring platí pro:

- C#

**Co:** odebere kód, který bude nikdy spuštěn.

**Kdy:** vašeho programu nemá žádnou cestu na fragment kódu, provedení nepotřebné tento fragment kódu.

**Důvod:** zlepšení čitelnosti a jeho udržovatelnost odebráním kód, který je nadbytečné a nebude nikdy provedena.

## <a name="how-to"></a>Postupy

1. Umístěte ukazatel myši na libovolné místo v vybledlé se kód, který nedostupný:

![Barevně nedostupný kódu](media/unreachablecode-faded-cs.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **odebrat nedostupný kód** z okna náhledu – místní nabídka.
   - **Myš**
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **odebrat nedostupný kód** z okna náhledu – místní nabídka.

1. Když budete spokojeni se změnami, stiskněte **Enter** nebo klikněte na opravit v nabídce a změny budou potvrzeny.

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

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)