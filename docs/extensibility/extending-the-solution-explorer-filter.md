---
title: "Rozšíření filtru Průzkumníka řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Solution Explorer, extending
- extensibility [Visual Studio], projects and solutions
ms.assetid: df976c76-27ec-4f00-ab6d-a26a745dc6c7
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: afcaef724b5fc5f8270e5126e91d421f2e15b946
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-solution-explorer-filter"></a>Rozšíření filtru Průzkumník řešení
Můžete rozšířit **Průzkumníku řešení** filtrovat funkce, které chcete zobrazit nebo skrýt různých souborů. Například můžete vytvořit filtr, který zobrazuje pouze soubory C# – třída objektu pro vytváření v **Průzkumníku**, jak tento návod ukazuje.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="create-a-visual-studio-package-project"></a>Vytvoření balíčku projektu sady Visual Studio  
  
1.  Vytvoření projektu VSIX s názvem `FileFilter`. Přidání vlastního příkazu šablony položka s názvem **FileFilter**. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Přidat odkaz na `System.ComponentModel.Composition` a `Microsoft.VisualStudio.Utilities`.  
  
3.  Zkontrolujte příkaz nabídky se zobrazí na **Průzkumníku řešení** panelu nástrojů. Otevřete soubor FileFilterPackage.vsct.  
  
4.  Změny `<Button>` bloku pro následující:  
  
    ```xml  
    <Button guid="guidFileFilterPackageCmdSet" id="FileFilterId" priority="0x0400" type="Button">  
        <Parent guid="guidSHLMainMenu" id="IDG_VS_TOOLBAR_PROJWIN_FILTERS" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>FileNameFilter</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
### <a name="update-the-manifest-file"></a>Aktualizace souboru Manifest  
  
1.  V souboru source.extension.vsixmanifest Přidejte prostředek, který je součástí MEF.  
  
2.  Na **prostředky** , zvolte **nový** tlačítko.  
  
3.  V **typ** pole, zvolte **Microsoft.VisualStudio.MefComponent**.  
  
4.  V **zdroj** pole, zvolte **na projekt v aktuálním řešení**.  
  
5.  V **projektu** pole, zvolte **FileFilter**a potom zvolte **OK** tlačítko.  
  
### <a name="add-the-filter-code"></a>Přidejte kód filtru  
  
1.  Některé identifikátory GUID přidejte do souboru FileFilterPackageGuids.cs:  
  
    ```csharp  
    public const string guidFileFilterPackageCmdSetString = "00000000-0000-0000-0000-00000000"; // get your GUID from the .vsct file  
    public const int FileFilterId = 0x100;  
    ```  
  
2.  Přidejte soubor třídy do FileFilter projektu s názvem FileNameFilter.cs.  
  
3.  Nahraďte kód níže prázdného oboru názvů a třídy prázdný.  
  
     `Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem rootItems)` Metoda přebírá kolekce, která obsahuje kořenové složky řešení (`rootItems`) a vrátí kolekce položek, které mají být zahrnuty do filtru.  
  
     `ShouldIncludeInFilter` Metoda filtry položek v **Průzkumníku řešení** hierarchii na základě za předpokladu, že zadáte.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using System.Text.RegularExpressions;  
    using System.Threading.Tasks;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio.Shell;  
  
    namespace FileFilter  
    {  
        // Implements ISolutionTreeFilterProvider. The SolutionTreeFilterProvider attribute declares it as a MEF component  
        [SolutionTreeFilterProvider(FileFilterPackageGuids.guidFileFilterPackageCmdSetString, (uint)(FileFilterPackageGuids.FileFilterId))]  
        public sealed class FileNameFilterProvider : HierarchyTreeFilterProvider  
        {  
            SVsServiceProvider svcProvider;  
            IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;  
  
            // Constructor required for MEF composition  
            [ImportingConstructor]  
            public FileNameFilterProvider(SVsServiceProvider serviceProvider, IVsHierarchyItemCollectionProvider hierarchyCollectionProvider)  
            {  
                this.svcProvider = serviceProvider;  
                this.hierarchyCollectionProvider = hierarchyCollectionProvider;  
            }  
  
            // Returns an instance of Create filter class.  
            protected override HierarchyTreeFilter CreateFilter()  
            {  
                return new FileNameFilter(this.svcProvider, this.hierarchyCollectionProvider, FileNamePattern);  
            }  
  
            // Regex pattern for CSharp factory classes  
            private const string FileNamePattern = @"\w*factory\w*(.cs$)";  
  
            // Implementation of file filtering  
            private sealed class FileNameFilter : HierarchyTreeFilter  
            {  
                private readonly Regex regexp;  
                private readonly IServiceProvider svcProvider;  
                private readonly IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;  
  
                public FileNameFilter(  
                    IServiceProvider serviceProvider,  
                    IVsHierarchyItemCollectionProvider hierarchyCollectionProvider,  
                    string fileNamePattern)  
                {  
                    this.svcProvider = serviceProvider;  
                    this.hierarchyCollectionProvider = hierarchyCollectionProvider;  
                    this.regexp = new Regex(fileNamePattern, RegexOptions.IgnoreCase);  
                }  
  
                // Gets the items to be included from this filter provider.   
                // rootItems is a collection that contains the root of your solution  
                // Returns a collection of items to be included as part of the filter  
                protected override async Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem> rootItems)  
                {  
                    IVsHierarchyItem root = HierarchyUtilities.FindCommonAncestor(rootItems);  
                    IReadOnlyObservableSet<IVsHierarchyItem> sourceItems;  
                    sourceItems = await hierarchyCollectionProvider.GetDescendantsAsync(  
                                        root.HierarchyIdentity.NestedHierarchy,  
                                        CancellationToken);  
  
                    IFilteredHierarchyItemSet includedItems = await hierarchyCollectionProvider.GetFilteredHierarchyItemsAsync(  
                        sourceItems,  
                        ShouldIncludeInFilter,  
                        CancellationToken);  
                    return includedItems;  
                }  
  
                // Returns true if filters hierarchy item name for given filter; otherwise, false</returns>  
                private bool ShouldIncludeInFilter(IVsHierarchyItem hierarchyItem)  
                {  
                    if (hierarchyItem == null)  
                    {  
                        return false;  
                    }  
                    return this.regexp.IsMatch(hierarchyItem.Text);  
                }  
            }  
        }  
    }  
  
    ```  
  
4.  V FileFilter.cs odeberte z konstruktoru FileFilter kód umístění a zpracování příkazu. Výsledek by měl vypadat takto:  
  
    ```csharp  
    private FileFilter(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException("package");  
        }  
  
        this.package = package;  
    }  
    ```  
  
     Odeberte metodu ShowMessageBox().  
  
5.  V FileFilterPackage, cs, nahraďte kód v metodě inicializaci() s následujícími službami:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        Debug.WriteLine (string.Format(CultureInfo.CurrentCulture, "Entering Initialize() of: {0}", this.ToString()));  
        base.Initialize();  
    }  
    ```  
  
### <a name="test-your-code"></a>Otestujte svůj kód  
  
1.  Sestavte a spusťte projekt. Zobrazí se druhé instance Visual Studio. To se označuje jako experimentální instance.  
  
2.  V experimentální instanci sady Visual Studio otevřete projekt C#.  
  
3.  Vyhledejte tlačítko, které jste přidali na panelu nástrojů Průzkumníka řešení. Mělo by být čtvrté tlačítko od levého okraje.  
  
4.  Když kliknete na tlačítko, by měli být filtrovány všechny soubory a měli byste vidět "všechny položky byly filtrovány ze zobrazení." v Průzkumníku řešení.