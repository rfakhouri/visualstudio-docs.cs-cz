---
title: Refaktorovat kód, který převede dotazu LINQ příkazu foreach
ms.date: 05/15/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e8d19f86578e2aebda4e6c497d0c2d89c4826d8f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960149"
---
# <a name="refactoring-to-convert-linq-to-a-foreach-statement"></a>Refaktoring pro převod LINQ na příkazu foreach

Použít tento Refaktoring a převést [syntaxe dotazů LINQ](/dotnet/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq) k [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkazu.

Tento refaktoring platí pro:

- C#

## <a name="how-to-use-it"></a>Jak ji použít

1. Vybrat celý LINQ dotaz počáteční s `from`.

   > [!NOTE]
   > Tento refaktoring můžete použít jenom pro převod vyjádřit pomocí syntaxe dotazu a nikoli syntaxe využívající metody dotazů LINQ.

1. Stisknutím klávesy **Ctrl**+**.** nebo klikněte na tlačítko šroubovák ![šroubovák ikonu](../media/screwdriver-icon.png) ikonu na okraji na soubor kódu.

   ![Převést na foreach nabídky rychlé akce LINQ](media/convert-linq-to-foreach.png)

1. Vyberte **převést na "foreach"**. Nebo vyberte **náhled změn** otevřít [náhled změn](../../ide/preview-changes.md) dialogového okna a pak vyberte **použít**.

> [!NOTE]
> Pro C#, kód vygenerovaný tyto refaktoringy používá explicitního typu nebo [var](/dotnet/csharp/language-reference/keywords/var) pro proměnné iterace `foreach` smyčky. Typ v generovaném kódu explicitní nebo implicitní, závisí na nastavení stylu kódu, které jsou v oboru. Tato nastavení konkrétního stylu kódu jsou konfigurována na úrovni počítače v rámci **nástroje** > **možnosti** > **textový Editor**  >  **C#**  >  **Styl kódu** > **Obecné** > **\'var' Předvolby**, nebo na úrovni řešení [EditorConfig](../../ide/editorconfig-code-style-settings-reference.md#implicit-and-explicit-types) souboru. Pokud změníte nastavení stylu kódu v **možnosti**, znovu otevřete soubor kódu pro změny projevily.

## <a name="see-also"></a>Viz také:

- [LINQ](/dotnet/standard/using-linq)
- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)