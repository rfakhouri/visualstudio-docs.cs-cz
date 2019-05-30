---
title: Vytváření rozšíření pomocí příkazu nabídky | Dokumentace Microsoftu
ms.date: 3/16/2019
ms.topic: conceptual
helpviewer_keywords:
- write a vspackage
- vspackage
- tutorials
- visual studio package
ms.assetid: f97104c8-2bcb-45c7-a3c9-85abeda8df98
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fb18792e2d0d357bb131af6c12e97425cd72fd05
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345374"
---
# <a name="create-an-extension-with-a-menu-command"></a>Vytvoření rozšíření pomocí příkazu nabídky

Tento návod ukazuje, jak vytvořit rozšíření pomocí příkazu nabídky, který spustí Poznámkový blok.

## <a name="prerequisites"></a>Požadavky

Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-a-menu-command"></a>Vytvoření příkazu nabídky

1. Vytvořte projekt VSIX s názvem **FirstMenuCommand**. Šablona projektu VSIX v můžete najít **nový projekt** dialogové okno tak, že "vsix".

2. Po otevření projektu přidat vlastní příkaz šablonu položky s názvem **FirstCommand**. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat** > **nová položka**. V **přidat novou položku** dialogové okno, přejděte na **Visual C#**  > **rozšiřitelnost** a vyberte **vlastního příkazu**. V **název** pole v dolní části okna, změňte název souboru příkazu *FirstCommand.cs*.

3. Sestavte projekt a spusťte ladění.

    Experimentální instanci sady Visual Studio se zobrazí. Další informace o experimentální instanci najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).

::: moniker range="vs-2017"

4. V experimentální instanci aplikace, otevřete **nástroje** > **rozšíření a aktualizace** okna. Měli byste vidět **FirstMenuCommand** rozšíření tady. (Pokud otevřete **rozšíření a aktualizace** v instanci pracovního sadě Visual Studio, neuvidíte **FirstMenuCommand**).

::: moniker-end

::: moniker range=">=vs-2019"

4. V experimentální instanci aplikace, otevřete **rozšíření** > **spravovat rozšíření** okna. Měli byste vidět **FirstMenuCommand** rozšíření tady. (Pokud otevřete **spravovat rozšíření** v instanci pracovního sadě Visual Studio, neuvidíte **FirstMenuCommand**).

::: moniker-end

Teď přejděte **nástroje** nabídky v experimentální instanci aplikace. Měli byste vidět **vyvolat FirstCommand** příkazu. V tomto okamžiku zobrazí okno se zprávou, že příkaz **FirstCommandPackage uvnitř FirstMenuCommand.FirstCommand.MenuItemCallback()** . Uvidíme, jak se ve skutečnosti spustí program Poznámkový blok z tohoto příkazu v další části.

## <a name="change-the-menu-command-handler"></a>Změnit obslužná rutina příkazu nabídky

Teď můžeme aktualizovat obslužná rutina příkazu Spustit Poznámkový blok.

1. Zastavit ladění a vrátit se zpět k vaší instanci pracovní sady Visual Studio. Otevřít *FirstCommand.cs* soubor a přidejte následující příkaz using:

    ```csharp
    using System.Diagnostics;
    ```

2. Najdete soukromý konstruktor FirstCommand. Toto je kde příkazu se připojili ke službě příkazu a zadaná obslužná rutina příkazu. Změňte název obslužná rutina příkazu StartNotepad, následujícím způsobem:

    ```csharp
    private FirstCommand(AsyncPackage package, OleMenuCommandService commandService)
    {
        this.package = package ?? throw new ArgumentNullException(nameof(package));
        commandService = commandService ?? throw new ArgumentNullException(nameof(commandService));

        CommandID menuCommandID = new CommandID(CommandSet, CommandId);
        // Change to StartNotepad handler.
        MenuCommand menuItem = new MenuCommand(this.StartNotepad, menuCommandID);
        commandService.AddCommand(menuItem);
    }
    ```

3. Odebrat `MenuItemCallback` metoda a přidejte `StartNotepad` metodu, která se právě spusťte program Poznámkový blok:

    ```csharp
    private void StartNotepad(object sender, EventArgs e)
    {
        Process proc = new Process();
        proc.StartInfo.FileName = "notepad.exe";
        proc.Start();
    }
    ```

4. Nyní vyzkoušejte. Při spuštění ladění projektu a klikněte na tlačítko **nástroje** > **vyvolat FirstCommand**, byste měli vidět instance poznámkového bloku přijít.

    Můžete použít instanci <xref:System.Diagnostics.Process> má třída spustit libovolný spustitelný soubor, nejen Poznámkový blok. Vyzkoušejte si to s `calc.exe`, např.

## <a name="clean-up-the-experimental-environment"></a>Vyčistěte experimentální prostředí.

Pokud vyvíjíte několik rozšíření nebo stačí zkoumání výsledků s různými verzemi kódu rozšíření, experimentální prostředí mohou přestat fungovat tak, jak by měl. V takovém případě byste měli spustit skript obnovení. Je volána **resetovat experimentální instanci aplikace Visual Studio**, a je dodáván jako součást sady Visual Studio SDK. Tento skript odebere všechny odkazy na vaše rozšíření v experimentální prostředí, abyste je mohli začít úplně od začátku.

Můžete získat tohoto skriptu v jednom ze dvou způsobů:

1. Z plochy, vyhledejte **resetovat experimentální instanci aplikace Visual Studio**.

2. Z příkazového řádku spusťte následující příkaz:

    ```xml
    <VSSDK installation>\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe /Reset /VSInstance=<version> /RootSuffix=Exp && PAUSE

    ```

## <a name="deploy-your-extension"></a>Nasazení vašeho rozšíření

Teď, když máte rozšíření nástroje s požadovaným způsobem, je čas přemýšlení o sdílení s přáteli nebo kolegy. Je to jednoduché, za předpokladu, že mají nainstalovanou sadu Visual Studio 2015. Vše, co musíte udělat poslal je *VSIX* souborů, které jste vytvořili. (Nezapomeňte vytvořit v režimu vydání.)

Můžete najít *VSIX* u tohoto rozšíření v soubor *FirstMenuCommand* adresáře bin. Konkrétně za předpokladu, že jste vytvořili konfiguraci vydané verze, bude ve:

*\<adresář kódu > \FirstMenuCommand\FirstMenuCommand\bin\Release\ FirstMenuCommand.vsix*

K instalaci rozšíření, přítele musí zavřít všechny otevřené instance sady Visual Studio a pak dvakrát klikněte *VSIX* souboru, kterým se zobrazí **instalátor VSIX**. Soubory se zkopírují do *%LocalAppData%\Microsoft\VisualStudio\<verze > \Extensions* adresáře.

Když přítele sady Visual Studio zobrazí znovu, naleznou FirstMenuCommand rozšíření v **nástroje** > **rozšíření a aktualizace**. Můžete přejít na **rozšíření a aktualizace** odinstalace nebo zakázání rozšíření, příliš.

## <a name="next-steps"></a>Další kroky

Tento návod vám ukázal pouze malou část můžete dělat pomocí rozšíření sady Visual Studio. Tady je krátký seznam (poměrně snadno) je dobré, které vám pomůžou s rozšířeními sady Visual Studio:

1. Můžete provést mnoho dalších věcí s jednoduchý příkaz:

   1. Přidáte vlastní ikonu: [Přidání ikon k příkazům nabídky](../extensibility/adding-icons-to-menu-commands.md)

   2. Změna textu příkazu nabídky: [Změna textu příkazu nabídky](../extensibility/changing-the-text-of-a-menu-command.md)

   3. Přidání místní nabídky k příkazu: [Vytvoření vazby klávesové zkratky a položkami nabídky](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)

2. Přidáte různé druhy příkazy, nabídky a panely nástrojů: [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)

3. Přidat oken nástrojů a rozšíření integrovaných okna nástrojů sady Visual Studio: [Rozšířit a přizpůsobit panely nástrojů](../extensibility/extending-and-customizing-tool-windows.md)

4. Přidáte do existující editory kódu technologie IntelliSense, kód návrhy a další funkce: [Rozšíření služby jazyk a editor](../extensibility/extending-the-editor-and-language-services.md)

5. Přidání stránky možnosti a vlastnosti a nastavení uživatele do rozšíření: [Rozšíření vlastností a okno Vlastnosti](../extensibility/extending-properties-and-the-property-window.md) a [rozšířit možnosti a nastavení uživatele](../extensibility/extending-user-settings-and-options.md)

   Jiné druhy rozšíření vyžaduje trochu více práce, jako je vytvoření nového typu projektu ([rozšíření projektů](../extensibility/extending-projects.md)), vytvoření nového typu editoru ([vytváření vlastních editorů a návrhářů](../extensibility/creating-custom-editors-and-designers.md)), nebo implementaci vašeho rozšíření izolovaného prostředí: [Prostředí sady Visual Studio izolovaný režim](/visualstudio/extensibility/shell/visual-studio-isolated-shell)
