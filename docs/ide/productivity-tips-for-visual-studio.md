---
title: "Tipy pro vyšší produktivitu pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5e257d8d90d21c4298b92f7bc4b923ed5a720c85
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="productivity-tips-for-visual-studio"></a>Tipy pro vyšší produktivitu pro sadu Visual Studio

Následující tipy, můžete rychle a efektivně zápisu, přejděte a ladění kódu v sadě Visual Studio.

Další informace o běžných klávesových zkratek najdete v tématu [tipy a triky](../ide/tips-and-tricks-for-visual-studio.md). Získat úplný seznam najdete v tématu [identifikuje a přizpůsobení klávesových zkratek](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md) a [výchozí klávesové zkratky](../ide/default-keyboard-shortcuts-in-visual-studio.md).

## <a name="accessing-visual-studio-tools"></a>Přístup k nástroji Visual Studio

Příkazový řádek vývojáře nebo jiný nástroj Visual Studio, můžete přistupovat rychle Pokud připnete nabídky Start nebo na hlavním panelu.

1. V Průzkumníku Windows přejděte do `%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools`.

1. Klikněte pravým tlačítkem myši nebo Otevřít kontextovou nabídku **příkazový řádek vývojáře**a potom zvolte **připnout na Start** nebo **připnout na hlavní panel**.

## <a name="writing-code"></a>Psaní kódu

Napište kód rychleji pomocí následující funkce.

- **Použití ukázkové aplikace**. Vývoj aplikací můžete urychlit stahuje a instaluje ukázkové aplikace z [Microsoft Developer Network](https://code.msdn.microsoft.com/). Můžete si také přečíst určitou technologii nebo programovací koncept stažením a prohlížení sadu ukázka pro tuto oblast.

- **Použití prvku IntelliSense**. Při zadávání kódu v editoru, zobrazí se informace technologie IntelliSense, například vypsat členy, informace o parametrech, rychlé informace, podpis pomoci a dokončení Word. Tyto funkce podporují přibližné shody textu; například seznamy výsledky pro členy seznam obsahuje pouze položky, které začínají znaky, zda jste zadali, ale také položky, které obsahují znak kombinace kdekoli v jejich názvy. Další informace najdete v tématu [pomocí IntelliSense](../ide/using-intellisense.md).

- **Změnit automatické vkládání možností IntelliSense, protože jste zadali kód**. IntelliSense přepnutí do režimu návrhu, můžete určit, že IntelliSense možnosti jsou vloženy pouze v případě, že je explicitně zvolit.

     Pokud chcete povolit režim návrhu, vyberte **Ctrl** + **Alt** + **MEZERNÍK** klíče, nebo v řádku nabídek zvolte **upravit**, **IntelliSense**, **přepnout režim dokončení**.

- **Fragmenty kódu použít**. Můžete použít předdefinované fragmenty nebo vytvořit vlastní fragmenty kódu.

     Chcete-li vložit fragment kódu v řádku nabídek zvolte **upravit**, **IntelliSense**, **Vložit fragment** nebo otevřete místní nabídky v souboru a zvolte **Vložit fragment kódu** . Další informace najdete v tématu [fragmenty kódu](../ide/code-snippets.md).

- **Opravte chyby vloženého kódu**. Rychlé akce vám umožní snadno refactor, generovat nebo jinak změnit kód, který představuje jednu akci. Můžete použít tyto akce pomocí ikonou žárovky ![malé ikonou žárovky](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall"), nebo stisknutím kombinace kláves **Alt + Enter** nebo **Ctrl +.** Pokud je ukazatelem na příslušný řádek kódu. V tématu [rychlé akce](quick-actions.md) Další informace.

- **Zobrazit a upravit definici element kódu**. Můžete rychle zobrazit a upravit modul, ve kterém je definovaný element kódu, jako je členem, proměnné nebo místní.

    Otevřete definici v místním okně, zvýrazněte elementu a potom zvolte **Alt + F12** klíče, nebo otevřete místní nabídku pro element a potom vyberte **funkce Náhled definice**. V okně samostatného kódu otevřete definici, otevřete místní nabídku pro element a zvolte **přechod na definici**.

## <a name="navigating-within-your-code"></a>Navigace v rámci vašeho kódu

 Různé postupy můžete použít k vyhledání a přesunout do určitých umístění ve vašem kódu rychleji.

- **BOOKMARK řádků kódu**. Záložky můžete rychle přecházet na konkrétní řádky kódu v souboru.

    Pokud chcete nastavit záložku, na panelu nabídek, zvolte **upravit**, **záložky**, **Přepnout záložku**. Můžete zobrazit všechny záložky řešení v **záložky** okno. Další informace najdete v tématu [nastavení záložek v kódu](../ide/setting-bookmarks-in-code.md).

- **Vyhledejte symbol definice v souboru**. Můžete hledat v rámci řešení najít definice symbolů a názvy souborů, ale výsledky hledání neobsahují obory názvů nebo lokální proměnné.

   Chcete-li používat tuto funkci na řádku nabídek zvolte **upravit**, **přejít na**.

- **Procházet celková struktura kódu**. V **Průzkumníku**, můžete vyhledat a procházet třídy a jejich typy a členy ve vašich projektů. Můžete také vyhledat symboly, zobrazení hierarchie volání metody, najít odkazy na symboly a provádět další úlohy. Pokud se rozhodnete element kódu v **Průzkumníku řešení**, související soubor se otevře v **Preview** kartě a přesune kurzor na element v souboru. Další informace najdete v tématu [zobrazení struktury kódu](../ide/viewing-the-structure-of-code.md).

## <a name="finding-items-faster"></a>Rychlejší hledání položek

Můžete hledat ve IDE pro příkazy, soubory a možnosti, kromě filtrování obsah nástroj Windows zobrazit pouze relevantní informace pro aktuální úlohu.

- **Filtrovat obsah nástroj windows**. Můžete hledat v rámci obsah mnoho okna nástrojů, jako **sada nástrojů**, **vlastnosti** okně a **Průzkumníku řešení**, ale zobrazení pouze položek, jejichž názvy obsahovat znaky, které zadáte.

- **Zobrazit pouze chyby, které chcete na adresu**. Pokud se rozhodnete **filtru** tlačítko **seznam chyb** nástrojů, můžete snížit počet chyb, které se zobrazují v **seznam chyb** okno. Pouze chyby můžete zobrazit v souborech, které jsou otevřeny v editoru pouze chyby v aktuální soubor, nebo pouze chyby v aktuálním projektu. Můžete také prohledat v okně Seznam chyb, k vyhledání konkrétní chyby.

- **Vyhledání dialogových oken, příkazy nabídky a možnosti**. V [Snadné spuštění](../ide/reference/quick-launch-environment-options-dialog-box.md) zadejte klíčová slova nebo fráze pro položky, které se pokoušíte najít. Například se zobrazí následující možnosti, pokud zadáte `new project`:

    ![Rychlé spuštění výsledky pro 'nový projekt'](../ide/media/productivity_quicklaunch.png "Productivity_QuickLaunch")

    **Snadné spuštění** zobrazí odkazy na **nový projekt** dialogové okno, **přidat novou položku** dialogové okno a stránce projekty a řešení v **možnosti** Dialogové okno, mimo jiné. Rychlé spuštění výsledky mohou také obsahovat soubory projektu a nástroje systému windows.

## <a name="debugging-code"></a>Ladění kódu

Ladění může využívat velké množství času, ale následující tipy vám mohou pomoci urychlit proces.

- **Test stejné stránky, aplikace nebo webu v různých prohlížečích**. Při ladění kódu můžete snadno přepínat mezi nainstalovaných webových prohlížečů, včetně [nástroj Page Inspector (Visual Studio)](http://msdn.microsoft.com/Library/65880969-1ad2-47be-85b9-bb12c81bf209), aniž byste museli spouštět **procházet s** dialogové okno. Můžete použít **cíl ladění** seznam, který je na **standardní** nástrojů vedle **spustit ladění** tlačítko rychle ověření prohlížeče, který používáte jako při ladění nebo zobrazení stránky.

    ![Vyberte možnosti ladění webové prohlížeče](../ide/media/webbrowserdropdowntoolbar.png "WebBrowserDropDownToolbar")

- **Nastavte zarážky dočasné**. Můžete vytvořit dočasný zarážek v aktuálního řádku kódu a současně spuštění ladicího programu. Při kliknutí na tento řádek kódu, ladicího programu vstupuje do režimu pozastavení. Další informace najdete v tématu [procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md).

    Chcete-li tuto funkci použít, zvolte **Ctrl** + **F10** klíče nebo otevřete místní nabídku pro řádek kódu, na kterém chcete rozdělit a potom vyberte **spustit kurzor** .

- **Přesunout bod provádění během ladění**. Můžete přesunout aktuální bod spuštění pro různé části kódu a potom znovu spusťte ladění z tohoto bodu. Tato metoda je užitečná, pokud chcete ladit části kódu, aniž by museli znovu vytvořit všechny kroky, které jsou potřeba k dosažení této části. Další informace najdete v tématu [procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md).

     Pokud chcete přesunout bodu spuštění, přetáhněte do umístění, ve které chcete nastavit další příkaz ve stejném souboru zdroje a potom vyberte žlutý šipku **F5** klíče a pokračujte ladění.

- **Zachycení informací o hodnoty pro proměnné**. Můžete přidat datového tipu proměnné ve vašem kódu a kód pin, aby po dokončení ladění dostanete poslední známé hodnotu proměnné. Další informace najdete v tématu [zobrazení hodnot dat v datových tipech](../debugger/view-data-values-in-data-tips-in-the-code-editor.md).

     Pokud chcete přidat popis dat, musí být ladicí program v režimu pozastavení. Umístěte kurzor na proměnnou a pak zvolte tlačítko se PIN kód na popis dat, který se zobrazí. Ladění je zastavena, zobrazí se v zdrojový soubor vedle řádek kódu, který obsahuje proměnnou ikonou blue PIN kód. Pokud ukážete blue kódu pin, zobrazí se hodnota proměnné z nejnovější relace ladění.

- **Vymazání hodnot proměnných**. Můžete vymazat obsah [hodnot proměnných](../ide/reference/immediate-window.md) v době návrhu zadáním `>cls` nebo`>Edit.ClearAll`

     Další informace o dalších příkazech najdete v tématu [aliasy příkazů Visual Studio](../ide/reference/visual-studio-command-aliases.md).

## <a name="managing-files-toolbars-and-windows"></a>Správa souborů, panely nástrojů a systému Windows

 Současně můžete být práce ve více souborech kódu a přesun mezi několik nástrojů, když budete vyvíjet aplikace. Můžete ponechat pomocí následující tipy uspořádány.

- **Zachovány soubory, které často používáte viditelné v editoru**. Soubory na levé straně na kartě si můžete připnout tak, aby se zobrazoval bez ohledu na to, kolik souborů je otevřen v editoru.

     Pokud chcete připnout soubor, vyberte kartu souboru a poté zvolte **přepnutí PIN kód stavu** tlačítko.

- **Přesunout dokumenty a systému windows do dalších monitorováních**. Pokud používáte více než jedno monitorování při vývoji aplikací, můžete pracovat na částem aplikace snadněji přesunutím soubory, které jsou otevřeny v editoru a jiné monitorování. Také můžete přesunout, že nástroj windows, například windows ladicí program k jiné monitorování a karty ukotvení dokumentu a nástroj windows dohromady a vytvoří "vorech." Další informace najdete v tématu [přizpůsobení rozložení oken v sadě Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md).

     Můžete také spravovat soubory snadněji vytvořením jiná instance **Průzkumníku řešení** a ani ji přesunout do jiné monitorování. Chcete-li vytvořit další instanci **Průzkumníku řešení**, otevřete místní nabídky v **Průzkumníku řešení**a potom zvolte **nové zobrazení Průzkumníka řešení**.

- **Přizpůsobit písma, které se zobrazují v sadě Visual Studio**. Můžete změnit vzhled písma, velikosti a barvy, která se používá u textů v prostředí IDE. Můžete například přizpůsobit barvu elementů konkrétního kódu v editoru a tučné písmo v systému windows nástroj nebo v celé prostředí IDE. Další informace najdete v tématu [postupy: Změna písma a barev](../ide/how-to-change-fonts-and-colors-in-visual-studio.md) a [postupy: Změna písma a barev v editoru](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).

## <a name="see-also"></a>Viz také

[Výchozí klávesové zkratky pro často používané příkazy](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md)  
[Postupy: přizpůsobení nabídek a panelů nástrojů](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)  
[Návod: Vytvoření jednoduché aplikace](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)  
[Rady a tipy k usnadnění přístupu](../ide/reference/accessibility-tips-and-tricks.md)