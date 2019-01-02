---
title: Refaktorovat kód, který převede smyčky for k příkazu foreach
ms.date: 05/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 85a8d0c5644d1a7daf342b9524e75f7969b3781a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53888189"
---
# <a name="refactoring-to-convert-between-a-for-loop-and-a-foreach-statement"></a>Refaktoring pro převod mezi smyčky a příkazu foreach

Tento článek popisuje rychlé akce refaktoringů, převádět mezi dvěma struktur opakování. Zahrnuje některé důvody, proč můžete chtít přepínání [pro](/dotnet/csharp/language-reference/keywords/for) smyčky a [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkaz v kódu.

## <a name="convert-a-for-loop-to-a-foreach-statement"></a>Převést smyčky for k příkazu foreach

Pokud máte [pro](/dotnet/csharp/language-reference/keywords/for) smyčka v kódu, můžete tento refaktoring převeďte ho na [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkaz.

Tento refaktoring platí pro:

- C#

> [!NOTE]
> **Převést na foreach** refaktoring rychlá akce je dostupná jenom pro [pro](/dotnet/csharp/language-reference/keywords/for) smyček, které obsahují všechny tři části: inicializátor, podmínky a iterátor.

### <a name="why-convert"></a>Proč převést

Důvodů, proč můžete chtít převést [pro](/dotnet/csharp/language-reference/keywords/for) smyčku do [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkazu zahrnout:

- Proměnná místního smyčky uvnitř smyčka s výjimkou jako index nepoužívejte pro přístup k položkám.

- Chcete zjednodušit kód a snížit pravděpodobnost, že logických chyb v inicializátoru, podmínky a části iterátoru.

### <a name="how-to-use-it"></a>Jak ji použít

1. Umístit váš kurzor v `for` – klíčové slovo.

1. Stisknutím klávesy **Ctrl**+**.** nebo klikněte na tlačítko šroubovák ![šroubovák ikonu](../media/screwdriver-icon.png) ikonu na okraji na soubor kódu.

   ![Převést na foreach nabídky](media/convert-to-foreach.png)

1. Vyberte **převést na "foreach"**. Nebo vyberte **náhled změn** otevřít [náhled změn](../../ide/preview-changes.md) dialogového okna a pak vyberte **použít**.

## <a name="convert-a-foreach-statement-to-a-for-loop"></a>Převod příkazu foreach k smyčku for

Pokud máte [foreach (C#)](/dotnet/csharp/language-reference/keywords/foreach-in) nebo [For Each... Další (Visual Basic)](/dotnet/visual-basic/language-reference/statements/for-each-next-statement) příkaz v kódu, můžete použít tento refaktoring pro převod na [pro](/dotnet/csharp/language-reference/keywords/for) smyčky.

Tento refaktoring platí pro:

- C#

- Visual Basic

### <a name="why-convert"></a>Proč převést

Důvodů, proč můžete chtít převést [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) příkazu [pro](/dotnet/csharp/language-reference/keywords/for) smyčky patří:

- Chcete použít proměnnou místní smyčky uvnitř smyčka pro víc než jenom přístup k položce.

- Jste [iterace iteraci vícerozměrné pole](/dotnet/csharp/programming-guide/arrays/using-foreach-with-arrays) a chcete mít větší kontrolu nad prvky pole.

### <a name="how-to-use-it"></a>Jak ji použít

1. Umístit váš kurzor v `foreach` nebo `For Each` – klíčové slovo.

1. Stisknutím klávesy **Ctrl**+**.** nebo klikněte na tlačítko šroubovák ![šroubovák ikonu](../media/screwdriver-icon.png) ikonu na okraji na soubor kódu.

   ![Převést na nabídku](media/convert-to-for.png)

1. Vyberte **převést na hodnotu 'pro'**. Nebo vyberte **náhled změn** otevřít [náhled změn](../../ide/preview-changes.md) dialogového okna a pak vyberte **použít**.

1. Protože operací refaktoringu zavádí nové proměnné iterace počet **přejmenovat** pole se zobrazí v pravém horním rohu editoru. Pokud chcete zvolit jiný název pro proměnnou, zadejte jej a stiskněte klávesu **Enter** nebo vyberte **použít** v **přejmenovat** pole. Pokud nechcete zvolte název nové, stiskněte **Esc** nebo vyberte **použít** zrušíte **přejmenovat** pole.

> [!NOTE]
> Pro C#, kód vygenerovaný tyto refaktoringy používá explicitního typu nebo [var](/dotnet/csharp/language-reference/keywords/var) pro typ položky v kolekci. Typ v generovaném kódu explicitní nebo implicitní, závisí na nastavení stylu kódu, které jsou v oboru. Tato nastavení konkrétního stylu kódu jsou konfigurována na úrovni počítače v rámci **nástroje** > **možnosti** > **textový Editor**  >  **C#**  >  **Styl kódu** > **Obecné** > **\'var' Předvolby**, nebo na úrovni řešení [EditorConfig](../../ide/editorconfig-code-style-settings-reference.md#implicit-and-explicit-types) souboru. Pokud změníte nastavení stylu kódu v **možnosti**, znovu otevřete soubor kódu pro změny projevily.

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)