---
title: "Nejčastější dotazy: Převádění doplňků na rozšíření VSPackage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a01d333-6e31-423f-ae06-5091a4fcb7a9
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 43376b304637ffe59d443ee82350d5492133db2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="faq-converting-add-ins-to-vspackage-extensions"></a>Nejčastější dotazy: Převádění doplňků na VSPackage rozšíření
Doplňky jsou nyní zastaralé. Chcete-li nové rozšíření sady Visual Studio, potřebujete vytvořit VSIX rozšíření. Tady najdete odpovědi na některé nejčastější dotazy o tom, jak převést přidat v sadě Visual Studio na VSIX rozšíření.  
  
> [!WARNING]
>  Spouštění v sadě Visual Studio 2015 pro projekty C# a Visual Basic, můžete použít VSIX projekt a přidat šablony položek pro příkazy nabídky okna nástrojů a VSPackages. Další informace najdete v tématu [co je nového ve Visual Studio 2015 SDK](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md).  
  
> [!IMPORTANT]
>  V mnoha případech můžete jednoduše přenést kódu doplňku na projekt VSIX se položka VSPackage projektu. Můžete získat objekt automatizace DTE voláním <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> v <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda.  
>   
>  `DTE2 dte = (DTE2)GetService(typeof(DTE));`  
>   
>  Další informace najdete v tématu [jak v VSPackage spuštěním vlastního kódu doplňku?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_RunAddin) níže.  
  
## <a name="what-software-do-i-need-to-develop-vsix-extensions"></a>Jaký software je nutné vyvíjet rozšíření VSIX?  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="wheres-the-extension-documentation"></a>Kde je dokumentace rozšíření?  
 Začněte s [od vyvíjet rozšíření Visual Studia](../extensibility/starting-to-develop-visual-studio-extensions.md). Další články o vývoj rozšíření VSSDK na webu MSDN jsou pod než.  
  
## <a name="can-i-convert-my-add-in-project-to-a-vsix-project"></a>Můžete převést Moje v projektu doplňku do projektu VSIX?  
 O projekt nelze převést přímo do projektu VSIX, protože mechanismy VSIX projekty nejsou stejná jako v doplňku projekty. Šablona projektu VSIX plus šablony položek projektu správné značnou kód, který je poměrně snadné ke zprovoznění a spuštěná jako rozšíření VSIX.  
  
##  <a name="BKMK_StartDeveloping"></a>Jak spustit vývoje rozšíření VSIX?  
 Zde je, jak provedete VSIX, který má příkaz nabídky:  
  
#### <a name="to-make-a-vsix-extension-that-has-a-menu-command"></a>Chcete-li rozšíření VSIX, který má příkaz nabídky  
  
1.  Vytvoření projektu VSIX. (**Soubor**, **nový**, **projektu**, nebo typ **projektu** v **Snadné spuštění** okno). V **nový projekt** dialogové okno, rozbalte seznam **Visual C# nebo rozšíření** nebo **jazyka Visual Basic nebo rozšíření** a vyberte **projektu VSIX**.) Název projektu **TestExtension** a zadejte umístění pro ni.  
  
2.  Přidat **vlastní příkaz** šablony položek projektu. (Klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a vyberte **přidat / novou položku**. V **nový projekt** dialogové okno pro buď Visual C# nebo Visual Basic, vyberte **rozšiřitelnost** uzel a vyberte možnost **vlastní příkaz**.)  
  
3.  Stisknutím klávesy F5 sestavit a spustit projekt v režimu ladění.  
  
     Zobrazí se druhé instance Visual Studio. Této druhé instance se označuje jako experimentální instance a nemusí mít stejné nastavení jako instanci sady Visual Studio, který používáte k zápisu kódu. Při prvním spuštění experimentální instance, zobrazí se výzva k přihlásit k VS Online a zadejte motiv a profil.  
  
     Na **nástroje** nabídky (v experimentální instanci) byste měli vidět tlačítko s názvem **název Moje příkazu**. Pokud toto tlačítko, by se zobrazit zpráva: **uvnitř TestVSPackagePackage.MenuItemCallback()**.  
  
##  <a name="BKMK_RunAddin"></a>Jak můžete spustit vlastního kódu doplňku v VSPackage?  
 Kódu doplňku obvykle běží v jednom ze dvou způsobů:  
  
-   Aktivuje příkazu nabídky (kód je v `IDTCommandTarget.Exec` metoda)  
  
-   Automaticky při spuštění (kód je v `OnConnection` obslužné rutiny události.)  
  
 Lze provádět stejné akce v VSPackage. Chcete-li přidat kód doplňku v metoda zpětného volání:  
  
#### <a name="to-implement-a-menu-command-in-a-vspackage"></a>K implementaci příkazu nabídky v VSPackage  
  
1.  Vytvořte VSPackage, který má příkaz nabídky. (Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).)  
  
2.  Otevřete soubor, který obsahuje definici VSPackage. (V projektu jazyka C#, má  *\<název projektu >*Package.cs.)  
  
3.  Přidejte následující `using` příkazů do souboru:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  Najít `MenuItemCallback` metoda. Přidejte volání <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> získat <xref:EnvDTE80.DTE2> objektu:  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  Přidejte kód, který vaše doplněk byl v jeho `IDTCommandTarget.Exec` metoda. Například zde je kód, který přidává nové podokně **výstup** okno a v podokně nové výtisků "Některá Text".  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));  
        OutputWindow outputWindow = dte.ToolWindows.OutputWindow;  
  
        OutputWindowPane outputWindowPane = outputWindow.OutputWindowPanes.Add("A New Pane");  
        outputWindowPane.OutputString("Some Text");  
    }  
  
    ```  
  
6.  Sestavte a spusťte tento projekt. Stisknutím klávesy F5 nebo vyberte **spustit** na **ladění** panelu nástrojů. V experimentální instanci sady Visual Studio **nástroje** nabídky by měl mít tlačítko s názvem **název Moje příkazu**. Pokud vyberete toto tlačítko slova **některá Text** by se měla objevit v **výstup** podokna. (Možná budete muset otevřít **výstup** okno.)  
  
 Můžete taky nechat spustit při spuštění kódu. Tento přístup se obecně nedoporučuje pro VSPackage rozšíření. Pokud příliš mnoho rozšíření se pokusí načíst při spuštění sady Visual Studio, může být výrazně delší čas spuštění. Lepší postupem je automaticky načíst VSPackage jenom v případě, že se nesplní nějaká podmínka (např. řešení otevíráte).  
  
 Tento postup ukazuje, jak spustit doplňku kód v VSPackage, který načítá automaticky, když je otevřen řešení:  
  
#### <a name="to-autoload-a-vspackage"></a>K autoload VSPackage  
  
1.  Vytvoření projektu VSIX s položka projektu balíček Visual Studio. (Pokyny k tomu, najdete v části [jak spustit vývoj rozšíření VSIX?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping). Stačí přidat **balíček Visual Studio** místo položky projektu.) Název projektu VSIX **TestAutoload**.  
  
2.  Otevřete TestAutoloadPackage.cs. Najděte řádek, kde je deklarovaná třída balíčku:  
  
    ```csharp  
    public sealed class <name of your package>Package : Package  
    ```  
  
3.  Nad tímto řádkem je sada atributů. Přidejte tento atribut:  
  
    ```csharp  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    ```  
  
4.  Nastavte zarážky v `Initialize()` metoda a spusťte ladění (F5).  
  
5.  V experimentální instance otevřete projekt. VSPackage by se měly načíst a vaší zarážce by měl být přístupů.  
  
 Můžete zadat jiném kontextu, ve kterém se má načíst vaše VSPackage pomocí pole <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>. Další informace najdete v tématu [načítání VSPackages](../extensibility/loading-vspackages.md).  
  
## <a name="how-can-i-get-the-dte-object"></a>Jak získat objekt DTE?  
 Pokud se vaše doplněk nezobrazí uživatelské rozhraní – například příkazy nabídky, tlačítek panelu nástrojů nebo nástroj windows – bude pravděpodobně možné použít kód jako-je, pokud objekt automatizace DTE můžete získat z VSPackage. Tady je jak:  
  
#### <a name="to-get-the-dte-object-from-a-vspackage"></a>Chcete-li získat objekt DTE z VSPackage  
  
1.  V projektu VSIX pomocí šablony položky balíček Visual Studio, vyhledejte  *\<název projektu >*Package.cs souboru. Toto je třída, která je odvozena z <xref:Microsoft.VisualStudio.Shell.Package>; ho můžete pracovat s Visual Studio. V takovém případě použijte jeho <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> získat <xref:EnvDTE80.DTE2> objektu.  
  
2.  Přidat tyto `using` příkazy:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
3.  Najít `Initialize` metoda. Tato metoda zpracovává příkaz, který jste zadali v Průvodci vytvořením balíčku. Přidejte volání <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> GET pro objekt DTE:  
  
    ```csharp  
    DTE dte = (DTE)GetService(typeof(DTE));  
    ```  
  
 Až budete mít <xref:EnvDTE.DTE> objektu automatizace zbytek kódu doplňku můžete přidat do projektu. Pokud potřebujete <xref:EnvDTE80.DTE2> objektu, může stejnou věc udělat.  
  
## <a name="how-do-i-change-menu-commands-and-toolbar-buttons-in-my-add-in-to-the-vspackage-style"></a>Změna tlačítka panelu nástrojů a příkazy nabídky v mé doplňku na styl VSPackage?  
 Rozšíření VSPackage vytvoření většina příkazů nabídky, panely nástrojů, tlačítka panelu nástrojů a dalších uživatelského rozhraní pomocí souboru .vsct. **Vlastní příkaz** šablony položek projektu vám dává možnost vytvořit příkaz na **nástroje** nabídky. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
 Další informace o souborech .vsct najdete v tématu [jak VSPackages přidat prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md). Návody, které ukazují, jak chcete použít soubor .vsct k přidání položky nabídky, panely nástrojů a tlačítka panelu nástrojů, najdete v části [rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md).  
  
## <a name="how-do-i-add-custom-tool-windows-in-the-vspackage-way"></a>Jak přidat vlastní nástroj windows způsobem VSPackage?  
 Šablony položek projektu okno nástroje vlastní vám dává možnost vytvořit okno nástroje. Další informace o této šablony položek projektu najdete v tématu [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md). Informace o nástroji windows najdete v tématu [rozšíření a přizpůsobení nástrojů Windows](../extensibility/extending-and-customizing-tool-windows.md) a články v něm, zejména [přidání okno nástroje](../extensibility/adding-a-tool-window.md).  
  
## <a name="how-do-i-manage-visual-studio-windows-in-the-vspackage-way"></a>Jak lze spravovat windows Visual Studio způsobem VSPackage?  
 Pokud vaše doplněk spravuje windows Visual Studio, kód doplněk by měla fungovat v VSPackage. Například tento postup ukazuje, jak přidat kód, který spravuje **seznam úkolů** k `MenuItemCallback` metoda VSPackage.  
  
#### <a name="to-insert-window-management-code-from-an-add-in-into-a-vspackage"></a>Vložení kódu okno správy z doplňku do VSPackage  
  
1.  Vytvořit VSPackage, který má příkaz nabídky, jako v [jak spustit vývoj rozšíření VSIX?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping) části.  
  
2.  Otevřete soubor, který obsahuje definici VSPackage. (V projektu jazyka C#, má  *\<název projektu >*Package.cs.)  
  
3.  Přidat tyto `using` příkazy:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  Najít `MenuItemCallback` metoda. Přidejte volání <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> získat <xref:EnvDTE80.DTE2> objektu:  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  Přidejte kód z tohoto doplňku. Například zde je kód, který přidává nové úkoly **seznam úkolů**, uvádí počet úloh a poté se odstraní jeden úkol.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)   
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));   
  
        TaskList tl = (TaskList)dte.ToolWindows.TaskList;   
        askItem tlItem;   
  
        // Add a couple of tasks to the Task List.   
        tlItem = tl.TaskItems.Add(" ", " ", "Test task 1.",    
            vsTaskPriority.vsTaskPriorityHigh, vsTaskIcon.vsTaskIconUser,   
            true, "", 10, true, true);  
        tlItem = tl.TaskItems.Add(" ", " ", "Test task 2.",   
            vsTaskPriority.vsTaskPriorityLow, vsTaskIcon.vsTaskIconComment, true, "", 20, true,true);  
  
        // List the total number of task list items after adding the new task items.  
        System.Windows.Forms.MessageBox.Show("Task Item 1 description: "+tl.TaskItems.Item(2).Description);  
        System.Windows.Forms.MessageBox.Show("Total number of task items: "+tl.TaskItems.Count);   
  
        // Remove the second task item. The items list in reverse numeric order.   
        System.Windows.Forms.MessageBox.Show("Deleting the second task item");  
        tl.TaskItems.Item(2).Delete();  
        System.Windows.Forms.MessageBox.Show("Total number of task items: "+tl.TaskItems.Count);   
    }  
    ```  
  
## <a name="how-do-i-manage-projects-and-solutions-in-a-vspackage"></a>Jak spravovat projekty a řešení v VSPackage?  
 Pokud vaše doplněk spravuje projekty a řešení, kód doplněk by měla fungovat v VSPackage. Například tento postup ukazuje, jak přidat kód, který získá spouštěný projekt.  
  
1.  Vytvořit VSPackage, který má příkaz nabídky, jako v [jak spustit vývoj rozšíření VSIX?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping) části.  
  
2.  Otevřete soubor, který obsahuje definici VSPackage. (V projektu jazyka C#, má  *\<název projektu >*Package.cs.)  
  
3.  Přidat tyto `using` příkazy:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  Najít `MenuItemCallback` metoda. Přidejte volání <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> získat <xref:EnvDTE80.DTE2> objektu:  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  Přidejte kód z tohoto doplňku. Například následující kód získá název spouštěný projekt v řešení. (Řešení vícenásobného projektu je třeba otevřít při spuštění tohoto balíčku.)  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));   
  
        SolutionBuild2 sb = (SolutionBuild2)dte.Solution.SolutionBuild;   
        Project startupProj;   
        string msg = "";  
  
        foreach (String item in (Array)sb.StartupProjects)   
        {  
            msg += item;   
        }  
        System.Windows.Forms.MessageBox.Show("Solution startup Project: "+msg);   
        startupProj = dte.Solution.Item(msg);   
        System.Windows.Forms.MessageBox.Show("Full name of solution's startup project: "+"/n"+startupProj.FullName);   
    }  
    ```  
  
## <a name="how-do-i-set-keyboard-shortcuts-in-a-vspackage"></a>Nastavení klávesové zkratky v VSPackage  
 Můžete použít `<KeyBindings>` element .vsct souboru. V následujícím příkladu, klávesové zkratky pro příkaz `idCommand1` Alt + A a klávesová zkratka pro příkaz `idCommand2` je kombinace kláves Ctrl + Alt + A. Všimněte si syntaxe názvy klíčů.  
  
```xml  
<KeyBindings>  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand1" editor="guidVSStd97" key1="A" mod1="ALT" />  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand2" editor="guidVSStd97" key1="A" mod1="CONTROL" mod2="ALT" />  
</KeyBindings>  
```  
  
## <a name="how-do-i-handle-automation-events-in-a-vspackage"></a>Jak zpracování událostí automatizace v VSPackage?  
 Události automatizace v VSPackage zpracováváte stejným způsobem jako doplněk. Následující kód ukazuje, jak bude zpracováván `OnItemRenamed` událostí. (Tento příklad předpokládá, že jste, že jste již podmínky objekt DTE.)  
  
```csharp  
Events2 dteEvents = (Events2)dte.Events;  
dteEvents.ProjectItemsEvents.ItemRenamed += listener1.OnItemRenamed;   
. . .  
public void OnItemRenamed(EnvDTE.ProjectItem projItem, string oldName)   
{  
    string s = "[Event] Renamed " + oldName + " to " + Path.GetFileName(projItem.get_FileNames(1) + " in project " + projItem.ContainingProject.Name;   
}  
```