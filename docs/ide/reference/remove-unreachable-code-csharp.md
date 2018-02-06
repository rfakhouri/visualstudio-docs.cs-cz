---
title: "Odebrat nedostupný kódu refaktoringu pro jazyk C# v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: ghogen
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 12b6910aad6399b72b3e4bc10e6b857cc98c09bb
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="remove-unreachable-code-in-c"></a>Odebrat nedostupný kód v jazyce C# #

**Co:** odebere kód, který bude nikdy spuštěn.

**Kdy:** vašeho programu nemá žádnou cestu na fragment kódu, provedení nepotřebné tento fragment kódu.

**Důvod:** zlepšení čitelnosti a jeho udržovatelnost odebráním kód, který je nadbytečné a nebude nikdy provedena.

**Postupy:**

1. Umístěte ukazatel myši na libovolné místo v vybledlé se kód, který nedostupný:

![Barevně nedostupný kódu](media/unreachablecode-faded-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **odebrat nedostupný kód** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **odebrat nedostupný kód** z okna náhledu – místní nabídka.

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

[Refactoring](../refactoring-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)