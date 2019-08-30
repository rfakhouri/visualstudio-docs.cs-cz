---
title: Úvod do úprav pro vývojáře Visual Basic
description: Tento 10 minutový Úvod do editoru kódu v aplikaci Visual Studio ukazuje některé způsoby, jak Visual Studio usnadňuje psaní, navigaci a porozumění Visual Basic kódu.
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
ms.openlocfilehash: 5ebbe6ac8ef8e6a6de99159fa8dd5169a9dcac06
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70180393"
---
# <a name="learn-to-use-the-code-editor"></a>Zjistěte, jak pomocí editoru kódu

V tomto úvodu během 10 minut do editoru kódu v sadě Visual Studio přidáme kód pro soubor, který chcete podívat na některé ze způsobů, že sada Visual Studio provádí zápis, procházení a porozumění kódu jednodušší.

::: moniker range="vs-2017"

> [!TIP]
> Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

> [!TIP]
> Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads) stránku a nainstalovat zdarma.

::: moniker-end

V tomto článku se předpokládá, že už jste obeznámeni s Visual Basic. Pokud nejste, doporučujeme se podívat na kurz, například [Začínáme s Visual Basic v aplikaci Visual Studio](../../get-started/visual-basic/tutorial-console.md) jako první.

> [!TIP]
> Pokud chcete postupovat podle tohoto článku, ujistěte se, že máte vybraná nastavení Visual Basic pro Visual Studio. Informace o výběru nastavení pro integrované vývojové prostředí (IDE) najdete v tématu [Výběr nastavení prostředí](visual-studio-ide.md#select-environment-settings).

## <a name="create-a-new-code-file"></a>Vytvořte nový soubor kódu

Začněte tím, že vytváří se nový soubor a přidat nějaký kód do něj.

::: moniker range="vs-2017"

1. Otevřít Visual Studio.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřít Visual Studio. Stisknutím klávesy **ESC** nebo kliknutím na **pokračovat bez kódu** v okně Start otevřete vývojové prostředí.

::: moniker-end

2. V nabídce **soubor** na řádku nabídek vyberte možnost **nový soubor**.

3. V dialogovém okně **nový soubor** v kategorii **obecné** zvolte položku **Visual Basic třída**a pak zvolte možnost **otevřít**.

   V editoru se otevře nový soubor s kostrou Visual Basic třídy. (Už si můžete všimnout, že nemusíte vytvářet úplný projekt sady Visual Studio, abyste získali některé výhody, které Editor kódu nabízí, jako je například zvýrazňování syntaxe. Vše, co potřebujete, je soubor kódu!)

   ![Soubor kódu Visual Basic v aplikaci Visual Studio](media/tutorial-editor.png)

## <a name="use-code-snippets"></a>Používání fragmentů kódu

Visual Studio poskytuje užitečné *fragmenty kódu* , že vám pomůže rychle a snadno generovat běžně používá bloky kódu. [Fragmenty kódu](../../ide/code-snippets.md) jsou k dispozici pro různé programovací jazyky, C#včetně Visual Basic C++, a. Pojďme přidat **dílčí** fragment Visual Basic do našeho souboru.

1. Umístěte kurzor nad řádek, který říká `End Class`, a zadejte **Sub**.

   Zobrazí se automaticky otevírané okno s informacemi o `Sub` klíčovém slově a způsobu vložení **dílčího** fragmentu kódu.

   ![Technologie IntelliSense pro fragment kódu v sadě Visual Studio](media/tutorial-intellisense-snippet.png)

1. Stisknutím klávesy **kartu** dvakrát pro vložení fragmentu kódu.

   Osnova pro proceduru `MySub()` sub je přidána do souboru.

Fragmenty kódu k dispozici lišit pro různé programovací jazyky. Můžete se podívat na dostupné fragmenty kódu pro Visual Basic tím, že **vyberete Upravit** > **IntelliSense** > **Vložit fragment kódu** (nebo stisknout **CTRL**+**K**, **CTRL** + **X**). Pro Visual Basic jsou fragmenty kódu k dispozici pro následující kategorie:

![Visual Basic seznam fragmentů kódu](media/tutorial-code-snippet-list.png)

Existují fragmenty pro zjištění, zda soubor existuje v počítači, zápis do textového souboru, čtení hodnoty registru, provádění dotazu SQL a vytvoření příkazu [pro každý... Další příkaz](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)a mnoho dalších.

## <a name="comment-out-code"></a>Okomentujte kód

Panel nástrojů, který je řádek tlačítek v panelu nabídek v sadě Visual Studio může pomoct zvýší vaši produktivitu při kódování. Můžete například přepnout režim dokončování IntelliSense, zvětšit nebo zmenšit odsazení řádku nebo komentovat kód, který nechcete kompilovat. ([IntelliSense](../../ide/using-intellisense.md) je podpora kódování, která zobrazuje seznam metod porovnání, mimo jiné.) V této části jsme vám okomentujte nějaký kód.

![Tlačítka panelu nástrojů editoru](media/tutorial-editor-toolbar.png)

1. Do `MySub()` těla procedury vložte následující kód.

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

1. Nepoužíváme `morewords` pole, ale můžeme ho použít později, takže ho nechceme úplně odstranit. Místo toho můžeme okomentujte tyto řádky. Vyberte celou definici `morewords` pro pravou složenou závorku a pak zvolte tlačítko **Přidat komentář** k vybraným řádkům na panelu nástrojů. Pokud chcete použít klávesnici, stiskněte **Ctrl**+**K**, **Ctrl**+**C**.

   ![Okomentujte tlačítko](media/tutorial-comment-out.png)

   Znak `'` komentáře Visual Basic se přidá na začátek každého vybraného řádku, aby se přidal komentář ke kódu.

## <a name="collapse-code-blocks"></a>Sbalit bloky kódu

Můžete sbalit části kódu a soustředit se jenom na části, které vás zajímají. Chcete-li postupovat, sbalte `_words` pole na jeden řádek kódu. Vyberte malé šedé pole s znaménkem mínus uvnitř něj v okraji řádku, který říká `Dim _words = New String() {`. Nebo, pokud jste uživatel klávesnice, umístěte kurzor kamkoli do definice pole a stiskněte **kombinaci kláves CTRL**+**m**, **CTRL**+**m**.

![Sbalování tlačítko Sbalit](media/tutorial-collapse.png)

Sbalí blok kódu pouze na první řádek, následované třemi tečkami (`...`). Rozbalte blok kódu znovu, klikněte na stejnou šedé pole, které teď má znaménko plus nebo stisknutím klávesy **Ctrl**+**M**, **Ctrl**+**M**  znovu. Tato funkce se nazývá [Osnova](../../ide/outlining.md) a je zvláště užitečné, když jste sbalení dlouhé metody nebo celé třídy.

## <a name="view-symbol-definitions"></a>Definice zobrazení symbolů

Editor sady Visual Studio usnadňuje Zkontrolujte definici typu, metody atd. Jedním ze způsobů, je přejít na soubor, který obsahuje definici, například výběrem **přejít k definici** kdekoli je odkazováno na symbol. Ještě rychlejší tak, aby váš výběr čárka nepohybuje mimo soubor pracujete v je použití [definice operace Peek](../../ide/go-to-and-peek-definition.md#peek-definition). Umožňuje zobrazení náhledu definice `String` typu.

1. Klikněte pravým tlačítkem myši na `String` slovo a v nabídce obsah vyberte možnost **Náhled definice** . Také můžete stisknout klávesu **Alt**+**F12**.

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

1. Umístěte kurzor na definici `_words` proměnné a v místní nabídce klikněte pravým tlačítkem myši na možnost **Přejmenovat** .

   Automaticky otevírané okno **přejmenovat** dialogové okno se zobrazí v horní části přímo z editoru.

1. Když je proměnná `_words` stále vybraná, zadejte požadované názvy **slov**. Všimněte si, že odkaz na `words` v dotazu je také automaticky přejmenovány. Před stisknutím klávesy **ENTER** nebo kliknutím na možnost **použít**zaškrtněte políčko **zahrnout komentáře** v automaticky otevíraném okně pro **přejmenování** .

   ![přejmenování dialogového okna](media/tutorial-rename.png)

1. Stiskněte klávesu **ENTER** nebo klikněte na **použít**.

   Oba výskyty `words` jsou přejmenovány a také odkaz na `words` komentář kódu.

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