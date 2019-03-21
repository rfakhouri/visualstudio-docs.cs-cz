---
title: Prohlídka integrovaného vývojového prostředí sady Visual Studio
titleSuffix: ''
ms.date: 02/21/2019
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fe3b78562b9fa7b5632e1ce60788c918e065d3dc
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2019
ms.locfileid: "58325172"
---
# <a name="quickstart-first-look-at-the-visual-studio-ide"></a>Rychlý start: První seznámení s integrovaným vývojovým prostředím sady Visual Studio

V tomto úvodu 5 až 10 minut do integrovaného vývojového prostředí (IDE) sady Visual Studio provedeme si některé z okna, nabídek a další funkce uživatelského rozhraní.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

::: moniker range="vs-2017"

## <a name="start-page"></a>Úvodní stránka

První věc, kterou se zobrazí po spuštění sady Visual Studio je s největší pravděpodobností **úvodní stránka**. **Úvodní stránka** slouží jako "centra", které vám pomohou najít příkazy a potřebujete rychlejší soubory projektu. **Poslední** části zobrazí projekty a složky, které jste nedávno pracovali. V části **nový projekt**, můžete kliknout na odkaz zobrazíte **nový projekt** dialogové okno, nebo v části **otevřete**, můžete otevřít existující projekt kódu nebo složky. Na pravé straně je informační kanál nejnovější Novinky pro vývojáře.

![Úvodní stránka v sadě Visual Studio](media/start-page.png)

Pokud zavřete **úvodní stránka** a chcete ho znovu zobrazit, můžete znovu otevřít z **souboru** nabídky.

![Nabídka soubor v sadě Visual Studio](media/quickstart-IDE-file-menu-large.png)

::: moniker-end

::: moniker range=">=vs-2019"

## <a name="start-window"></a>Časový interval pro spuštění

První věc, který se zobrazí po spuštění sady Visual Studio je okno start. V okně start usnadňuje "kód" rychleji získat. Obsahuje možnosti, jak klonovat nebo podívejte se na kód, otevřete existující projekt nebo řešení, vytvořte nový projekt nebo stačí otevřít místní složku, která obsahuje některé soubory s kódem.

[![](media/vs-2019/start-window-labeled.png "V okně spuštění v aplikaci Visual Studio 2019")](media/vs-2019/start-window-labeled.png#lightbox)

Pokud je to Visual Studio používáte poprvé, bude váš seznam posledních projektů prázdný.

Pokud pracujete s typu než MSBuild na základě základů kódu, budete používat **otevřít místní složku** možnost otevření kódu v sadě Visual Studio. Další informace najdete v tématu [vývoj kódu v sadě Visual Studio bez projektů nebo řešení](develop-code-in-visual-studio-without-projects-or-solutions.md). V opačném případě můžete vytvořit nový projekt nebo klonování projektu z poskytovatele zdroj jako GitHub nebo Azure DevOps.

**Pokračovat bez kódu** možnost jednoduše otevře vývojové prostředí sady Visual Studio bez jakýchkoli konkrétních projektu nebo kód načtený. Můžete zvolit tuto možnost připojit [Live Share](/visualstudio/liveshare/) relace nebo se připojit k procesu pro ladění. Můžete také stisknout klávesu **Esc** zavřete okno start a otevření rozhraní IDE.

::: moniker-end

## <a name="create-a-project"></a>Vytvoření projektu

Pokračujte ve zkoumání funkcí sady Visual Studio, vytvoříme nový projekt.

::: moniker range="vs-2017"

1. Na **úvodní stránka**, do vyhledávacího pole v rámci **nový projekt**, zadejte v **konzoly** pro filtrování seznamu typů projektů na ty, které obsahují "console" v názvu.

   ![Hledat v šablonách projektů na úvodní stránce Visual Studio](media/start-page-search-templates.png)

   Visual Studio poskytuje různé druhy šablony projektů, které vám pomůžou začít pracovat rychle kódování. Zvolte možnost jazyka C# **Konzolová aplikace (.NET Framework)** šablony projektu. (Případně pokud jste v jazyce Visual Basic, C++, Javascript nebo jiné jazyk pro vývojáře, můžete vytvořit projekt v jednom z těchto jazyků. Uživatelské rozhraní, které jsme vám pomyslného je podobné pro všechny programovací jazyky.)

1. V **nový projekt** dialogové okno, které se zobrazí, přijměte výchozí název projektu a zvolte možnost **OK**.

::: moniker-end

::: moniker range=">=vs-2019"

1. V okně start zvolte **vytvořte nový projekt**.

   Otevře se okno, které říká **vytvořte nový projekt**. Toto okno se někdy označuje jako **nový projekt** dialogového okna a to je, kde můžete procházet a vyberte šablonu projektu. Také udržuje seznam naposledy použitých projektu šablony.

1. Do vyhledávacího pole v horní části, zadejte v **konzoly** pro filtrování seznamu typů projektů na ty, které obsahují "console" v názvu. Dále zpřesnit výsledky hledání podle výběru **C#** (nebo jiném jazyce podle vašeho výběru) z **jazyk** výběr.

   ![Dialogové okno nového projektu v aplikaci Visual Studio 2019](media/vs-2019/create-a-new-project.png)

1. Pokud jste vybrali C#, Visual Basic nebo F# jako svůj oblíbený jazyk, vyberte **Konzolová aplikace (.NET Framework)** šablony a klikněte na tlačítko **Další**. (Pokud jste vybrali jiný jazyk, stačí vyberte všechny šablony. Uživatelské rozhraní, které jsme vám pomyslného je podobné pro všechny programovací jazyky.)

1. Na **konfigurovat nový projekt** stránce, přijměte výchozí název projektu a umístění a klikněte na tlačítko **vytvořit**.

::: moniker-end

   Vytvoření projektu a soubor s názvem *Program.cs* se otevře v **Editor** okna. **Editor** zobrazuje obsah souborů a je, ve kterém budete provádět většinu práce psaní kódu v sadě Visual Studio.

   ![Editor v sadě Visual Studio](media/editor.png)

## <a name="solution-explorer"></a>Průzkumník řešení

**Průzkumník řešení**, což je obvykle na pravé straně sady Visual Studio, se dozvíte, grafické reprezentace hierarchie souborů a složek ve vašem projektu, řešení nebo složky s kódem. Můžete procházet hierarchii a přejděte k souboru v **Průzkumníka řešení**.

![Průzkumník řešení v sadě Visual Studio](media/quickstart-IDE-solution-explorer.png)

## <a name="menus"></a>Nabídky

Příkazy nabídek v horní části Visual Studio seskupí do kategorií. Například **projektu** nabídka obsahuje příkazy související s projektem, ve které pracujete. Na **nástroje** nabídky, si můžete přizpůsobit chování sady Visual Studio tak, že vyberete **možnosti**, nebo přidání funkcí k instalaci tak, že vyberete **stažení nástrojů a funkcí**.

::: moniker range="vs-2017"

![Panel nabídek v sadě Visual Studio 2017](media/quickstart-IDE-menu-bar.png)

::: moniker-end

::: moniker range=">=vs-2019"

![Panel nabídek v aplikaci Visual Studio 2019](media/vs-2019/menu-bar.png)

::: moniker-end

## <a name="error-list"></a>Seznam chyb

Otevřít **seznam chyb** okno výběrem **zobrazení** nabídky a potom **seznam chyb**.

**Seznam chyb** se dozvíte, chyby, varování a zprávy týkající se aktuální stav vašeho kódu. Pokud nejsou žádné chyby (například chybějící závorka nebo středník) v souboru nebo kdekoli ve vašem projektu, jsou zde uvedeny.

![Seznam chyb v sadě Visual Studio](media/quickstart-IDE-error-list.png)

## <a name="output-window"></a>Výstup – okno

**Výstup** okno zobrazuje výstup zprávy z sestavení vašeho projektu a váš poskytovatel správy zdrojových kódů.

Vytvořme projektu zobrazíte některé výstup sestavení. Z **sestavení** nabídce zvolte **sestavit řešení**. **Výstup** okno automaticky získá fokus a zobrazí zprávy úspěšné sestavení.

![Okno výstup v sadě Visual Studio](media/build-output-minimal.png)

## <a name="quick-launch"></a>Snadné spuštění

**Snadné spuštění** vyhledávacího pole je rychlý a snadný způsob, jak přejít na prakticky cokoli v sadě Visual Studio. Můžete zadat nějaký text související s co chcete udělat, a ho budete zobrazit seznam možností, které se vztahují na text. Představte si například, že chcete zvýšit úroveň podrobností výstupu sestavení zobrazíte další podrobnosti o tom, co přesně sestavení dělá. Zde je, jak vám může provést:

::: moniker range="vs-2017"

1. Vyhledejte **Snadné spuštění** vyhledávacího pole v pravém horním rohu integrovaného vývojového prostředí. (Nebo stisknout **Ctrl**+**Q** k němu přistupovat.)

2. Typ **podrobností** do **Snadné spuštění** vyhledávacího pole. V zobrazené výsledky, zvolte **projekty a řešení--> sestavení a spuštění** pod **možnosti** kategorie.

   ![Snadné spuštění vyhledávacího pole v sadě Visual Studio 2017](media/quickstart-IDE-quick-launch.png)

   **Možnosti** dialogové okno s **sestavíte a spustíte** stránka možností.

::: moniker-end

::: moniker range=">=vs-2019"

1. Vyhledejte **Snadné spuštění** vyhledávacího pole v horní části rozhraní IDE, stačí napravo od nabídky. (Nebo stisknout **Ctrl**+**Q** k němu přistupovat.)

2. Typ **podrobností** do **Snadné spuštění** vyhledávacího pole. V zobrazené výsledky, zvolte **podrobnost nástroje MSBuild změnu**.

   ![Snadné spuštění vyhledávacího pole v aplikaci Visual Studio 2019](media/vs-2019/quick-launch-verbosity.png)

   **Možnosti** dialogové okno s **sestavíte a spustíte** stránka možností.

::: moniker-end

3. V části **podrobnosti výstupu sestavení projektu nástroje MSBuild**, zvolte **normální**a potom klikněte na tlačítko **OK**.

4. Znovu sestavte projekt kliknutím pravým tlačítkem na **ConsoleApp1** projekt **Průzkumníka řešení** a zvolíte **znovu sestavit** v místní nabídce.

   Tentokrát **výstup** okně se zobrazí podrobnější protokolování z procesu sestavení, včetně souborů, které byly zkopírovány where.

   ![Výstup podrobné sestavení v sadě Visual Studio](media/build-output-verbose.png)

## <a name="send-feedback-menu"></a>Odeslat zpětnou vazbu nabídky

By se vyskytnou potíže při použití sady Visual Studio, nebo pokud máte návrhy na vylepšení produktu, můžete použít **odeslat zpětnou vazbu** nabídce v horní části okna nástroje Visual Studio vedle **rychlé Spuštění** pole.

::: moniker range="vs-2017"

![Odeslat nabídku názoru v sadě Visual Studio 2017](media/quickstart-IDE-send-feedback.png)

::: moniker-end

::: moniker range=">=vs-2019"

![Odeslat nabídku názoru v aplikaci Visual Studio 2019](media/vs-2019/send-feedback-menu.png)

::: moniker-end

## <a name="next-steps"></a>Další kroky

Jsme se zabývali jenom některé funkce sady Visual Studio k seznámit s uživatelským rozhraním. Chcete-li podrobněji:

> [!div class="nextstepaction"]
> [Další informace o editoru kódu](../get-started/tutorial-editor.md)

> [!div class="nextstepaction"]
> [Seznamte se s projekty a řešení](../get-started/tutorial-projects-solutions.md)

## <a name="see-also"></a>Viz také:

- [Přehled prostředí IDE sady Visual Studio](../get-started/visual-studio-ide.md)
- [Další funkce sady Visual Studio](../ide/advanced-feature-overview.md)
- [Změna barvy motivu a písma](../ide/quickstart-personalize-the-ide.md)
