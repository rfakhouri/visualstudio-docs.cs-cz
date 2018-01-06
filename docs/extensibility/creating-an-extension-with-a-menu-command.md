---
title: "Vytvoření rozšíření pomocí příkazu v nabídce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- write a vspackage
- vspackage
- tutorials
- visual studio package
ms.assetid: f97104c8-2bcb-45c7-a3c9-85abeda8df98
caps.latest.revision: "56"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3d4e1be21a7471d318a3429dae60f484227a4f26
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-an-extension-with-a-menu-command"></a>Vytvoření rozšíření pomocí příkazu nabídky
Tento návod ukazuje, jak vytvořit rozšíření s příkaz nabídky, která spustí program Poznámkový blok.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-menu-command"></a>Vytvoření příkazu nabídky  
  
1.  Vytvoření projektu VSIX s názvem **FirstMenuCommand**. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Když na projekt se otevře, přidejte šablonu a vlastní příkaz položka s názvem **FirstCommand**. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **vlastní příkaz**. V **název** pole v dolní části okna, změňte název souboru příkaz **FirstCommand.cs**.  
  
3.  Sestavte projekt a spusťte ladění.  
  
     Zobrazí se experimentální instanci sady Visual Studio. Další informace o experimentální instanci najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).  
  
4.  V experimentální instance, otevřete **nástroje nebo rozšíření a aktualizace** okno. Měli byste vidět **FirstMenuCommand** rozšíření sem. (Pokud otevřete **rozšíření a aktualizace** v instanci pracovní sady Visual Studio, neuvidíte **FirstMenuCommand**).  
  
     Nyní přejděte k **nástroje** nabídky v experimentální instanci. Měli byste vidět **vyvolání FirstCommand** příkaz. V tomto okamžiku ho právě otevře okno se zprávou, která říká "FirstCommandPackage uvnitř FirstMenuCommand.FirstCommand.MenuItemCallback()". Zobrazí jsme ve skutečnosti spuštění programu Poznámkový blok z tohoto příkazu v další části.  
  
## <a name="changing-the-menu-command-handler"></a>Změna obslužná rutina nabídky  
 Teď umožňuje aktualizovat obslužná rutina spustit program Poznámkový blok.  
  
1.  Zastavte ladění a vraťte se k instanci pracovní sady Visual Studio. Otevřete soubor FirstCommand.cs a přidejte následující příkaz using:  
  
    ```csharp  
    using System.Diagnostics;  
    ```  
  
2.  Najít soukromý konstruktor FirstCommand. Toto je kde příkaz se připojili ke službě příkazu a je zadána obslužná rutina příkazu. Změňte název obslužná rutina StartNotepad, následujícím způsobem:  
  
    ```csharp  
    private FirstCommand(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
         OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(CommandSet, CommandId);  
            // Change to StartNotepad handler.  
            MenuCommand menuItem = new MenuCommand(this.StartNotepad, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
3.  Remove – metoda MenuItemCallback a přidejte StartNotepad metodu, která se právě spusťte program Poznámkový blok:  
  
    ```csharp  
    private void StartNotepad(object sender, EventArgs e)  
    {  
        Process proc = new Process();  
        proc.StartInfo.FileName = "notepad.exe";  
        proc.Start();  
    }  
    ```  
  
4.  Nyní vyzkoušejte ji. Při spuštění ladění projektu a klikněte na tlačítko **nástroje / vyvolání FirstCommand**, měli byste vidět instanci programu Poznámkový blok se spustit.  
  
     Můžete použít instanci <xref:System.Diagnostics.Process> třídy ke spuštění jakéhokoliv spustitelného souboru, nikoli jen Poznámkový blok. Vyzkoušejte s calc.exe, např.  
  
## <a name="cleaning-up-the-experimental-environment"></a>Čištění experimentální prostředí  
 Pokud vyvíjíte několik rozšíření, nebo jen prohlížení výsledků s různými verzemi nástroje rozšíření kódu, experimentální prostředí může přestat pracovat způsobem, ke kterému by měl. V takovém případě byste měli spustit skript resetování. Je volána **resetovat Visual Studio 2015 experimentální instanci**, a je dodáván jako součást Visual Studio SDK. Tento skript odebere všechny odkazy na rozšíření v prostředí nástroje experimentální, abyste mohli začít od začátku.  
  
 Můžete získat tohoto skriptu v jednom ze dvou způsobů:  
  
1.  Z plochy, Najít **resetovat Visual Studio 2015 experimentální instanci**.  
  
2.  Z příkazového řádku spusťte následující příkaz:  
  
    ```  
    <VSSDK installation>\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe /Reset /VSInstance=14.0 /RootSuffix=Exp && PAUSE  
  
    ```  
  
## <a name="deploying-your-extension"></a>Nasazení rozšíření  
 Teď, když máte nástroj rozšíření s požadovaným způsobem, je čas myslet sdílení s kolegy a přátel. Je snadné, tak dlouho, dokud mají sadu Visual Studio 2015. Všechny, které musíte udělat, je jejich odeslání souboru VSIX, který jste vytvořili. (Nezapomeňte vytvořit v režimu vydání.)  
  
 V adresáři bin FirstMenuCommand můžete najít soubor VSIX pro tuto příponu. Konkrétně za předpokladu, že jste vytvořili konfigurace verze, bude ve:  
  
 **\<adresář kódu > \FirstMenuCommand\FirstMenuCommand\bin\Release\ FirstMenuCommand.vsix**  
  
 Chcete-li nainstalovat rozšíření, váš přítel musí zavřete všechny otevřené instance sady Visual Studio, pak poklikejte na soubor VSIX, který se vyvolá **instalační program VSIX**. Soubory se zkopírují do **%LocalAppData%\Microsoft\VisualStudio\14.0\Extensions** adresáře.  
  
 Pokud váš přítel přináší Visual Studio znovu, si budete najít rozšíření FirstMenuCommand v **nástroje nebo rozšíření a aktualizace**. Si můžete přejít na **rozšíření a aktualizace** odinstalovat nebo rozšíření, příliš zakázat.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod vám ukázal pouze malou část toho co můžete dělat s rozšíření sady Visual Studio. Tady je seznam krátké jiné (přiměřeně snadno) věcí, které můžete provést rozšíření sady Visual Studio:  
  
1.  Může provádět mnoho další akce s jednoduchý příkaz:  
  
    1.  Přidat vlastní ikonu: [přidání ikony příkazů nabídky](../extensibility/adding-icons-to-menu-commands.md)  
  
    2.  Změňte text příkazu v nabídce: [změna Text příkazu nabídky](../extensibility/changing-the-text-of-a-menu-command.md)  
  
    3.  Přidat místní nabídky k příkazu: [vazby klávesové zkratky pro položky nabídky](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
  
2.  Přidat různé druhy příkazy, nabídek a panelů nástrojů: [rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)  
  
3.  Nástroje systému windows přidávat a rozšiřovat předdefinované okna nástrojů Visual Studio: [rozšíření a přizpůsobení okna nástrojů](../extensibility/extending-and-customizing-tool-windows.md)  
  
4.  Přidat technologii IntelliSense, návrhy kódu a další funkce pro stávající kódu editory: [rozšíření pro Editor a jazyk služby](../extensibility/extending-the-editor-and-language-services.md)  
  
5.  Přidání možnosti a vlastnost stránky a nastavení uživatele do vaší rozšíření: [rozšíření vlastností a v okně Vlastnosti](../extensibility/extending-properties-and-the-property-window.md) a [rozšíření uživatelská nastavení a možnosti](../extensibility/extending-user-settings-and-options.md)  
  
 Ostatní typy rozšíření vyžaduje trochu další práci, jako je například vytvoření nového typu projektu ([rozšíření projekty](../extensibility/extending-projects.md)), vytvoření nového typu editoru ([vytváření vlastní editory a návrhářů,](../extensibility/creating-custom-editors-and-designers.md)), nebo implementace rozšíření v izolovaném prostředí shell: [izolované prostředí sady Visual Studio](../extensibility/visual-studio-isolated-shell.md)