---
title: Refaktorování kódu var místo explicitního typu
ms.date: 05/15/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 893fc2f989dab579690cdac37edae3ba0fad606a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53869135"
---
# <a name="refactoring-to-replace-var-with-an-explicit-type"></a>Refaktoring pro var místo explicitního typu

Použít tento refaktoring k nahrazení [var](/dotnet/csharp/language-reference/keywords/var) v deklaraci lokální proměnné explicitního typu.

Tento refaktoring platí pro:

- C#

## <a name="why-to-use-an-explicit-type"></a>Proč použít explicitní typ

Toto jsou některé důvody pro deklarování proměnné explicitního typu:

- Aby se zlepšila čitelnost kódu.

- Pokud nechcete inicializovat proměnné v prohlášení.

Ale [var](/dotnet/csharp/language-reference/keywords/var) musí být použita při proměnná je inicializována pomocí anonymního typu a vlastnosti objektu jsou přístupné později. Další informace najdete v tématu [implicitně typované lokální proměnné (C#)](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables).

## <a name="how-to-use-it"></a>Jak ji použít

1. Ustaví blikající kurzor `var` – klíčové slovo.

1. Stisknutím klávesy **Ctrl**+**.** nebo klikněte na tlačítko šroubovák ![šroubovák ikonu](../media/screwdriver-icon.png) ikonu na okraji na soubor kódu.

   ![Použít explicitní typ nabídky rychlé akce](media/use-explicit-type.png)

1. Vyberte **použít explicitní typ**. Nebo vyberte **náhled změn** otevřít [náhled změn](../../ide/preview-changes.md) dialogového okna a pak vyberte **použít**.

## <a name="see-also"></a>Viz také:

- [Implicitně typované proměnné (C#)](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)
- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)