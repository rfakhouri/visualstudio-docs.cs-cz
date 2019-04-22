---
title: Prohlídka integrovaného vývojového prostředí sady Visual Studio
titleSuffix: ''
ms.date: 02/05/2019
ms.topic: quickstart
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94fff3c08d9bf6be7467e98a08d107b65928bd60
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "58790664"
---
# <a name="first-look-at-the-visual-studio-ide"></a>První seznámení s integrovaným vývojovým prostředím sady Visual Studio

V tomto úvodu 5 až 10 minut do integrovaného vývojového prostředí (IDE) sady Visual Studio provedeme si některé z okna, nabídek a další funkce uživatelského rozhraní.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

::: moniker range=">=vs-2019"

## <a name="start-window"></a>Časový interval pro spuštění

První věc, který se zobrazí po spuštění sady Visual Studio je okno start. V okně start usnadňuje "kód" rychleji získat. Obsahuje možnosti, jak zavřít nebo podívejte se na kód, otevřete existující projekt nebo řešení, vytvořte nový projekt nebo stačí otevřít místní složku, která obsahuje některé soubory s kódem.

[![](media/vs-2019/start-window.png "V okně spuštění v aplikaci Visual Studio 2019")](media/vs-2019/start-window.png)

Pokud je to Visual Studio používáte poprvé, bude váš seznam posledních projektů prázdný.

Pokud pracujete s typu než MSBuild na základě základů kódu, budete používat **otevřít místní složku** možnost otevření kódu v sadě Visual Studio. Další informace najdete v tématu [vývoj kódu v sadě Visual Studio bez projektů nebo řešení](develop-javascript-code-without-solutions-projects.md). V opačném případě můžete vytvořit nový projekt nebo klonování projektu z poskytovatele zdroj jako GitHub nebo Azure DevOps.

**Pokračovat bez kódu** možnost jednoduše otevře vývojové prostředí sady Visual Studio bez jakýchkoli konkrétních projektu nebo kód načtený. Můžete zvolit tuto možnost připojit [Live Share](/visualstudio/liveshare/) relace nebo se připojit k procesu pro ladění. Můžete také stisknout klávesu **Esc** zavřete okno start a otevření rozhraní IDE.

::: moniker-end

::: moniker range="vs-2017"

## <a name="start-page"></a>Úvodní stránka

První věc, kterou se zobrazí po spuštění sady Visual Studio je s největší pravděpodobností **úvodní stránka**. **Úvodní stránka** slouží jako "centra", které vám pomohou najít příkazy a potřebujete rychlejší soubory projektu. **Poslední** části zobrazí projekty a složky, které jste nedávno pracovali. V části **nový projekt**, můžete kliknout na odkaz zobrazíte **nový projekt** dialogové okno, nebo v části **otevřete**, můžete otevřít existující projekt kódu nebo složky. Na pravé straně je informační kanál nejnovější Novinky pro vývojáře.

![Úvodní stránka v sadě Visual Studio](media/start-page.png)

Pokud zavřete **úvodní stránka** a chcete ho znovu zobrazit, můžete znovu otevřít z **souboru** nabídky.

![Nabídka soubor v sadě Visual Studio](media/quickstart-IDE-file-menu-large.png)

::: moniker-end

## <a name="create-a-project"></a>Vytvoření projektu

Pokračujte ve zkoumání funkcí sady Visual Studio, vytvoříme nový projekt.

::: moniker range=">=vs-2019"

1. V okně start vyberte **vytvořte nový projekt**a potom do vyhledávacího pole zadejte **javascript** pro filtrování seznamu typů projektů na ty, které obsahují "javascript" v jejich název nebo jazyk typu.

   Visual Studio poskytuje různé druhy šablony projektů, které vám pomůžou začít pracovat rychle kódování. (Případně, pokud jste vývojář, TypeScript, můžete vytvořit projekt v daném jazyce. Uživatelské rozhraní, které jsme vám pomyslného je podobné pro všechny programovací jazyky.)

   ![Hledat v šablonách projektů v okně spuštění sady Visual Studio](media/vs-2019/create-new-project.png)

1. Zvolte **prázdná webová aplikace Node.js** šablony projektu a klikněte na tlačítko **Další**.

1. V **konfigurovat nový projekt** dialogové okno, které se zobrazí, přijměte výchozí název projektu a zvolte možnost **vytvořit**.

::: moniker-end

::: moniker range="vs-2017"

1. Na **úvodní stránka**, do vyhledávacího pole v rámci **nový projekt**, zadejte v **javascript** pro filtrování seznamu typů projektů na ty, které obsahují "javascript" v názvu nebo typ jazyka.

   ![Hledat v šablonách projektů na úvodní stránce Visual Studio](media/start-page-search-templates.png)

   Visual Studio poskytuje různé druhy šablony projektů, které vám pomůžou začít pracovat rychle kódování. Zvolte **prázdná webová aplikace Node.js** šablony projektu. (Případně, pokud jste vývojář, TypeScript, můžete vytvořit projekt v daném jazyce. Uživatelské rozhraní, které jsme vám pomyslného je podobné pro všechny programovací jazyky.)

1. V **nový projekt** dialogové okno, které se zobrazí, přijměte výchozí název projektu a zvolte možnost **OK**.
::: moniker-end

   Vytvoření projektu a soubor s názvem *server.cs* se otevře v **Editor** okna. **Editor** zobrazuje obsah souborů a je, ve kterém budete provádět většinu práce psaní kódu v sadě Visual Studio.

   ![Editor v sadě Visual Studio](media/editor.png)

## <a name="solution-explorer"></a>Průzkumník řešení

**Průzkumník řešení**, což je obvykle na pravé straně sady Visual Studio, se dozvíte, grafické reprezentace hierarchie souborů a složek ve vašem projektu, řešení nebo složky s kódem. Můžete procházet hierarchii a přejděte k souboru v **Průzkumníka řešení**.

![Průzkumník řešení v sadě Visual Studio](media/quickstart-IDE-solution-explorer.png)

## <a name="menus"></a>Nabídky

Příkazy nabídek v horní části Visual Studio seskupí do kategorií. Například **projektu** nabídka obsahuje příkazy související s projektem, ve které pracujete. Na **nástroje** nabídky, si můžete přizpůsobit chování sady Visual Studio tak, že vyberete **možnosti**, nebo přidání funkcí k instalaci tak, že vyberete **stažení nástrojů a funkcí**.

![Panel nabídek v sadě Visual Studio](media/quickstart-IDE-menu-bar.png)

Otevřete **seznam chyb** okno výběrem **zobrazení** nabídky a potom **seznam chyb**.

## <a name="error-list"></a>Seznam chyb

**Seznam chyb** se dozvíte, chyby, varování a zprávy týkající se aktuální stav vašeho kódu. Pokud nejsou žádné chyby (například chybějící závorka nebo středník) v souboru nebo kdekoli ve vašem projektu, jsou zde uvedeny.

![Seznam chyb v sadě Visual Studio](media/quickstart-IDE-error-list.png)

## <a name="output-window"></a>Výstup – okno

**Výstup** okno zobrazuje výstup zprávy z sestavení vašeho projektu a váš poskytovatel správy zdrojových kódů.

Vytvořme projektu zobrazíte některé výstup sestavení. Z **sestavení** nabídce zvolte **sestavit řešení**. **Výstup** okno automaticky získá fokus a zobrazí zprávy úspěšné sestavení.

![Okno výstup v sadě Visual Studio](media/build-output-minimal.png)

## <a name="search-box"></a>Vyhledávací pole

Do vyhledávacího pole je rychlý a snadný způsob, jak to je mnohem nic v sadě Visual Studio. Můžete zadat nějaký text související s co chcete udělat, a ho budete zobrazit seznam možností, které se vztahují na text. Představte si například, že chcete zvýšit úroveň podrobností výstupu sestavení zobrazíte další podrobnosti o tom, co přesně sestavení dělá. Zde je, jak vám může provést:

1. Typ **podrobností** do vyhledávacího pole. V zobrazené výsledky, zvolte **projekty a řešení--> sestavení a spuštění** pod **možnosti** kategorie.

   ![Vyhledávací pole v sadě Visual Studio](media/quickstart-IDE-quick-launch.png)

   **Možnosti** dialogové okno s **sestavíte a spustíte** stránka možností.

1. V části **podrobnosti výstupu sestavení projektu nástroje MSBuild**, zvolte **normální**a potom klikněte na tlačítko **OK**.

1. Znovu sestavte projekt kliknutím pravým tlačítkem na **NodejsWebApp1** projekt **Průzkumníka řešení** a zvolíte **znovu sestavit** v místní nabídce.

   Tentokrát **výstup** okně se zobrazí podrobnější protokolování z procesu sestavení, včetně souborů, které byly zkopírovány where.

   ![Výstup podrobné sestavení v sadě Visual Studio](media/build-output-verbose.png)

## <a name="send-feedback-menu"></a>Odeslat zpětnou vazbu nabídky

Musí se vyskytnou potíže při použití sady Visual Studio, nebo pokud máte návrhy na vylepšení produktu, můžete použít **odeslat zpětnou vazbu** nabídce v horní části okna nástroje Visual Studio.

![Odeslat nabídku názoru v sadě Visual Studio](../ide/media/quickstart-ide-send-feedback.png)

## <a name="next-steps"></a>Další kroky

Jsme se zabývali jenom některé funkce sady Visual Studio k seznámit s uživatelským rozhraním. Chcete-li podrobněji:

> [!div class="nextstepaction"]
> [Další informace o editoru kódu](write-and-edit-code.md)

> [!div class="nextstepaction"]
> [Seznamte se s projekty a řešení](../get-started/tutorial-projects-solutions.md)

## <a name="see-also"></a>Viz také:

- [Přehled prostředí IDE sady Visual Studio](../get-started/visual-studio-ide.md)
- [Další funkce sady Visual Studio 2017](../ide/advanced-feature-overview.md)
- [Změna barvy motivu a písma](../ide/quickstart-personalize-the-ide.md)
