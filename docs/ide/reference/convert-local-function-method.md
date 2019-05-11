---
title: Převést metodu místní funkce
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: ccddc3aef24ba14245dc568ca5f369e38ce8eba0
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531638"
---
# <a name="convert-a-local-function-to-a-method"></a>Převést metodu místní funkce

Tento refaktoring platí pro:

- C#
- Visual Basic

**Co:** Lokální funkce převeďte na metodu.

**Kdy:** Máte místní funkci, kterou chcete definovat mimo aktuální místní kontext.

**Proč:** Má být převeden místní funkci do metody tak, aby při volání mimo místní kontext. Můžete chtít převést na metodu, když lokální funkce je stále příliš dlouhý. Při definici funkce v samostatné metodě, je váš kód lépe čitelný.

## <a name="convert-local-function-to-method-refactoring"></a>Převést místní funkci na refaktoring – metoda

1. Umístěte kurzor místní funkci.

    ![Převést místní funkci na ukázku kódu – metoda](media/convert-local-function-to-method.png)

2. Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

    ![Převést místní funkci na ukázku opravu kódu – metoda](media/convert-local-function-to-method-codefix.png)

2. Stisknutím klávesy Enter můžete potvrdit přijetí operací refaktoringu.

    ![Místní funkce CONVERT ukázku výsledek – metoda](media/convert-local-function-to-method-result.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../csharp-developer-productivity.md)
