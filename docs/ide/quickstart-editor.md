---
title: "Úvod k úpravám v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: CSharp
ms.openlocfilehash: b74acd0b7711f7b11965bdde6fd2e152ee340c85
ms.sourcegitcommit: 1aa9282b1f0bc2795df3264cbd1e331cc44c23f3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/08/2017
---
# <a name="quickstart-coding-in-the-editor"></a>Rychlý úvod: kódování v editoru

V této 10 minut Úvod do editoru přidáme kód do souboru se podívat na některé způsoby, sada Visual Studio provádí zápis, navigace a pochopení kódu jednodušší.

## <a name="create-a-new-code-file"></a>Vytvoření nového souboru kódu

Spuštění vytvoření nového souboru a přidáním nějaký kód do ní. Všimněte si, že jsme nemají k vytvoření projektu k získání některé z výhod, které nabízí editor.

1. Otevřete Visual Studio a z **soubor** nabídky v řádku nabídek zvolte **nový** > **souboru...** .

1. V **nový soubor** dialogovém **Obecné** kategorie, zvolte **Visual C# – třída**a potom zvolte **otevřete**.

   Nový soubor se otevře v editoru s kostru třídy jazyka C#.

## <a name="using-code-snippets"></a>Používání fragmentů kódu

Visual Studio poskytuje fragmenty užitečné kódu, které vám pomůže rychle a snadno vygenerovat běžně používá bloky kódu. [Fragmenty kódu](../ide/code-snippets.md) jsou k dispozici pro různé programovací jazyky, včetně C#, Visual Basic a C++. Přidejme jazyka C# `void Main` fragment kódu do našich souboru.

1. Umístěte kurzor pod složená závorka `Class1` konstruktor a zadejte znaky `svm`.

   Zobrazí dialogové okno IntelliSense zobrazí s informacemi o `svm` fragment kódu.

   ![Fragment kódu technologie IntelliSense](media/quickstart-intellisense-snippet.png)

1. Stiskněte klávesu **kartě** dvakrát, chcete-li vložit fragment kódu.

   Zobrazí `static void Main()` podpis metody se přidají do souboru. `Main()` Metoda je vstupní bod pro aplikací v C#.

Fragmenty kódu k dispozici lišit pro různé jazyky. Můžete si prohlédnout fragmenty kódu k dispozici pro programovací jazyk výběrem **upravit**, **IntelliSense**, **Vložit fragment...** a pak vyberete složku svůj jazyk. Pro jazyk C# seznamu vypadat třeba takto:

![Seznam fragmentu kódu C#](media/quickstart-code-snippet-list.png)

Seznam obsahuje fragmenty pro vytvoření třídy, konstruktor, `Console.WriteLine()`, `for` smyčky, `if` a `switch` příkazy a další.

## <a name="commenting-out-code"></a>Při psaní komentářů se kódu

Panel nástrojů poskytuje řadu tlačítek pro zvýšení produktivity, jako je kód. Můžete například přepnout režim dokončení IntelliSense, zvýšit nebo snížit odsazení, nastavte záložku nebo komentář kódu. V této části jsme budete komentář se některé kód, který jsme nechcete zkompilovat.

![Editor panelu nástrojů](media/quickstart-editor-toolbar.png)

1. Vložte následující kód do `Main()` metoda textu.

    ```csharp
    // _words is a string array that we'll sort alphabetically
    string[] _words = {
        "the",
        "quick",
        "brown",
        "fox",
        "jumps"
    }

    string[] morewords = {
        "over",
        "the",
        "lazy",
        "dog"
    };

    IEnumerable<string> query = from word in _words
                                orderby word.Length
                                select word;
    ```

1. Nejsou používáme `morewords` proměnné, ale nemůžeme smíte ji použít později, jsme nechcete, aby ho odstranit. Místo toho můžeme komentář tyto řádky. Vyberte celou definici `morewords` k zavření středníkem a potom zvolte **komentář vybrané řádky** na panelu nástrojů nebo stiskněte tlačítko **Ctrl** + **Tisíc**, **Ctrl**+**C**.

   ![Komentář tlačítko](media/quickstart-comment-out.png)

   Komentář znaků jazyka C# `//` jsou přidány na začátek komentář kód každém řádku.

## <a name="collapsing-code-blocks"></a>Sbalení bloky kódu

Neradi najdete v části prázdný konstruktor pro `Class1` který byl vygenerován, takže k zpřehlednit naše zobrazení kódu, umožňuje sbalit. Zvolte pole malé šedé se minus uvnitř ho na okraji první řádek konstruktoru. Nebo, pokud se uživatel klávesnice, umístěte kurzor kdekoli v konstruktoru kód a stiskněte klávesu **Ctrl**+**M**, **Ctrl**+**M** .

![Osnova tlačítko Sbalit](media/quickstart-collapse.png)

Blok kódu sbalí jenom na první řádek, za nímž následuje třemi tečkami (`...`). Chcete-li rozšířit blok kódu znovu, klikněte na tlačítko stejné šedé pole, která teď má znaménko plus v, nebo klikněte na tlačítko **Ctrl**+**M**, **Ctrl**+**M**  znovu. Tato funkce je volána [osnovy](../ide/outlining.md) a je obzvláště užitečné, když jste sbalení dlouho metody nebo celý třídy.

## <a name="viewing-symbol-definitions"></a>Definice zobrazení symbolů

Editoru Visual Studio snadno Zkontrolujte definici typu, metoda atd. Jedním ze způsobů je přejděte na soubor, který obsahuje definici, třeba tak, že zvolíte **přechod na definici** kdekoli symbol odkazuje. I rychlejší způsobem, který nepodporuje přesun zaměření pro vaše mimo soubor pracujete v je použití [funkce Náhled definice](../ide/go-to-and-peek-definition.md#peek-definition). Umožňuje prohlížet definice `string`.

1. Klikněte pravým tlačítkem na výskyt žádné `string` a zvolte **funkce Náhled definice** z kontextové nabídky&mdash;nebo stiskněte klávesu **Alt**+**F12**.

   Automaticky otevírané okno se zobrazí s definicí `String` třídy. Můžete posouvat automaticky otevírané okno, nebo i funkce Náhled na definici jiného typu z peeked kódu.

   ![Funkce Náhled definice – okno](media/quickstart-peek-definition.png)

1. Zavřete okno provedla definice výběrem pole malé s "x" v pravé horní překryvné okno.

## <a name="using-intellisense-to-complete-words"></a>Používání atributu IntelliSense pro dokončení slova

[IntelliSense](../ide/using-intellisense.md) je prostředek neocenitelnou pomocí při jste kódování. Může zobrazit, informace o Dostupní členové typ nebo parametr podrobnosti o různých přetížení metody. Můžete taky IntelliSense dokončit slovo po zadání dostatečný počet znaků k rozlišení ho. Přidejme řádku kódu vytiskněte seřazené řetězce do okna konzoly.

1. Níže `query` proměnné, začněte psát následující kód:

   ```csharp
   foreach (string str in qu
   ```

   Zobrazí technologie IntelliSense ukazují **rychlé informace** o `query` symbol.

   ![Kompletní aplikace word IntelliSense](media/quickstart-intellisense-completion-list.png)

1. Chcete-li vložit zbývající aplikace word `query` pomocí funkce "Dokončení slovo" na IntelliSense, stiskněte klávesu **kartě**.

1. Dokončete vypnout blok kódu, aby vypadala jako následující kód. Můžete dokonce praxi, používání fragmentů kódu znovu tak, že zadáte `cw` a stisknutím klávesy **kartě** dvakrát ke generování `Console.WriteLine` kódu.

   ```csharp
   foreach (string str in query)
   {
      Console.WriteLine(str);
   }
   ```

## <a name="refactoring-a-name"></a>Refaktoring název

Nikdo poprvé získá kód doprava a jednu z akcí, které chcete změnit je název proměnné nebo metoda. Už si můžete vyzkoušet Visual Studio [refaktoring](../ide/refactoring-code-generation-quick-actions.md#refactoring) funkce přejmenovat `_words` proměnnou `words`.

1. Umístěte ukazatel myši nad definice `words` proměnnou a zvolte **přejmenovat...**  z klikněte pravým tlačítkem nebo místní nabídky nebo klikněte na tlačítko **Ctrl**+**R**, **Ctrl**+**R**.

   Automaticky otevírané okno **přejmenovat** dialogové okno se zobrazí v horní části napravo od editoru.

1. Zadejte požadovaný název `words`. Všimněte si, že odkaz na `words` v dotazu je také automaticky přejmenovat. Před stisknutím klávesy **Enter**, vyberte **zahrnout komentáře** zaškrtnout políčko **přejmenovat** automaticky otevírané okno pole.

   ![přejmenování dialogového okna](media/quickstart-rename.png)

1. Stiskněte klávesu **zadejte**.

   Obě výskyty `words` byla přejmenována, a také odkaz na `words` v komentář kódu.

## <a name="next-steps"></a>Další kroky

Po dokončení tento rychlý start pro editoru Visual Studio! Dále můžete vyzkoušet některé z dalších quickstarts pro Visual Studio IDE, vyhledejte v další způsoby [navigace v kódu](../ide/navigating-code.md), nebo najdete pod odkazy na další informace o funkcích jsme se podívali na. V opačném případě radostí kódování!

## <a name="see-also"></a>Viz také

[Rychlý úvod: první pohled na Visual Studio IDE](../ide/quickstart-ide-orientation.md)  
[Rychlý úvod: přizpůsobení Visual Studio IDE a Editor](../ide/quickstart-personalize-the-ide.md)  
[Fragmenty kódu](../ide/code-snippets.md)  
[Sbalení](../ide/outlining.md)  
[Přejít k definici a Náhled definice](../ide/go-to-and-peek-definition.md)  
[Refactoring](../ide/refactoring-code-generation-quick-actions.md#refactoring)  
[Používání atributu IntelliSense](../ide/using-intellisense.md)  