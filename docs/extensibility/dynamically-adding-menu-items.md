---
title: Dynamicky přidání položek nabídky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- DYNAMICITEMSTART
- menu items, adding dynamically
- menus, adding dynamic items
ms.assetid: d281e9c9-b289-4d64-8d0a-094bac6c333c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bf7c9f8da800e827ac4b1993c55d4d96c8ca9d89
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133260"
---
# <a name="dynamically-adding-menu-items"></a>Dynamicky přidání položek nabídky
Položky nabídky můžete přidat v době běhu zadáním `DynamicItemStart` příkaz příznak na definici tlačítko zástupný symbol v sadě Visual Studio souboru příkaz – Tabulka (.vsct), pak definování (v kódu) počet nabídky položky k zobrazení a zpracování příkazy. Při načítání VSPackage zástupný text nahrazen položky dynamické nabídky.  
  
 Visual Studio použije dynamické seznamy v **nedávno použité** seznamu (naposledy použitých), který zobrazuje názvy dokumenty, které byly nedávno otevřeny, a **Windows** seznam, který zobrazuje názvy systému windows které jsou aktuálně otevřené.   `DynamicItemStart` Příznak na definici příkazu určuje, že příkaz je zástupný symbol, dokud je otevřen VSPackage. Po otevření VSPackage zástupného textu se nahradí 0 nebo více příkazů, které jsou vytvořeny v době běhu a přidat do seznamu dynamické. Nelze zobrazit v nabídce, kde se zobrazí seznamu dynamických, dokud je otevřen VSPackage pozici.  Visual Studio k naplnění seznamu dynamických, požádá VSPackage k a příkazy s ID jehož prvních znaků jsou stejné jako Identifikátor zástupného textu. Když Visual Studio vyhledá odpovídajícího příkazu, přidá do seznamu dynamické název příkazu. Potom přidá ID a hledá jiného odpovídající příkazu a přidejte do seznamu dynamické, dokud nejsou žádné další dynamické příkazy.  
  
 Tento návod ukazuje, jak nastavit projekt po spuštění v řešení sady Visual Studio pomocí příkazu na **Průzkumníku řešení** panelu nástrojů. Ji používá řadič nabídky, který má dynamické rozevírací seznam projektů v aktivním řešení. Aby tento příkaz při žádné řešení není otevřené nebo otevřete řešení má jenom jeden projektu, VSPackage je načtena, jenom když má více projektů řešení.  
  
 Další informace o souborech .vsct najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="creating-an-extension-with-a-menu-command"></a>Vytvoření rozšíření pomocí příkazu nabídky  
  
1.  Vytvoření projektu VSIX s názvem `DynamicMenuItems`.  
  
2.  Po otevření projektu přidejte šablonu a vlastní příkaz položky a pojmenujte ji **DynamicMenu**. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="setting-up-the-elements-in-the-vsct-file"></a>Nastavení prvků v souboru .vsct  
 Pokud chcete vytvořit řadič nabídky k položkám dynamické nabídky na panelu nástrojů, zadejte následující prvky:  
  
-   Dva příkaz skupin, ten, který obsahuje řadič nabídky a jiné, který obsahuje položky nabídky v rozevírací nabídce  
  
-   Element menu jednoho typu `MenuController`  
  
-   Dvě tlačítka, který funguje jako zástupný symbol pro položek nabídky a jiné, který poskytuje ikonu a popis tlačítka na panelu nástrojů.  
  
1.  V DynamicMenuPackage.vsct zadejte ID příkazů. Přejděte k části symboly a nahradit IDSymbol prvky v **guidDynamicMenuPackageCmdSet** GuidSymbol bloku. Je třeba definovat IDSymbol prvky pro dvě skupiny, řadičem nabídky, příkaz zástupný symbol a příkaz ukotvení.  
  
    ```csharp  
    <GuidSymbol name="guidDynamicMenuPackageCmdSet" value="{ your GUID here }">  
        <IDSymbol name="MyToolbarItemGroup" value="0x1020" />  
        <IDSymbol name="MyMenuControllerGroup" value="0x1025" />  
        <IDSymbol name="MyMenuController" value ="0x1030"/>  
        <IDSymbol name="cmdidMyAnchorCommand" value="0x0103" />  
        <!-- NOTE: The following command expands at run time to some number of ids.  
         Try not to place command ids after it (e.g. 0x0105, 0x0106).  
         If you must add a command id after it, make the gap very large (e.g. 0x200) -->  
        <IDSymbol name="cmdidMyDynamicStartCommand" value="0x0104" />  
    </GuidSymbol>    
    ```  
  
2.  V části skupiny odstranit existující skupiny a přidejte dvě skupiny, kterou jste právě zadali:  
  
    ```  
    <Groups>  
        <!-- The group that adds the MenuController on the Solution Explorer toolbar.   
             The 0x4000 priority adds this group after the group that contains the  
             Preview Selected Items button, which is normally at the far right of the toolbar. -->  
        <Group guid="guidDynamicMenuPackageCmdSet" id="MyToolbarItemGroup" priority="0x4000" >  
            <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN" />  
        </Group>  
        <!-- The group for the items on the MenuController drop-down. It is added to the MenuController submenu. -->  
        <Group guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" priority="0x4000" >  
            <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" />  
        </Group>  
    </Groups>  
    ```  
  
     Přidáte MenuController. Nastavte příznak příkaz DynamicVisibility, protože to není vždy viditelné. ButtonText se nezobrazí.  
  
    ```  
    <Menus>  
        <!-- The MenuController to display on the Solution Explorer toolbar.  
             Place it in the ToolbarItemGroup.-->  
        <Menu guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" priority="0x1000" type="MenuController">  
            <Parent guid="guidDynamicMenuPackageCmdSet" id="MyToolbarItemGroup" />  
            <CommandFlag>DynamicVisibility</CommandFlag>  
            <Strings>  
               <ButtonText></ButtonText>  
           </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
3.  Přidáte dvě tlačítka, jeden jako zástupný symbol pro položky dynamické nabídky a druhý jako kotvu pro MenuController.  
  
     Nadřazený tlačítko zástupný text je **MyMenuControllerGroup**. Přidejte příkaz příznaky DynamicItemStart, DynamicVisibility a TextChanges na tlačítko zástupný symbol. ButtonText se nezobrazí.  
  
     Tlačítko ukotvení obsahuje ikonu a text popisku. Nadřazený tlačítko ukotvení je také **MyMenuControllerGroup**. Přidejte příznak NoShowOnMenuController příkaz a ujistěte se, že tlačítko nezobrazí ve skutečnosti v rozevírací nabídce řadiče nabídky a příznak FixMenuController příkaz aby trvalé ukotvení.  
  
    ```  
    <!-- The placeholder for the dynamic items that expand to N items at runtime. -->  
    <Buttons>  
        <Button guid="guidDynamicMenuPackageCmdSet" id="cmdidMyDynamicStartCommand" priority="0x1000" >  
          <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" />  
          <CommandFlag>DynamicItemStart</CommandFlag>  
          <CommandFlag>DynamicVisibility</CommandFlag>  
          <CommandFlag>TextChanges</CommandFlag>  
          <!-- This text does not appear. -->  
          <Strings>  
            <ButtonText>Project</ButtonText>  
          </Strings>  
        </Button>  
  
        <!-- The anchor item to supply the icon/tooltip for the MenuController -->  
        <Button guid="guidDynamicMenuPackageCmdSet" id="cmdidMyAnchorCommand" priority="0x0000" >  
          <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" />  
          <!-- This is the icon that appears on the Solution Explorer toolbar. -->  
          <Icon guid="guidImages" id="bmpPicArrows"/>  
          <!-- Do not show on the menu controller's drop down list-->  
          <CommandFlag>NoShowOnMenuController</CommandFlag>  
          <!-- Become the permanent anchor item for the menu controller -->  
          <CommandFlag>FixMenuController</CommandFlag>  
          <!-- The text that appears in the tooltip.-->  
          <Strings>  
            <ButtonText>Set Startup Project</ButtonText>  
          </Strings>  
        </Button>  
    </Buttons>  
    ```  
  
4.  Přidejte ikonu do projektu (ve složce prostředky) a poté přidejte odkaz na něj v souboru .vsct. V tomto návodu použijeme ikonu šipky, která je zahrnuta v šabloně projektů.  
  
5.  Přidáte oddíl VisibilityConstraints mimo části příkazy těsně před části symboly. (Může se zobrazit upozornění Pokud přidáte po symboly.) V této části je zajištěno, že řadiče nabídky se zobrazí, jenom když je načten řešení s více projekty.  
  
    ```  
    <VisibilityConstraints>  
         <!--Make the MenuController show up only when there is a solution with more than one project loaded-->  
        <VisibilityItem guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" context="UICONTEXT_SolutionHasMultipleProjects"/>  
    </VisibilityConstraints>  
    ```  
  
## <a name="implementing-the-dynamic-menu-command"></a>Implementace příkaz dynamická nabídka  
 Vytvořte třídu příkaz dynamická nabídka, která dědí z <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>. V této implementaci určuje konstruktoru predikát má být použit pro odpovídající příkazy. Je nutné přepsat <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.DynamicItemMatch%2A> metoda pomocí této predikát nastavit <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.MatchedCommandId%2A> vlastnosti, které identifikuje příkaz, který má být volána.  
  
1.  Vytvoření nového jazyka C# – třída souboru s názvem DynamicItemMenuCommand.cs a přidejte třídu s názvem **DynamicItemMenuCommand** který dědí z <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>:  
  
    ```csharp  
    class DynamicItemMenuCommand : OleMenuCommand  
    {  
  
    }  
  
    ```  
  
2.  Přidejte následující příkazy:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using System.ComponentModel.Design;  
    ```  
  
3.  Přidejte soukromé pole k uložení predikát shody:  
  
    ```csharp  
    private Predicate<int> matches;  
  
    ```  
  
4.  Přidejte konstruktor, který dědí z <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> konstruktor a určuje obslužná rutina příkazu a <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> obslužné rutiny. Přidejte predikát pro párování příkaz:  
  
    ```csharp  
    public DynamicItemMenuCommand(CommandID rootId, Predicate<int> matches, EventHandler invokeHandler, EventHandler beforeQueryStatusHandler)  
        : base(invokeHandler, null /*changeHandler*/, beforeQueryStatusHandler, rootId)  
    {  
        if (matches == null)  
        {  
            throw new ArgumentNullException("matches");  
        }  
  
        this.matches = matches;  
    }  
    ```  
  
5.  Přepsání <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.DynamicItemMatch%2A> metody, které se volá shod predikátu a nastaví <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.MatchedCommandId%2A> vlastnost:  
  
    ```csharp  
    public override bool DynamicItemMatch(int cmdId)  
    {  
        // Call the supplied predicate to test whether the given cmdId is a match.  
        // If it is, store the command id in MatchedCommandid   
        // for use by any BeforeQueryStatus handlers, and then return that it is a match.  
        // Otherwise clear any previously stored matched cmdId and return that it is not a match.  
        if (this.matches(cmdId))  
        {  
            this.MatchedCommandId = cmdId;  
            return true;  
        }  
  
        this.MatchedCommandId = 0;  
        return false;  
    }  
    ```  
  
## <a name="adding-the-command"></a>Přidání příkazu  
 Konstruktor DynamicMenu je, kde nastavíte příkazy nabídky, včetně dynamické nabídky a položky nabídky.  
  
1.  DynamicMenuPackage.cs přidejte GUID sadu příkazů nástroje a ID příkazu:  
  
    ```csharp  
    public const string guidDynamicMenuPackageCmdSet = "00000000-0000-0000-0000-00000000";  // get the GUID from the .vsct file  
    public const uint cmdidMyCommand = 0x104;  
    ```  
  
2.  V souboru DynamicMenu.cs, přidejte následující příkazy:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using System.ComponentModel.Design;  
    ```  
  
3.  Ve třídě DynamicMenu přidejte soukromé pole **dte2**.  
  
    ```csharp  
    private DTE2 dte2;  
    ```  
  
4.  Přidání privátní rootItemId pole:  
  
    ```csharp  
    private int rootItemId = 0;  
    ```  
  
5.  V konstruktoru DynamicMenu přidejte příkaz nabídky. V další části budeme definovat obslužná rutina `BeforeQueryStatus` obslužné rutiny události a predikát shodu.  
  
    ```csharp  
    private DynamicMenu(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            // Add the DynamicItemMenuCommand for the expansion of the root item into N items at run time.   
            CommandID dynamicItemRootId = new CommandID(new Guid(DynamicMenuPackageGuids.guidDynamicMenuPackageCmdSet), (int)DynamicMenuPackageGuids.cmdidMyCommand);  
            DynamicItemMenuCommand dynamicMenuCommand = new DynamicItemMenuCommand(dynamicItemRootId,  
                IsValidDynamicItem,  
                OnInvokedDynamicItem,  
                OnBeforeQueryStatusDynamicItem);  
                commandService.AddCommand(dynamicMenuCommand);  
                }  
  
        dte2 = (DTE2)this.ServiceProvider.GetService(typeof(DTE));  
    }  
    ```  
  
## <a name="implementing-the-handlers"></a>Implementace obslužných rutin  
 Pokud chcete implementovat dynamické položky nabídky na řadiči nabídky, je nutné zpracovat příkaz při kliknutí na položku dynamické. Musíte také implementovat logiku, která nastaví stav položky nabídky. Přidání obslužných rutin k třídě DynamicMenu.  
  
1.  K implementaci **nastavit spouštěný projekt** příkaz, přidejte **OnInvokedDynamicItem** obslužné rutiny události. Vypadá to, jejíž název je stejný jako text příkazu, který má byla volána a nastaví ho jako projekt po spuštění nastavením jeho absolutní cestu v projektu <xref:EnvDTE.SolutionBuild.StartupProjects%2A> vlastnost.  
  
    ```csharp  
    private void OnInvokedDynamicItem(object sender, EventArgs args)  
    {  
        DynamicItemMenuCommand invokedCommand = (DynamicItemMenuCommand)sender;  
        // If the command is already checked, we don't need to do anything  
        if (invokedCommand.Checked)  
            return;  
  
        // Find the project that corresponds to the command text and set it as the startup project  
        var projects = dte2.Solution.Projects;  
        foreach (Project proj in projects)  
        {  
            if (invokedCommand.Text.Equals(proj.Name))  
            {  
                dte2.Solution.SolutionBuild.StartupProjects = proj.FullName;  
                return;  
            }  
        }  
    }  
    ```  
  
2.  Přidat `OnBeforeQueryStatusDynamicItem` obslužné rutiny události. Toto je obslužná rutina volána před provedením `QueryStatus` událostí. Se určuje, zda položky nabídky položku "Skutečná", tedy ne zástupný symbol položku, a zda je položka již zaškrtnuté (což znamená, že projekt je již nastavena jako projekt po spuštění).  
  
    ```csharp  
    private void OnBeforeQueryStatusDynamicItem(object sender, EventArgs args)  
    {  
        DynamicItemMenuCommand matchedCommand = (DynamicItemMenuCommand)sender;  
        matchedCommand.Enabled = true;  
        matchedCommand.Visible = true;  
  
        // Find out whether the command ID is 0, which is the ID of the root item.  
        // If it is the root item, it matches the constructed DynamicItemMenuCommand,  
         // and IsValidDynamicItem won't be called.  
        bool isRootItem = (matchedCommand.MatchedCommandId == 0);  
  
        // The index is set to 1 rather than 0 because the Solution.Projects collection is 1-based.  
        int indexForDisplay = (isRootItem ? 1 : (matchedCommand.MatchedCommandId - (int) DynamicMenuPackageGuids.cmdidMyCommand) + 1);  
  
        matchedCommand.Text = dte2.Solution.Projects.Item(indexForDisplay).Name;  
  
        Array startupProjects = (Array)dte2.Solution.SolutionBuild.StartupProjects;  
        string startupProject = System.IO.Path.GetFileNameWithoutExtension((string)startupProjects.GetValue(0));  
  
        // Check the command if it isn't checked already selected  
        matchedCommand.Checked = (matchedCommand.Text == startupProject);  
  
        // Clear the ID because we are done with this item.  
        matchedCommand.MatchedCommandId = 0;  
    }  
    ```  
  
## <a name="implementing-the-command-id-match-predicate"></a>Implementace predikát shodu ID příkazu  
  
1.  Nyní implementujte predikát shodu. Je potřeba určit dvě věci: nejprve, zda se ID příkazu, který je platný (je větší než nebo rovna hodnotě ID deklarované příkazu) a druhé, zda Určuje možné projektu (je menší než počet projekty v řešení).  
  
    ```csharp  
    private bool IsValidDynamicItem(int commandId)  
    {  
        // The match is valid if the command ID is >= the id of our root dynamic start item   
        // and the command ID minus the ID of our root dynamic start item  
        // is less than or equal to the number of projects in the solution.  
        return (commandId >= (int)DynamicMenuPackageGuids.cmdidMyCommand) && ((commandId - (int)DynamicMenuPackageGuids.cmdidMyCommand) < dte2.Solution.Projects.Count);  
    }  
    ```  
  
## <a name="setting-the-vspackage-to-load-only-when-a-solution-has-multiple-projects"></a>Nastavení VSPackage načíst jenom v případě, že má více projektů řešení  
 Protože **nastavit spouštěný projekt** příkaz nebude mít smysl, pokud aktivním řešení obsahuje více než jeden projekt, můžete nastavit vaše VSPackage k automaticky načíst jenom v takovém případě. Používáte <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> společně s kontext uživatelského rozhraní <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids.SolutionHasMultipleProjects>. V souboru DynamicMenuPackage.cs přidejte do třídy DynamicMenuPackage následující atributy:  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
[ProvideMenuResource("Menus.ctmenu", 1)]  
[ProvideAutoLoad(UIContextGuids.SolutionHasMultipleProjects)]  
[Guid(DynamicMenuPackage.PackageGuidString)]  
public sealed class DynamicMenuItemsPackage : Package  
{}  
```  
  
## <a name="testing-the-set-startup-project-command"></a>Testování nastavte projekt po spuštění příkazu  
 Nyní můžete otestovat váš kód.  
  
1.  Sestavte projekt a spusťte ladění. Experimentální instanci by se zobrazit.  
  
2.  V experimentální instance otevřete řešení, které má více než jeden projekt.  
  
     Měli byste vidět na ikonu šipky na **Průzkumníku řešení** panelu nástrojů. Při rozšiřování, by se zobrazit položky nabídky, které představují různé projekty v řešení.  
  
3.  Pokud jeden z projektů zaškrtnete, bude projekt po spuštění.  
  
4.  Když zavřete řešení nebo otevřete řešení, které má pouze jeden projekt, by měl zmizet ikonu panelu nástrojů.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)   
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)