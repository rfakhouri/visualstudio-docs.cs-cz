---
title: "Správa projektů Universal Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47926aa1-3b41-410d-bca8-f77fc950cbe7
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6fdb3585d0b2bba5daf248707fa2848d3d32dfdb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="managing-universal-windows-projects"></a>Správa projektů Universal Windows
Univerzální aplikace pro Windows jsou aplikace, které se zaměřují na Windows 8.1 a Windows Phone 8.1, což umožňuje vývojářům používat kód a dalších prostředků na obě platformy. Sdílené kód a prostředky jsou uchovávány v sdílený projekt, zatímco kód specifický pro platformu a prostředky jsou uchovávány v samostatné projekty, jeden pro systém Windows a druhou pro Windows Phone. Další informace o univerzálních aplikací pro Windows najdete v tématu [univerzálních aplikací pro Windows](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx). Visual Studio rozšíření, které spravují projekty měli vědět, že projekty univerzálních aplikací pro Windows mají strukturu, která se liší od jedné platformy aplikace. Tento návod ukazuje, jak přejděte sdílený projekt a spravovat sdílené položky.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="navigate-the-shared-project"></a>Přejděte sdílený projekt  
  
1.  Vytvoření projektu C# VSIX s názvem **TestUniversalProject**. (**Soubor nové, projektu** a potom **balíčku sady Visual Studio C#, rozšiřitelnosti,**). Přidat **vlastní příkaz** šablony položek projektu (v Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**, pak přejděte na **rozšiřitelnost**). Název souboru **TestUniversalProject**.  
  
2.  Přidat odkaz na Microsoft.VisualStudio.Shell.Interop.12.1.DesignTime.dll a Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll (v **rozšíření** části).  
  
3.  Otevřete TestUniversalProject.cs a přidejte následující `using` příkazy:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.PlatformUI;  
    using Microsoft.Internal.VisualStudio.PlatformUI;   
    using System.Collections.Generic;   
    using System.IO;  
    using System.Windows.Forms;  
    ```  
  
4.  Ve třídě TestUniversalProject přidejte soukromé pole přejdete **výstup** okno.  
  
    ```csharp  
    public sealed class TestUniversalProject   
    {  
        IVsOutputWindowPane output;  
    . . .  
    }  
    ```  
  
5.  Nastavte odkaz na podokno výstup uvnitř TestUniversalProject konstruktor:  
  
    ```csharp  
    private TestUniversalProject(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException("package");  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.ShowMessageBox;  
            MenuCommand menuItem = new MenuCommand(eventHandler, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
        // get a reference to the Output window  
                    output = (IVsOutputWindowPane)ServiceProvider.GetService(typeof(SVsGeneralOutputWindowPane));  
    }  
    ```  
  
6.  Odeberte existující kód `ShowMessageBox` metoda:  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)   
    {  
    }  
    ```  
  
7.  Získáte DTE objekt, který budeme používat pro jiné účely několik v tomto návodu. Taky se ujistěte, že řešením je načtena při stisknutí tlačítka nabídky.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {   
        var dte = (EnvDTE.DTE)this.ServiceProvider.GetService(typeof(EnvDTE.DTE));  
        if (dte.Solution != null)   
        {  
            . . .  
        }  
        else   
        {  
            MessageBox.Show("No solution is open");  
            return;   
        }  
    }  
    ```  
  
8.  Najít sdílený projekt. Sdílený projekt je čistě kontejneru; nemá sestavení nebo vytvořit výstupy. Následující metoda vyhledá první sdílený projekt v řešení tak, že vyhledá <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objekt, který má schopnost sdílený projekt.  
  
    ```csharp  
    private IVsHierarchy FindSharedProject()  
    {  
        var sln = (IVsSolution)this.ServiceProvider.GetService(typeof(SVsSolution));  
        Guid empty = Guid.Empty;  
        IEnumHierarchies enumHiers;  
  
        //get all the projects in the solution  
        ErrorHandler.ThrowOnFailure(sln.GetProjectEnum((uint)__VSENUMPROJFLAGS.EPF_LOADEDINSOLUTION, ref empty, out enumHiers));  
        foreach (IVsHierarchy hier in ComUtilities.EnumerableFrom(enumHiers))  
        {  
            if (PackageUtilities.IsCapabilityMatch(hier, "SharedAssetsProject"))  
            {  
                return hier;  
            }  
        }  
        return null;  
    }  
    ```  
  
9. V `ShowMessageBox` metody výstup titulek (název projektu, který se zobrazí v **Průzkumníku řešení**) sdílené projektu.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
  
        if (dte.Solution != null)  
        {  
            var sharedHier = this.FindSharedProject();  
            if (sharedHier != null)  
            {  
                string sharedCaption = HierarchyUtilities.GetHierarchyProperty<string>(sharedHier, (uint)VSConstants.VSITEMID.Root,  
                     (int)__VSHPROPID.VSHPROPID_Caption);  
                output.OutputStringThreadSafe(string.Format("Found shared project: {0}\n", sharedCaption));  
            }  
            else  
            {  
                MessageBox.Show("Solution has no shared project");  
                return;  
            }  
                }  
        else  
        {  
            MessageBox.Show("No solution is open");  
            return;  
        }  
    }  
    ```  
  
10. Získání projektu active platformy. Platforma projekty jsou projekty, které obsahuje kód specifický pro platformu a prostředky. Následující metoda používá nové pole <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID7> získat projektu active platformy.  
  
    ```csharp  
    private IVsHierarchy GetActiveProjectContext(IVsHierarchy hierarchy)  
    {  
        IVsHierarchy activeProjectContext;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hierarchy, (uint)VSConstants.VSITEMID.Root,  
             (int)__VSHPROPID7.VSHPROPID_SharedItemContextHierarchy, out activeProjectContext))  
        {  
            return activeProjectContext;  
        }  
        else  
        {  
            return null;  
        }  
    }  
    ```  
  
11. V `ShowMessageBox` metody výstup titulek active platformy projektu.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
  
        if (dte.Solution != null)  
        {  
            var sharedHier = this.FindSharedProject();  
            if (sharedHier != null)  
            {  
                string sharedCaption = HierarchyUtilities.GetHierarchyProperty<string>(sharedHier, (uint)VSConstants.VSITEMID.Root,  
                     (int)__VSHPROPID.VSHPROPID_Caption);  
                output.OutputStringThreadSafe(string.Format("Shared project: {0}\n", sharedCaption));  
  
                var activePlatformHier = this.GetActiveProjectContext(sharedHier);  
                if (activePlatformHier != null)  
                {  
                    string activeCaption = HierarchyUtilities.GetHierarchyProperty<string>(activePlatformHier,  
                         (uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_Caption);  
                    output.OutputStringThreadSafe(string.Format("Active platform project: {0}\n", activeCaption));  
                }  
                else  
                {  
                MessageBox.Show("Shared project has no active platform project");  
                }  
            }  
            else  
            {  
                MessageBox.Show("Solution has no shared project");  
                return;  
            }  
        }  
        else  
            {  
                MessageBox.Show("No solution is open");  
                return;  
            }  
        }  
  
    ```  
  
12. Iterace projekty platformy. Následující metoda získá všechny import projektů (platforma) z sdílený projekt.  
  
    ```csharp  
    private IEnumerable<IVsHierarchy> EnumImportingProjects(IVsHierarchy hierarchy)  
    {  
        IVsSharedAssetsProject sharedAssetsProject;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hierarchy, (uint)VSConstants.VSITEMID.Root,  
            (int)__VSHPROPID7.VSHPROPID_SharedAssetsProject, out sharedAssetsProject)  
            && sharedAssetsProject != null)  
        {  
            foreach (IVsHierarchy importingProject in sharedAssetsProject.EnumImportingProjects())  
            {  
                yield return importingProject;  
            }  
        }  
    }  
    ```  
  
    > [!IMPORTANT]
    >  Pokud uživatel otevřel projektu jazyka C++ universal Windows aplikace v experimentální instanci, výše uvedený kód vyvolá výjimku. Jedná se o známý problém. Abyste se vyhnuli výjimku, nahraďte `foreach` blokovat výše následujícím kódem:  
  
    ```csharp  
    var importingProjects = sharedAssetsProject.EnumImportingProjects();  
    for (int i = 0; i < importingProjects.Count; ++i)  
    {  
        yield return importingProjects[i];  
    }   
    ```  
  
13. V `ShowMessageBox` metody výstup titulek každý projekt platformy. Vložte následující kód řádku, který produkuje titulek active platformy projektu. V tomto seznamu se objeví pouze projektů platformy, které jsou načteny.  
  
    ```csharp  
    output.OutputStringThreadSafe("Platform projects:\n");  
  
    IEnumerable<IVsHierarchy> projects = this.EnumImportingProjects(sharedHier);  
  
    bool isActiveProjectSet = false;  
    foreach (IVsHierarchy platformHier in projects)  
    {  
        string platformCaption = HierarchyUtilities.GetHierarchyProperty<string>(platformHier, (uint)VSConstants.VSITEMID.Root,  
            (int)__VSHPROPID.VSHPROPID_Caption);  
        output.OutputStringThreadSafe(string.Format(" * {0}\n", platformCaption));  
    }  
    ```  
  
14. Změňte projekt active platformy. Nastaví metodu aktivního projektu pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetProperty%2A>.  
  
    ```csharp  
    private int SetActiveProjectContext(IVsHierarchy hierarchy, IVsHierarchy activeProjectContext)  
    {  
        return hierarchy.SetProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID7.VSHPROPID_SharedItemContextHierarchy, activeProjectContext);  
    }  
    ```  
  
15. V `ShowMessageBox` metoda, změnit projekt active platformy. Vložte tento kód uvnitř `foreach` bloku.  
  
    ```csharp  
    bool isActiveProjectSet = false;  
    string platformCaption = null;  
    foreach (IVsHierarchy platformHier in projects)  
    {  
        platformCaption = HierarchyUtilities.GetHierarchyProperty<string>(platformHier, (uint)VSConstants.VSITEMID.Root,  
             (int)__VSHPROPID.VSHPROPID_Caption);  
        output.OutputStringThreadSafe(string.Format(" * {0}\n", platformCaption));  
  
        // if this project is neither the shared project nor the current active platform project,   
        // set it to be the active project  
        if (!isActiveProjectSet && platformHier != activePlatformHier)  
        {  
            this.SetActiveProjectContext(sharedHier, platformHier);  
            activePlatformHier = platformHier;  
            isActiveProjectSet = true;  
        }  
    }  
    output.OutputStringThreadSafe("set active project: " + platformCaption +'\n');  
    ```  
  
16. Nyní vyzkoušejte ji. Stisknutím klávesy F5 spusťte experimentální instanci. Vytvoření projektu aplikace universal rozbočovače C# v experimentální instanci (v **nový projekt** dialogové okno, **Visual C# / Windows / Windows 8 / Universal nebo rozbočovače aplikace**). Po načtení řešení, přejděte na **nástroje** nabídky a klikněte na tlačítko **vyvolání TestUniversalProject**a potom zkontrolujte text **výstup** podokně. Měli byste vidět něco jako následující:  
  
    ```  
    Found shared project: HubApp.Shared  
    The active platform project: HubApp.Windows  
    Platform projects:  
     * HubApp.Windows  
     * HubApp.WindowsPhone  
    set active project: HubApp.WindowsPhone  
    ```  
  
### <a name="manage-the-shared-items-in-the-platform-project"></a>Správa sdílené položky v projektu platformy  
  
1.  Vyhledejte sdílené položky v projektu platformy. Položky v sdílený projekt se zobrazí v projektu platformy jako sdílené položky. Nejde zobrazit, je **Průzkumníku řešení**, ale můžete provede hierarchii projektu, kde je najít. Následující metoda provede hierarchii a shromažďuje všechny sdílené položky. Výstupy volitelně titulek každé položky. Sdílené položky jsou identifikovány nové vlastnosti <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID7>.  
  
    ```csharp  
    private void InspectHierarchyItems(IVsHierarchy hier, uint itemid, int level, List<uint> itemIds, bool getSharedItems, bool printItems)  
    {  
        string caption = HierarchyUtilities.GetHierarchyProperty<string>(hier, itemid, (int)__VSHPROPID.VSHPROPID_Caption);  
        if (printItems)  
            output.OutputStringThreadSafe(string.Format("{0}{1}\n", new string('\t', level), caption));  
  
        // if getSharedItems is true, inspect only shared items; if it's false, inspect only unshared items  
        bool isSharedItem;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hier, itemid, (int)__VSHPROPID7.VSHPROPID_IsSharedItem, out isSharedItem)  
            && (isSharedItem == getSharedItems))  
        {  
            itemIds.Add(itemid);  
        }  
  
        uint child;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hier, itemid, (int)__VSHPROPID.VSHPROPID_FirstChild, Unbox.AsUInt32, out child)  
            && child != (uint)VSConstants.VSITEMID.Nil)  
        {  
            this.InspectHierarchyItems(hier, child, level + 1, itemIds, isSharedItem, printItems);  
  
            while (HierarchyUtilities.TryGetHierarchyProperty(hier, child, (int)__VSHPROPID.VSHPROPID_NextSibling, Unbox.AsUInt32, out child)  
                && child != (uint)VSConstants.VSITEMID.Nil)  
            {  
                this.InspectHierarchyItems(hier, child, level + 1, itemIds, isSharedItem, printItems);  
            }  
                    }  
    }  
    ```  
  
2.  V `ShowMessageBox` metoda, přidejte následující kód, který provede položky platformy projektu hierarchie. Vložte ho do `foreach` bloku.  
  
    ```csharp  
    output.OutputStringThreadSafe("Walk the active platform project:\n");  
    var sharedItemIds = new List<uint>();  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, sharedItemIds, true, true);  
    ```  
  
3.  Čtení sdílené položky. Sdílené položky se zobrazí v projektu platformy jako skrytá propojených souborů a může číst všechny vlastnosti jako obyčejnou připojené soubory. Následující kód načte úplnou cestu první sdílené položky.  
  
    ```csharp  
    var sharedItemId = sharedItemIds[0];  
    string fullPath;  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(sharedItemId, out fullPath));  
    output.OutputStringThreadSafe(string.Format("Shared item full path: {0}\n", fullPath));  
    ```  
  
4.  Nyní vyzkoušejte ji. Stisknutím klávesy F5 spusťte experimentální instanci. Vytvoření projektu aplikace universal rozbočovače C# v experimentální instanci (v **nový projekt** dialogové okno, **Visual C# / Windows / Windows 8 / Universal nebo rozbočovače aplikace**) přejděte na **nástroje** nabídky a klikněte na tlačítko **vyvolání TestUniversalProject**a potom zkontrolujte text **výstup** podokně. Měli byste vidět něco jako následující:  
  
    ```  
    Found shared project: HubApp.Shared  
    The active platform project: HubApp.Windows  
    Platform projects:  
     * HubApp.Windows  
     * HubApp.WindowsPhone  
    set active project: HubApp.WindowsPhone  
    Walk the active platform project:  
        HubApp.WindowsPhone  
            <HubApp.Shared>  
                App.xaml  
                    App.xaml.cs  
                Assets  
                    DarkGray.png  
                    LightGray.png  
                    MediumGray.png  
                Common  
                    NavigationHelper.cs  
                    ObservableDictionary.cs  
                    RelayCommand.cs  
                    SuspensionManager.cs  
                DataModel  
                    SampleData.json  
                    SampleDataSource.cs  
                HubApp.Shared.projitems  
                Strings  
                    en-US  
                        Resources.resw  
            Assets  
                HubBackground.theme-dark.png  
                HubBackground.theme-light.png  
                Logo.scale-240.png  
                SmallLogo.scale-240.png  
                SplashScreen.scale-240.png  
                Square71x71Logo.scale-240.png  
                StoreLogo.scale-240.png  
                WideLogo.scale-240.png  
            HubPage.xaml  
                HubPage.xaml.cs  
            ItemPage.xaml  
                ItemPage.xaml.cs  
            Package.appxmanifest  
            Properties  
                AssemblyInfo.cs  
            References  
                .NET for Windows Store apps  
                HubApp.Shared  
                Windows Phone 8.1  
            SectionPage.xaml  
                SectionPage.xaml.cs  
    ```  
  
### <a name="detecting-changes-in-platform-projects-and-shared-projects"></a>Detekce změn v projekty platformy a sdílených projektů  
  
1.  Hierarchie a projekt události můžete použít ke zjištění změn v sdílených projektů, stejně jako u projektů platformy. Však položky projektu v sdílený projekt nejsou viditelné, což znamená, že určité události neaktivovat při změně položek sdílený projekt.  
  
     Vezměte v úvahu posloupnost událostí při přejmenování souboru v projektu:  
  
    1.  Název souboru se změní na disku.  
  
    2.  Aktualizovaný soubor projektu obsahuje nový název souboru.  
  
     Události hierarchie (například <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>) obecně sledování změn, zobrazí v uživatelském rozhraní, jako v **Průzkumníku řešení**. Události hierarchie zvažte operace přejmenování souboru sestává z odstranění souboru a poté přidání souboru. Ale při změně neviditelná položek, systém událostí hierarchie aktivuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> událostí, ale ne <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> událostí. Proto při přejmenování souboru v projektu platformy, můžete získat i <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A>, ale Pokud přejmenujete soubor ve sdílené projektu, můžete získat pouze <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A>.  
  
     Sledovat změny v položkách projektu, může zpracovat události položek projektu prostředí DTE (těm, které jsou součástí <xref:EnvDTE.ProjectItemsEventsClass>). Ale pokud jsou zpracování velkého počtu událostí, můžete získat lepší výkon zpracování událostí v <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>. V tomto návodu ukážeme pouze hierarchie události a události DTE. V tomto postupu přidáte naslouchací proces událostí sdílený projekt a projekt platformy. Potom při přejmenování jeden soubor ve sdíleném projektu a další soubor v projektu platformy, se zobrazí události, které se aktivuje například pro každou operaci přejmenovat.  
  
     V tomto postupu přidáte naslouchací proces událostí sdílený projekt a projekt platformy. Potom při přejmenování jeden soubor ve sdíleném projektu a další soubor v projektu platformy, se zobrazí události, které se aktivuje například pro každou operaci přejmenovat.  
  
2.  Přidejte naslouchací proces událostí. Přidejte nový soubor třídu do projektu a pojmenujte ji HierarchyEventListener.cs.  
  
3.  Otevřete soubor HierarchyEventListener.cs a přidejte následující příkazy:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio;  
    using System.IO;  
  
    ```  
  
4.  Máte `HierarchyEventListener` implementaci třídy <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>:  
  
    ```csharp  
    class HierarchyEventListener : IVsHierarchyEvents  
    { }  
  
    ```  
  
5.  Implementace členů <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>, jako v následujícím kódu.  
  
    ```csharp  
    class HierarchyEventListener : IVsHierarchyEvents  
    {  
        private IVsHierarchy hierarchy;  
        IVsOutputWindowPane output;   
  
        internal HierarchyEventListener(IVsHierarchy hierarchy, IVsOutputWindowPane outputWindow) {  
             this.hierarchy = hierarchy;  
             this.output = outputWindow;  
        }  
  
        int IVsHierarchyEvents.OnInvalidateIcon(IntPtr hIcon) {  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnInvalidateItems(uint itemIDParent) {  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemAdded(uint itemIDParent, uint itemIDSiblingPrev, uint itemIDAdded) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemAdded: " + itemIDAdded + "\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemDeleted(uint itemID) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemDeleted: " + itemID + "\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemsAppended(uint itemIDParent) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemsAppended\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnPropertyChanged(uint itemID, int propID, uint flags) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnPropertyChanged: item ID " + itemID + "\n");  
            return VSConstants.S_OK;  
        }  
    }  
  
    ```  
  
6.  Ve stejné třídě přidejte jinou obslužnou rutinu události pro událost DTE <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed>, který dojde vždy, když je položka projektu přejmenovat.  
  
    ```csharp  
    public void OnItemRenamed(EnvDTE.ProjectItem projItem, string oldName)  
    {  
        output.OutputStringThreadSafe(string.Format("[Event] Renamed {0} to {1} in project {2}\n",  
             oldName, Path.GetFileName(projItem.get_FileNames(1)), projItem.ContainingProject.Name));  
    }  
    ```  
  
7.  Zaregistrujte se pro události hierarchie. Je třeba zaregistrovat zvlášť pro každý projekt, kterou sledujete. Přidejte následující kód v `ShowMessageBox`, jeden pro sdílený projekt a druhou pro jeden z projektů platformy.  
  
    ```csharp  
    // hook up the event listener for hierarchy events on the shared project  
    HierarchyEventListener listener1 = new HierarchyEventListener(sharedHier, output);  
    uint cookie1;  
    sharedHier.AdviseHierarchyEvents(listener1, out cookie1);  
  
    // hook up the event listener for hierarchy events on the   
    active project  
    HierarchyEventListener listener2 = new HierarchyEventListener(activePlatformHier, output);  
    uint cookie2;  
    activePlatformHier.AdviseHierarchyEvents(listener2, out cookie2);  
    ```  
  
8.  Zaregistrujte si událost položky projektu DTE <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed>. Přidejte následující kód po spojit druhý naslouchací proces.  
  
    ```csharp  
    // hook up DTE events for project items  
    Events2 dteEvents = (Events2)dte.Events;  
    dteEvents.ProjectItemsEvents.ItemRenamed += listener1.OnItemRenamed;  
  
    ```  
  
9. Změna sdílené položky. Nelze změnit sdílené položky v projektu platformy; Místo toho je nutné upravit v sdílený projekt, který je vlastníkem skutečné tyto položky. Můžete získat odpovídající ID položky v sdílený projekt s <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.IsDocumentInProject%2A>, předá úplná cesta sdílené položky. Potom můžete upravit sdílené položky. Změna rozšířena do projekty platformy.  
  
    > [!IMPORTANT]
    >  Byste měli zjistit, jestli je položka projektu sdílené položce před změnou ho.  
  
     Následující metodu upraví název položky souboru projektu.  
  
    ```csharp  
    private void ModifyFileNameInProject(IVsHierarchy project, string path)  
    {    
        int found;  
        uint projectItemID;  
        VSDOCUMENTPRIORITY[] priority = new VSDOCUMENTPRIORITY[1];  
        if (ErrorHandler.Succeeded(((IVsProject)project).IsDocumentInProject(path, out found, priority, out projectItemID))  
            && found != 0)  
        {  
            var name = DateTime.Now.Ticks.ToString() + Path.GetExtension(path);  
            project.SetProperty(projectItemID, (int)__VSHPROPID.VSHPROPID_EditLabel, name);  
            output.OutputStringThreadSafe(string.Format("Renamed {0} to {1}\n", path,name));  
        }  
    }  
    ```  
  
10. Volat tuto metodu za všechny ostatní kód v `ShowMessageBox` k úpravě souboru název položky v sdílený projekt. Vložení to za kód, který získá úplnou cestu položky v sdílený projekt.  
  
    ```csharp  
    // change the file name of an item in a shared project  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, sharedItemIds, true, true);  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(sharedItemId, out fullPath));   
    output.OutputStringThreadSafe(string.Format("Shared project item ID = {0}, full path = {1}\n", sharedItemId, fullPath));  
    this.ModifyFileNameInProject(sharedHier, fullPath);  
    ```  
  
11. Sestavte a spusťte projekt. Vytvoření aplikace universal rozbočovače C# v experimentální instanci, přejděte na **nástroje** nabídky a klikněte na tlačítko **vyvolání TestUniversalProject**a zkontrolujte text v podokně výstup Obecné. Název první položky v sdílený projekt (Očekáváme, že bude soubor App.xaml) by mělo být změněno a měli byste vidět, který <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed> událost je aktivována. V takovém případě vzhledem k tomu, že přejmenování App.xaml způsobí, že App.xaml.cs k přejmenování i, měli byste vidět čtyři události (dvě pro každou platformu projekt). (DTE události do not track položky v sdílený projekt.) Měli byste vidět dvě <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> události (jeden pro každou platformu projektů), ale ne <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> události.  
  
12. Nyní zkuste přejmenování souboru v projektu platformy a uvidíte rozdíl v události, které získat aktivováno. Přidejte následující kód v `ShowMessageBox` po volání `ModifyFileName`.  
  
    ```csharp  
    // change the file name of an item in a platform project  
    var unsharedItemIds = new List<uint>();  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, unsharedItemIds, false, false);  
  
    var unsharedItemId = unsharedItemIds[0];  
    string unsharedPath;  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(unsharedItemId, out unsharedPath));  
    output.OutputStringThreadSafe(string.Format("Platform project item ID = {0}, full path = {1}\n", unsharedItemId, unsharedPath));  
  
    this.ModifyFileNameInProject(activePlatformHier, unsharedPath);  
    ```  
  
13. Sestavte a spusťte projekt. Vytvoření projektu univerzální C# v experimentální instanci, přejděte na **nástroje** nabídky a klikněte na tlačítko **vyvolání TestUniversalProject**a zkontrolujte text v podokně obecné výstup. Po přejmenování souboru v projektu platformy, měli byste vidět i <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> událostí a <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> událostí. Protože změna souboru způsobeno žádné další soubory, které chcete změnit, a vzhledem k tomu, že kamkoli nemáte získat rozšíří změny položek v projektu platformy, existuje pouze jeden každý z těchto událostí.