---
title: "Začínáme s R v sadě Visual Studio | Microsoft Docs"
description: "Návod k používání R v sadě Visual Studio, včetně vytváření projektu, interaktivních okna kódu úprav a ladění."
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: cf8df86322e10054dee5dbcee95839506f690306
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="getting-started-with-r-tools-for-visual-studio"></a>Začínáme s R Tools pro sadu Visual Studio

Až budete mít R nástrojů pro Visual Studio (RTVS) nainstalován (viz [instalace](installing-r-tools-for-visual-studio.md)), můžete rychle získat chuť prostředí, které poskytují tyto nástroje. 

## <a name="create-an-r-project"></a>Vytvoření projektu R

1. Spuštění sady Visual Studio.
1. Zvolte **soubor > Nový > projekt...** (Ctrl+Shift+N)
1. Vyberte z v části "R projekt" **šablony > R**, název a umístění poskytnout projekt a vyberte **OK**:

   ![Dialogové okno Nový projekt pro R v sadě Visual Studio (RTVS v VS2017)](media/getting-started-01-new-project.png)

1. Po vytvoření projektu, zobrazí se následující windows:

    - Na pravé straně je Průzkumníka Visual Studio řešení, kde uvidíte projektu uvnitř obsahujícího *řešení*. (Řešení může obsahovat libovolný počet projekty různých typů; viz [projekty](r-projects-in-visual-studio.md) podrobnosti.
    - V levé horní části je nový soubor R (`script.R`) kde můžete upravit zdrojového kódu se všemi sady Visual Studio je úpravy funkce.
    - V dolní vlevo **R interaktivní** okno, ve kterém můžete interaktivně vývoj a testování kódu.

> [!Note]
> Můžete použít **R interaktivní** okno bez nutnosti všechny projekty otevřené a to i když je načten jiný typ projektu. Právě vyberte **R nástroje > Windows > R interaktivní** kdykoli.

## <a name="explore-the-interactive-window-and-intellisense"></a>Prozkoumat interaktivní okno a IntelliSense

1. Test, který interaktivních okna pracuje tak, že zadáte v `3 + 4` a pak zadejte zobrazíte výsledek:

    ![R interaktivních okna ve Visual Studio 2017 (VS2017)](media/getting-started-02-interactive1.png)

1. Zadejte něco obtížnější, `ds <- c(1.5, 6.7, 8.9) * 1:12`a potom zadejte `ds` zobrazíte výsledek:

    ![Další příklad interaktivní R v sadě Visual Studio](media/getting-started-03-interactive2.png)

1. Zadejte `mean(ds)` , ale Všimněte si, že jakmile zadáte `m` nebo `me`, Visual Studio IntelliSense poskytuje možnosti automatického dokončování. Po dokončení, které chcete je vybrali v seznamu, stiskněte klávesu Tab, chcete-li vložit. Výběr pomocí klávesy se šipkami nebo myš, můžete změnit.

    ![Zobrazování kódu technologie IntelliSense](media/getting-started-04-intellisense1.png)

1. Po dokončení `mean`, zadejte levé závorky `(` a poznamenejte si, jak technologie IntelliSense vám vložené nápovědy pro funkce:

    ![Zobrazení nápovědy pro funkci IntelliSense](media/getting-started-05-intellisense2.png)

1. Dokončení řádku `mean(ds)` a stiskněte klávesu Enter, chcete-li zobrazit výsledek (`[1] 39.51667`).

1. Interaktivních okna je integrována nápovědy, takže zadávání `?mean` zobrazí nápovědu pro tuto funkci v **pomoci R** oken v sadě Visual Studio. Podrobnosti najdete v tématu [Nápověda v R nástrojů pro Visual Studio](getting-started-help.md).

    ![R pomůže oken v sadě Visual Studio](media/getting-started-06-help.png)

1. Některé příkazy, jako například `plot(1:100)`, otevřete nové okno v sadě Visual Studio, když nelze zobrazit výstup přímo v okně interaktivní:

    ![Zobrazení vykreslení v sadě Visual Studio](media/getting-started-07-plot-window.png)

Interaktivních okna také umožňuje zkontrolovat historii, načtěte a uložit pracovní prostory, připojení k ladicí program a interakci s soubory zdrojového kódu místo pomocí kopírování vkládání. V tématu [práce s interaktivních okna R](interactive-repl-for-r-in-visual-studio.md) podrobnosti.

## <a name="experience-code-editing-features"></a>Funkce pro úpravu kódu prostředí

Práce s interaktivních okna stručně ukazuje základní úpravy funkce jako je technologie IntelliSense, které lze použít také v editoru kódu. Pokud zadáte stejný kód jako před, zobrazí stejné automatické doplňování a výzvy IntelliSense, ale není výstup.

Psaní kódu v `.R` souboru umožňuje zobrazit všech vašich kódech najednou a je jednodušší a provést změny malé rychle zjistit výsledek spuštěním kódu v okně interaktivní. Může mít libovolný počet souborů tak, jak chcete v projektu. Pokud je kód v souboru, můžete také spustit ho krok za krokem v ladicím programu (popsané dále v tomto článku). Tyto funkce jsou užitečné, když jste vývoj výpočetní algoritmy a psaní kódu k manipulaci s jeden nebo více datových sad, zejména v případě, že chcete prověřit všechna mezilehlých výsledků.

Jako příklad následující kroky vytvoření trochu kódu a prozkoumejte [centrální věta Limit](https://en.wikipedia.org/wiki/Central_limit_theorem) (Wikipedia). (V tomto příkladu je přizpůsobené z *R kuchařka* podle Paul Teetor.)

1. V `script.R` editor, zadejte následující kód:

    ```R
    mu <- 50
    stddev <- 1
    N <- 10000
    pop <- rnorm(N, mean = mu, sd = stddev)
    plot(density(pop), main = "Population Density", xlab = "X", ylab = "")
    ```

1. Rychle zobrazit výsledky, vyberte všechny kód (Ctrl + A) a potom stiskněte klávesu Ctrl + Enter nebo klikněte pravým tlačítkem a vyberte **provést v interaktivní**. Na vybraný úsek kódu je spusťte v okně interaktivní jako, pokud jste zadali přímo, zobrazuje výsledek v okně výkresu:

    ![Zobrazení vykreslení v sadě Visual Studio](media/getting-started-08-plot1.png)

1. Pro jeden řádek stačí stisknout klávesu Ctrl + Enter kdykoli spustit tento řádek v okně interaktivní.

> [!Tip]
> Další informace vzor úpravou a kombinace kláves Ctrl + Enter (nebo Vybrat vše, co se Ctrl + a stisknutím klávesy Ctrl + Enter) rychlé spuštění kódu. Díky tomu je mnohem efektivnější než pomocí myši pro stejné operace.
> 
> Kromě toho můžete můžete přetahování okno výkresu mimo rámec Visual Studio a umístěte ho jinak můžete kdykoli na zobrazení. Pak můžete nastavit velikost okna výkresu do dimenzí, které chcete a ukládat ho do obrazu nebo soubor PDF.

1. Přidejte další pár řádků kódu se má vložit druhého grafu:

    ```R
    n <- 30
    samp.means <- rnorm(N, mean = mu, sd = stddev / sqrt(n))
    lines(density(samp.means))
    ```

1. Stiskněte kombinaci kláves Ctrl + A a Ctrl + Enter znovu spustit kód, který vytvořil následující výsledek:

    ![Aktualizované duální vykreslení v sadě Visual Studio](media/getting-started-09-plot2.png)

1. Problém je, že první výkresu Určuje svislé měřítko, druhý vykreslení (s `lines`) nevejde. Chcete-li tento problém, je potřeba nastavit `ylim` parametr na `plot` volání, ale provést, aby byly správně, je potřeba přidat kód pro výpočet maximální hodnoty svislé. Díky této řádek po řádku v okně interaktivní je nepohodlná, protože potřebujeme ke změně uspořádání kód, který použije `samp.means` před voláním `plot`. V souboru kódu ale snadno bychom mohli příslušné úpravy:

    ```R
    mu <- 50
    stddev <- 1
    N <- 10000
    pop <- rnorm(N, mean = mu, sd = stddev)

    n <- 30
    samp.means <- rnorm(N, mean = mu, sd = stddev / sqrt(n))
    max.samp.means <- max(density(samp.means)$y)

    plot(density(pop), main = "Population Density",
        ylim = c(0, max.samp.means),
        xlab = "X", ylab = "")
    lines(density(samp.means))
    ```

1. CTRL + A Ctrl + Enter znovu zobrazte a výsledek:

    ![Aktualizované duální vykreslení v sadě Visual Studio, škálovat správně](media/getting-started-10-plot3.png)

Je informace, které můžete provést v editoru. Podrobnosti najdete v tématu [úpravy kódu](editing-r-code-in-visual-studio.md), [IntelliSense](r-intellisense.md), a [výstřižky kódu](code-snippets-for-r.md).

## <a name="debugging-your-code"></a>Ladění kódu

Jeden z klíčů síly sady Visual Studio je její ladění uživatelského rozhraní. RTVS staví na této silné foundation a přidá inovativní uživatelského rozhraní, jako [proměnné Průzkumníka a Data tabulky prohlížeč](variable-explorer.md). Zde právě Podívejme se první na ladění.

1. Pokud chcete začít, resetovat aktuální pracovní prostor Vymazat všechno, co provedete krok, pokud pomocí **R nástroje > relace > resetovat** příkazu nabídky. Ve výchozím nastavení vše, co můžete udělat v okně interaktivní nabíhají s aktuální relací, který pak používá také ladicího programu. Resetováním relace je zajistit, že relaci ladění začíná žádná existující data. **Resetovat** příkazu, ale neovlivní vaše `script.R` zdrojového souboru, vzhledem k tomu, který má spravovat a uložit mimo pracovní prostor.

1. S `script.R` soubor vytvoří v předchozí části, nastavte zarážky v řádku, který začíná `pop <-` umístění pomocí kurzoru na tomto řádku a potom stisknutím klávesy F9 nebo výběrem **ladění > Přepnout zarážku** nabídky příkaz. Případně jednoduše klikněte v levém okraji (nebo oddělovací mezery) pro tento řádek, ve kterém se zobrazí červený zarážek tečky:

    ![Nastavení boru přerušení v editoru](media/getting-started-11-debug1.png)

1. Spuštění ladicího programu s kódem v `script.R` výběrem buď **zdrojový soubor spouštěcí** na panelu nástrojů zobrazí tlačítko pro výběr **ladění > zdrojový soubor spouštěcí** položky nabídky nebo stisknete F5. Visual Studio zadá režim ladění a spuštění kódu. Zastaví, ale na řádku, kde je nastavena zarážka:

    ![Probíhá zastavení na zarážek v ladicím programu sady Visual Studio](media/getting-started-12-debug2.png)

1. Během ladění, Visual Studio poskytuje schopnost krokovat kód řádek po řádku. Můžete také krok do funkce, krok přes, nebo z nich tak, aby kontext volání. Tyto možnosti, společně s ostatními, můžete najít na **ladění** nabídka, v místní nabídce klikněte pravým tlačítkem v editoru a ladění nástrojů:

    ![Ladění panelu nástrojů v sadě Visual Studio](media/getting-started-13-debug3.png)

1. Při zastavení na zarážce, můžete zkontrolovat hodnoty proměnných. Vyhledejte **automobily** oken v sadě Visual Studio a vyberte kartu podél dolního s názvem **místní hodnoty –**. **Místní hodnoty** v okně se zobrazí místní proměnné k aktuálnímu bodu v programu. Při zastavení na zarážce nastavit dříve můžete vidět, že `pop` proměnná ještě není definován. Teď použít **ladění > Krokovat s přeskočením** příkazu (F10) a zobrazit tak hodnotu pro `pop` zobrazí:

    ![Místní hodnoty – okno v sadě Visual Studio](media/getting-started-14-debug4.png)

1. K prozkoumání proměnné v různých oborech, včetně globální obor a balíček obory, použijte [proměnné Explorer](variable-explorer.md). Proměnné Explorer nabízí také umožňuje přepnout do tabulkového zobrazení s řazení sloupců a exportovat data do souboru CSV.

    ![Rozšířené zobrazení Průzkumníka proměnné](media/variable-explorer-expanded-results.png)

1. Můžete pokračovat v procházení programu řádek po řádku, nebo vybrat možnost **pokračovat** (F5) ke spuštění dokončení (nebo na další zarážku).

Přechod hlubší naleznete v tématu [ladění](debugging-r-in-visual-studio.md) a [proměnné Explorer](variable-explorer.md).

## <a name="next-steps"></a>Další kroky

V tomto návodu jste se naučili základy R projektů, použití interaktivních okna, úprav a ladění v sadě Visual Studio code. Chcete-li pokračovat, prohlížení další funkce, najdete na následující články a také články, které jsou uvedené v tabulce obsahu:

- [Ukázkové projekty](getting-started-samples.md)
- [Úpravy kódu](editing-r-code-in-visual-studio.md)
- [Ladění](debugging-r-in-visual-studio.md)
- [Pracovní prostory](r-workspaces-in-visual-studio.md)
- [Vizualizace dat](visualizing-data-with-r-in-visual-studio.md)
