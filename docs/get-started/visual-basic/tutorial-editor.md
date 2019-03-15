---
title: Úvod do úprav pro vývojáře v jazyce Visual Basic
description: Tento úvod během 10 minut do editoru kódu v sadě Visual Studio jsou uvedeny některé ze způsobů, že sada Visual Studio provádí zápis, navigace a pochopení kódu jazyka Visual Basic jednodušší.
ms.custom: seodec18, get-started
ms.date: 11/20/2018
ms.technology: vs-ide-general
ms.topic: tutorial
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 3af730ae4d5b358eab223e2a5a8288daaf632071
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58069629"
---
# <a name="learn-to-use-the-code-editor"></a>Zjistěte, jak pomocí editoru kódu

V tomto úvodu během 10 minut do editoru kódu v sadě Visual Studio přidáme kód pro soubor, který chcete podívat na některé ze způsobů, že sada Visual Studio provádí zápis, procházení a porozumění kódu jednodušší.

> [!TIP]
> Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

Tento článek předpokládá, že jste již obeznámeni s jazykem Visual Basic. Pokud si nejste, doporučujeme vám podívejte se na kurz jako [Začínáme s jazykem Visual Basic v sadě Visual Studio](../../get-started/visual-basic/tutorial-console.md) první.

> [!TIP]
> Pokud chcete postupovat podle tohoto článku, ujistěte se, že máte nastavení jazyka Visual Basic vybraných pro Visual Studio. Informace o výběru nastavení pro integrované vývojové prostředí (IDE) najdete v tématu [vyberte nastavení prostředí](visual-studio-ide.md#select-environment-settings).

## <a name="create-a-new-code-file"></a>Vytvořte nový soubor kódu

Začněte tím, že vytváří se nový soubor a přidat nějaký kód do něj.

::: moniker range="vs-2017"

1. Otevřít Visual Studio.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřít Visual Studio. Stisknutím klávesy **Esc** nebo klikněte na tlačítko **pokračovat bez kódu** v okně start otevřete vývojové prostředí.

::: moniker-end

2. Z **souboru** nabídku v panelu nabídky zvolte **nový soubor**.

3. V **nový soubor** dialogovém okně **Obecné** kategorie, zvolte **třídy jazyka Visual Basic**a klikněte na tlačítko **otevřít**.

   Nový soubor se otevře v editoru pomocí kostru třídy jazyka Visual Basic. (Můžete už Všimněte si, že není nutné k vytvoření úplné projektu sady Visual Studio získáte některé výhody, které nabízí editor kódu, jako je například zvýraznění syntaxe. Vše, co potřebujete je soubor kódu.)

   ![Soubor kódu jazyka Visual Basic v sadě Visual Studio](media/tutorial-editor.png)

## <a name="use-code-snippets"></a>Používání fragmentů kódu

Visual Studio poskytuje užitečné *fragmenty kódu* , že vám pomůže rychle a snadno generovat běžně používá bloky kódu. [Fragmenty kódu](../../ide/code-snippets.md) jsou k dispozici pro různé programovací jazyky Visual Basic, včetně C#a C++. Přidejme jazyka Visual Basic **Sub** fragment kódu do souboru.

1. Umístěte ukazatel myši nad řádkem, který říká `End Class`a typ **sub**.

   Automaticky se zobrazí dialogové okno s informacemi o `Sub` – klíčové slovo a způsob, jak vložit **Sub** fragmentu kódu.

   ![Technologie IntelliSense pro fragment kódu v sadě Visual Studio](media/tutorial-intellisense-snippet.png)

1. Stisknutím klávesy **kartu** dvakrát pro vložení fragmentu kódu.

   Osnova pro proceduru Sub `MySub()` se přidá do souboru.

Fragmenty kódu k dispozici lišit pro různé programovací jazyky. Můžete si prohlédnout fragmenty kódu k dispozici v jazyce Visual Basic výběrem **upravit** > **IntelliSense** > **Vložit fragment** (nebo stiskněte klávesu  **CTRL**+**K**, **Ctrl**+**X**). V jazyce Visual Basic fragmenty kódu jsou k dispozici v těchto kategoriích:

![Seznam fragment kódu jazyka Visual Basic](media/tutorial-code-snippet-list.png)

Pokud soubor existuje na počítači, zápis do textového souboru, čtení hodnoty registru, provádění dotazu SQL, vytváření jsou fragmenty kódu pro určení [For Each... Další příkaz](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)a mnoho dalších.

## <a name="comment-out-code"></a>Okomentujte kód

Panel nástrojů, který je řádek tlačítek v panelu nabídek v sadě Visual Studio může pomoct zvýší vaši produktivitu při kódování. Například vám můžete přepnout režim dokončování IntelliSense, zvětšit nebo zmenšit odsazení řádku nebo okomentujte kód, které nemá pro kompilaci. ([IntelliSense](../../ide/using-intellisense.md) je kódování podpory, který zobrazí seznam odpovídajících metod, mimo jiné.) V této části jsme vám okomentujte nějaký kód.

![Tlačítka panelu nástrojů editoru](media/tutorial-editor-toolbar.png)

1. Vložte následující kód do `MySub()` postup textu.

   ```vb
   ' _words is a string array that we'll sort alphabetically
   Dim _words = New String() {
   "the",
   "quick",
   "brown",
   "fox",
   "jumps"
   }

   Dim morewords = New String() {
   "over",
   "the",
   "lazy",
   "dog"
   }

   Dim query = From word In _words
               Order By word.Length
               Select word
   ```

1. Nepoužíváme `morewords` pole, ale může ho později použít tak nechceme zcela odstranit. Místo toho můžeme okomentujte tyto řádky. Vyberte definici celý `morewords` na pravou složenou složených závorek a klikněte na tlačítko **Odkomentujte vybrané řádky** tlačítko na panelu nástrojů. Pokud chcete použít klávesnici, stiskněte **Ctrl**+**K**, **Ctrl**+**C**.

   ![Okomentujte tlačítko](media/tutorial-comment-out.png)

   Znak komentář jazyka Visual Basic `'` se přidá na začátek okomentujte kód každém řádku.

## <a name="collapse-code-blocks"></a>Sbalit bloky kódu

Můžete sbalit oddíly kódu zaměřit jenom na ty části, které vás zajímají. Cvičení, umožňuje sbalit `_words` pole na jeden řádek kódu. Vyberte malé šedé pole se znaménkem minus uvnitř u okraje řádku, který říká `Dim _words = New String() {`. Nebo, pokud jste uživatel klávesnice, umístěte kurzor kdekoli v definici pole a stiskněte klávesu **Ctrl**+**M**, **Ctrl**+**M** .

![Sbalování tlačítko Sbalit](media/tutorial-collapse.png)

Sbalí blok kódu pouze na první řádek, následované třemi tečkami (`...`). Rozbalte blok kódu znovu, klikněte na stejnou šedé pole, které teď má znaménko plus nebo stisknutím klávesy **Ctrl**+**M**, **Ctrl**+**M**  znovu. Tato funkce se nazývá [Osnova](../../ide/outlining.md) a je zvláště užitečné, když jste sbalení dlouhé metody nebo celé třídy.

## <a name="view-symbol-definitions"></a>Definice zobrazení symbolů

Editor sady Visual Studio usnadňuje Zkontrolujte definici typu, metody atd. Jedním ze způsobů, je přejít na soubor, který obsahuje definici, například výběrem **přejít k definici** kdekoli je odkazováno na symbol. Ještě rychlejší tak, aby váš výběr čárka nepohybuje mimo soubor pracujete v je použití [definice operace Peek](../../ide/go-to-and-peek-definition.md#peek-definition). Umožňuje zobrazení náhledu definice `String` typu.

1. Klikněte pravým tlačítkem na slovo `String` a zvolte **definice operace Peek** z nabídky obsahu. Také můžete stisknout klávesu **Alt**+**F12**.

   Se zobrazí automaticky otevírané okno s definicí `String` třídy. V automaticky otevíraném okně, nebo dokonce náhled definice jiného typu než peeked kódu můžete posouvat.

   ![Okno definice operace Peek](media/tutorial-peek-definition.png)

1. Zavřete okno Definice nahlédnout do malé pole "x" v pravé horní části v automaticky otevíraném okně výběrem.

## <a name="use-intellisense-to-complete-words"></a>K dokončení slova použít technologie IntelliSense

[Technologie IntelliSense](../../ide/using-intellisense.md) je neocenitelný při řízení zdrojů, když jste psaní kódu. Může zobrazit informace o Dostupní členové typu nebo parametr podrobnosti pro jiné přetížení metody. K dokončení slova Jakmile zadáte dostatečný počet znaků k rozlišení ho můžete také použít technologie IntelliSense. Přidáme řádek kódu vytiskne řazené řetězce v okně konzoly, což je standardní místo pro výstup z programu přejděte.

1. Níže `query` proměnné, začněte psát následující kód:

   ```vb
   For Each str In qu
   ```

   Zobrazí technologie IntelliSense zobrazí **rychlé informace** o `query` symbol.

   ![Doplňování technologie IntelliSense aplikace word v sadě Visual Studio](media/tutorial-intellisense-completion-list.png)

1. Chcete-li vložit zbytek slova `query` pomocí funkce doplňování technologie IntelliSense pro Wordu, stiskněte klávesu **kartu**.

1. Dokončete mimo blok kódu, aby vypadala jako následující kód.

   ```vb
   For Each str In query
       Console.WriteLine(str)
   Next
   ```

## <a name="refactor-a-name"></a>Refaktorovat název

Nikdo poprvé získá přímo a je jednou z věcí, které budete muset změnit název proměnné nebo metody. Si můžete vyzkoušet Visual Studio [Refaktorujte](../../ide/refactoring-in-visual-studio.md) funkce přejmenovat `_words` proměnnou `words`.

1. Umístěte ukazatel myši nad definici `_words` proměnné a zvolte **přejmenovat** z nabídky klikněte pravým tlačítkem nebo kontext.

   Automaticky otevírané okno **přejmenovat** dialogové okno se zobrazí v horní části přímo z editoru.

1. S proměnnou `_words` stále vybraná, zadejte požadovaný název **slova**. Všimněte si, že odkaz na `words` v dotazu je také automaticky přejmenovány. Než stisknete klávesu **Enter** nebo klikněte na tlačítko **použít**, vyberte **zahrnutí komentářů** zaškrtávací políčko ve **přejmenovat** v místním okně.

   ![přejmenování dialogového okna](media/tutorial-rename.png)

1. Stisknutím klávesy **Enter** nebo klikněte na tlačítko **použít**.

   Oba výskyty `words` jsou přejmenovány a také odkaz na `words` v komentáři kódu.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Seznamte se s projekty a řešení](tutorial-projects-solutions.md)

## <a name="see-also"></a>Viz také:

- [Fragmenty kódu](../../ide/code-snippets.md)
- [Vyhledání kódu](../../ide/navigating-code.md)
- [Sbalení](../../ide/outlining.md)
- [Přejít k definici a Náhled definice](../../ide/go-to-and-peek-definition.md)
- [Refactoring](../../ide/refactoring-in-visual-studio.md)
- [Používání technologie IntelliSense](../../ide/using-intellisense.md)