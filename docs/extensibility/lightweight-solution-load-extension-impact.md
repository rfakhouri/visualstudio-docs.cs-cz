---
redirect_url: /visualstudio/extensibility/what-s-new-in-the-visual-studio-2017-sdk/
ms.openlocfilehash: 5706797ed88dce5b2f481b17d99e9501b960ddca
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
Title: "jednoduché řešení zatížení (dolní limit) | Microsoft Docs"ms.custom:" "ms.date: ms.reviewer" 01/17/2017":" "ms.suite:" "ms.technology: 
  - ms.tgt_pltfrm "vs-ide-sdk": "" ms.topic: "článku" helpviewer_keywords: 
  - "Načíst VSPackages lightweight řešení"
  - "VSPackages, rychlé řešení zatížení" ms.assetid: 0a71d91e-dc71-4d6b-bbfe-9e4ecd9e5fd1 caps.latest.revision: 1 Autor: ms.author "gregvanl": "gregvanl" správce: ghogen
---
# <a name="lightweight-solution-load-lsl"></a>Prosté řešení zatížení (dolní limit)

## <a name="background-information-on-lsl"></a>Základní informace na dolní limit

Prosté načíst řešení je nová funkce v 2017 VS, které bude výrazně snížit čas načítání řešení, které umožňují rychle zajistit vyšší produktivitu. Pokud je povoleno dolní limit, Visual Studio nenačte plně projekty dokud zahájením práce s nimi.

Dolní limit může ovlivnit rozšíření Visual Studia. Rozšíření, jejichž funkce závisí na projekt, který má být načten nemusí fungovat a nebudou správně fungovat bez následující pokyny zmíněné v tomto dokumentu.

Pro další informace o dolní limit pomocí následujících odkazů:

* [Blog zatížení Lightweight řešení](https://blogs.msdn.microsoft.com/visualstudio/2016/10/11/shorter-solution-load-time-in-visual-studio-15)
* Máte dotazy? Obraťte se na nás na adrese[lslsupport@microsoft.com](mailto:lslsupport@microsoft.com)

## <a name="enable-the-setting-to-load-projects-in-deferred-mode"></a>Povolit nastavení načíst projekty v režimu "odložené"

1. Zavřete všechny aktuálně otevřené řešení.
2. Přejděte na **nástroje** > **možnost** > **projekty a řešení** > **Obecné** nastavení stránka.
3. Zkontrolujte **Lightweight řešení zatížení** políčko Povolit nastavení.

Po otevření řešení s výše zapnutí nastavení rozhraní IDE zobrazuje regulární zobrazení projektů, ale projekty nebyly načteny.

## <a name="differences-between-deferred-load-and-regular-load-of-projects"></a>Rozdíly mezi odložené zatížení a regulární zatížení projektů

S Lightweight řešení zatížení projekty nebyly načteny, při otevírání řešení. Pro tyto "odložené projekty" je vytvořit se zakázaným inzerováním hierarchie. Průzkumníku řešení ukazuje očekávaný zobrazení ikony a názvy projektů, není nijak naznačeno uživatelského rozhraní, které jsou některé nebo všechny projekty v "režimu odložené".

S dolní limit povolené rozšíření už očekávat potřebné projekty jsou při aktivaci operace již zcela načteny. Volající musí zkontrolovat, zda jsou závislé na Načíst projekty. Pokud rozšíření vyžaduje informace z odložené projektu, rozšíření postupujte takto:

1. Načtěte podle potřeby projekty.
2. Použít novou **rozhraní API prostoru** získat informace z odložené projekt bez jeho načítání.

Nové **rozhraní API prostoru** umožňuje získat informace, například vlastnícím projektu zdrojový soubor a všechny zdrojové soubory pro zadaný projekt z projektu odložené pomocí rozšíření. V některých případech jenom omezenou sadu projektů musí být načíst. Možnost zprava je rovnováhu mezi frekvenci operací, snadné alternativní přístupů a celkové činnost koncového uživatele.

Všechny projektu a řešení zatížení související události při vyvolání stále v režimu dolní limit. To umožňuje součásti ze sady VS získat očekávané chování a chovají stejným způsobem jako při jsou načtena projekty. Práci při řešení otevřete výrazně snížit, když související s načítání projektu.

## <a name="ui-requirements-and-changes"></a>Požadavky uživatelského rozhraní a změny

Všechny uživatelského rozhraní musí považovat za projekty načíst a odložené stejné. To znamená, že všechny akce, které lze provést na načíst projektu musí být pro odložené projekty, na několik výjimek. Chcete-li funkce dosáhnout, jsou změny některé stávající platforma pro rozhraní API a také zavedením nových rozhraní API.

### <a name="expectations-for-ui"></a>Očekávání pro uživatelského rozhraní

1. Funkce musí zobrazit že žádné visual rozdíly v závislosti na tom, pokud jsou načtena nebo odložení projekty.
2. Odložené projekty musí zahrnovat všechny výpis nebo výčtu přes načíst projekty řešení.
3. Žádnou akci, která je k dispozici proti načíst projekt by měl být k dispozici pro odložené projektu.
4. Funkce, musí požadavek na načtení projekty pouze tehdy, když:
  * Není přímou interakci s funkcí. Nenačtou ho preventivně projekty.
  * Gesto "V tématu více výsledky" je provedené uživatelem. Níže najdete obecných zásad uživatelského rozhraní.
  * Splnění akcí lze pouze plně načíst projekt. Použijte dolní limit a otevřené rozhraní API projektu, kdykoli je to možné a odeslat žádost o funkce požádá, když není k dispozici funkce.

### <a name="changes-in-platform-apis-to-help-drive-ui"></a>Změny v platformě rozhraní API pro pomoci uživatelského rozhraní

1. Požádat řešení, pokud byl otevřen v režimu Lightweight řešení zatížení a kolik projekty jsou ve stavu odloženého jsou k dispozici nová rozhraní API.
2. Slouží pro novou událost, když jsou načteny všechny odložené projekty v řešení.
3. Nová rozhraní API jsou uvedeny požádat projektu, pokud je odložen.
4. Do zahrnout odložené projekty požadující načíst projekty jsou aktualizovány stávajících rozhraní API.
5. Stávajících rozhraní API se aktualizuje za účelem rychlé řešení, které je úplným načtením po otevření řešení.

### <a name="how-to-add-see-more-results-for-a-feature"></a>Postup přidání "V tématu více výsledky" pro funkci.

Funkce, které provedení dotazu na obsah projekty měli zvážit dopad odložené projekty. V některých situacích funkce můžete získat výsledky jejich dotazu z dolní limit a rozhraní API prostoru pro odložené projekt. V ostatních případech omezení funkce vyžadují projekty tak, aby se jej načíst. Obě tyto situace by měl poskytovat gesto nové "V tématu více výsledky", který umožňuje uživatelům plně zatížení projekty a dotaz znovu. Tato gesto umožňuje funkce, které chcete poskytnout nejlepší aproximace, pokud existují odložené projekty přitom poskytuje způsob, jak získat ideální výsledek při projekty jsou ve skutečnosti načíst uživatele.

Obecné algoritmus pro funkce by měla být:

### <a name="when-the-query-is-performed-over-a-single-project"></a>Pokud se provede dotaz rozhraní prostřednictvím jediného projektu

```csharp
// IsInDeferredState() and EnsureProjectIsLoadedHelper() in this sample can be found in the "Helpful code snippets" section of this document
public void Query(IVsHierarchy projectToQuery)
{
    // 1. Perform calculation/query
    DoQuery(projectToQuery);

    // 2. Present results to the user
    ShowResults();

    // 3. If the project was deferred, then present a "See More Results" UI element
    if (IsInDeferredState(projectToQuery))
    {
        ShowSeeMoreResults();
    }
}

public void OnClick_SeeMoreResults()
{
    // 1. Ask ask for the project to be loaded
    IVsHierarchy projectFromLastQuery = GetProjectFromLastQuery();
    IVsHierarchy loadedProject = EnsureProjectIsLoadedHelper(projectFromLastQuery);

    if (loadedProject != null)
    {
        // 2. Re-run the query on the loaded projects
        Query(loadedProject);
    }
    else
    {
        ShowErrorMessage();
    }
}
```

### <a name="when-the-query-is-performed-over-the-whole-solution"></a>Pokud se provede dotaz rozhraní přes celé řešení

```csharp
// Requires Microsoft.VisualStudio.Shell.Interop.15.0.DesignTime.dll
public void Query()
{
    // 1. Perform calculation/query
    DoQuery();

    // 2. Present results to the user
    ShowResults();

    // 3. If there were deferred projects, then present a "See More Results from all projects" UI element
    var solution = // the solution
    object deferredCount = 0;
    int hr = ((IVsSolution)solution).GetProperty((int)__VSPROPID7.VSPROPID_DeferredProjectCount, out deferredCount);
    if (ErrorHandler.Succeeded(hr) && ((int)deferredCount > 0))
    {
        ShowSeeMoreResults();
    }
}

public void OnClick_SeeMoreResults()
{
    // 1. Force the solution to load, as requested by the user. This brings up a UI with a "Cancel" button (unless supppresed with __VSBSLFLAGS.VSBSLFLAGS_NotCancelable)
    var solution = // get IVsSolution4
    int hr = ((IVsSolution4)solution).EnsureSolutionIsLoaded((uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    if (ErrorHandler.Succeeded(hr))
    {
        // 2. Re-run the query
        Query();
    }
    else
    {
        ShowErrorMessage();
    }
}
```

## <a name="api-changes"></a>Rozhraní API změny

### <a name="new-api"></a>Nové rozhraní API

IVsSolution7.IsSolutionLoadDeferred (out odložení bool)

Pokud vrátí hodnotu true aktuálním řešení byl načten v odložené režimu. Všimněte si, že pokud řešení byl původně načten odložené režimu, i když jsou všechny odložené projekty nakonec načíst v aktuální relaci (kvůli gesta explicitní uživatele nebo vynucené operacemi), tato vlastnost by stále vrátí hodnotu PRAVDA.

__VSPROPID7. VSPROPID_DeferredProjectCount

Vrátí počet projekty aktuálně v režimu odložené. Tato vlastnost bude mít hodnotu v rozsahu [0, VSPROPID_ProjectCount].

__VSHPROPID9. VSHPROPID_IsDeferred

Vrátí hodnotu true Pokud projekt hierarchie je ve stavu odloženého zatížení.

__VSENUMPROJFLAGS3 s hodnotami EPF_DEFERRED a EPF_NOTDEFERRED

Tyto příznaky se dá předat do [IVsSolution.GetProjectEnum()](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivssolution.getprojectenum.aspx) Iterujte přes projekty odložené a odložen.

### <a name="new-events"></a>Nové události

IVsSolutionEvents7.OnAfterLoadAllDeferredProjects()

Tato událost se vyvolá po všech odložených projekty byly načteny. V tomto okamžiku VSPROPID_DeferredProjectCount je rovna 0. Všimněte si, že je tato událost vyvolána jako součást řešení zatížení a nemusí vůbec vydána v relaci. Jenom je aktivována, pokud se načtou všechny odložené projekty.

### <a name="changes-to-existing-api"></a>Změny existujícího rozhraní API

* Předávání [__VSENUMPROJFLAGS](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vsenumprojflags.aspx). EPF_LOADEDINSOLUTION k [IVsSolution.GetProjectEnum()](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivssolution.getprojectenum.aspx) vrátí odložení projekty.
* Předávání [__VSENUMPROJFLAGS](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vsenumprojflags.aspx). EPF_UNLOADEDINSOLUTION nevrací odložené projekty.
* [KnownUIContexts.SolutionExistsAndFullyLoadedContext](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.knownuicontexts.solutionexistsandfullyloadedcontext.aspx) je nastaven na hodnotu true v řešení otevřete. Odložené projekty jsou považovány za načíst, takže tento kontext se nastavuje hodně starší než v režimu dolní limit.
* [__VSPROPID](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vspropid.aspx). VSPROPID_ProjectCount vrátí součet načíst a odložené projekty.

## <a name="helpful-code-snippets"></a>Fragmenty kódu užitečné

### <a name="check-if-a-solution-was-opened-in-deferred-load-mode"></a>Zkontrolujte, pokud byl řešení otevřeného v režimu odložené zatížení

```csharp
/// <summary>
/// Checks if the solution was opened in LSL mode.
/// </summary>
/// <returns>True if the solution was opened in LSL mode, false otherwise.</returns> public static bool IsSolutionLoadDeferred()
{
    IVsSolution7 vsSolution = ServiceProvider.GlobalProvider.GetService(typeof(SVsSolution)) as IVsSolution7;
    Assumes.Present(vsSolution);

    return vsSolution.IsSolutionLoadDeferred();
}
```

### <a name="check-if-a-project-is-deferred"></a>Zkontrolujte, pokud je odložení projektu

```csharp
/// <summary>
/// Checks to see if a project is deferred.
/// </summary>
/// <param name="projectsToLoad">A set of deferred and/or loaded projects to ensure are loaded.</param>
/// <returns>True if the project is deferred. False if it is any other state, such as loaded, unloaded, or virtual.</returns>
/// <remarks>Requires Microsoft.VisualStudio.Shell.Interop.15.0.DesignTime.dll</remarks>
public static bool IsInDeferredState(IVsHierarchy vsHierarchy)
{
    object deferred;
    int hr = vsHierarchy.GetProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID9.VSHPROPID_IsDeferred, out deferred);

    if (ErrorHandler.Succeeded(hr))
    {
        return (bool)deferred;
    }

    return false;
}
```

### <a name="load-a-project"></a>Načtení projektu

```csharp
/// <summary>
/// Ensures a project is fully loaded.
/// </summary> /// <param name="projectToLoad">A deferred or loaded project to ensure is loaded.</param>
/// <remarks>Requires Microsoft.VisualStudio.Shell.15.0.dll and Microsoft.VisualStudio.Shell.Interop.dll</remarks>
public static IVsHierarchy EnsureProjectIsLoadedHelper(IVsHierarchy projectToLoad)
{
    int hr = VSConstants.S_OK;
    var solution = // get the solution

    // 1. Ask the solution to load the required project. To reduce wait time,
    //    we load only the project we need, not the entire solution.
    hr = projectToLoad.GetGuidProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_ProjectIDGuid, out projectGuid);
    hr = ErrorHandler.ThrowOnFailure(hr);
    hr = ((IVsSolution4)solution).EnsureProjectIsLoaded(projectGuid, (uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    hr = ErrorHandler.ThrowOnFailure(hr);

    // 2. After the project is loaded, grab the latest IVsHierarchy object.
    IVsHierarchy loadedProject = null;
    hr = ((IVsSolution)solution).GetProjectOfGuid(projectGuid, out loadedProject);
    hr = ErrorHandler.ThrowOnFailure(hr);

    return loadedProject;
}
```

### <a name="load-a-set-of-projects"></a>Načíst sadu projektů

```csharp
/// <summary>
/// Ensures a collection of IVsHierarchys are loaded. To be used when deferred projects absolutely cannot be used.
/// </summary>
/// <param name="projectsToLoad">A set of deferred and/or loaded projects to ensure are loaded.</param>
/// <remarks>Requires Microsoft.VisualStudio.Shell.15.0.dll and Microsoft.VisualStudio.Shell.Interop.dll</remarks>
public static IReadOnlyCollection<IVsHierarchy> EnsureProjectsAreLoadedHelper(IReadOnlyCollection<IVsHierarchy> projectsToLoad)
{
    if (projectsToLoad == null || projectsToLoad.Count == 0)
        return projectsToLoad;

    int hr = VSConstants.S_OK;
    List<Guid> projectGuids = new List<Guid>(projectsToLoad.Count);
    List<IVsHierarchy> loadedProjects = new List<IVsHierarchy>(projectsToLoad.Count);
    var solution = // get the solution

    // 1. Collect projects to force load
    foreach (var project in projectsToLoad)
    {
        Guid projectGuid;
        hr = project.GetGuidProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_ProjectIDGuid, out projectGuid)
        hr = ErrorHandler.ThrowOnFailure(hr);
        projectGuids.Add(projectGuid);
    }

    // 2. Ask the solution to load the required projects. To reduce wait time,
    //    we load only the projects we need, not the entire solution.
    hr = ((IVsSolution4)solution).EnsureProjectsAreLoaded(projectCount, projectGuids.ToArray(), (uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    hr = ErrorHandler.ThrowOnFailure(hr);

    // 3. After the projects are loaded, grab the latest IVsHierarchy objects
    foreach (var projectGuid in projectGuids)
    {
        IVsHierarchy loadedProject = null;
        hr = ((IVsSolution)solution).GetProjectOfGuid(projectGuid, out loadedProject);
        hr = ErrorHandler.ThrowOnFailure(hr);
        loadedProjects.Add(loadedProject);
    }

    return loadedProjects;
}
```

### <a name="checks-if-the-solution-has-deferred-projects"></a>Kontroluje, pokud má řešení odložení projekty

```csharp
/// <summary>
/// Checks if the solution has deferred projects
/// </summary>
/// <returns>True if the solution has deferred projects, false otherwise.</returns>
public static bool SolutionHasDeferredProjects()
{
    IVsSolution vsSolution = ServiceProvider.GlobalProvider.GetService(typeof(SVsSolution)) as IVsSolution;
    Assumes.Present(vsSolution);
    object varHasDeferredProjects;
    if (ErrorHandler.Succeeded(vsSolution.GetProperty(
        (int)__VSPROPID7.VSPROPID_DeferredProjectCount, out varHasDeferredProjects)))
    {
        return (int)varHasDeferredProjects != 0;
    }

    return false;
}
```

## <a name="getting-detailed-information-with-workspace-apis"></a>Získávání podrobné informace a rozhraní API pracovního prostoru

### <a name="how-to-get-detailed-info-on-a-lsl-solution"></a>Jak získat podrobné informace o řešení dolní limit

Nová rozhraní API pracovního prostoru jsou zveřejňovány prostřednictvím IVsSolutionWorkspaceService pomohou získat podrobné informace o řešení.

Tato rozhraní API můžete použít k získání aktuální pracovní prostor, aktivním řešení, informace o spravovaných příkazového řádku, jakož i službu index pro pracovní prostor. Tato rozhraní API můžete využít další službu indexu a získat podrobná data, například všechny zdrojové soubory v projektu vlastnícím projektu zdrojového souboru, všechny projekty obsažené v aktuálním řešení, všechny P2P odkazů v projektu atd.

Následující fragmenty kódu ukazují použití rozhraní API pracovního prostoru.

### <a name="get-ivssolutionworkspaceservice-initially"></a>Nejdřív získat IVsSolutionWorkspaceService

>**Poznámka:** prosím pouze získat IVsSolutionWorkspaceService ve scénářích dolní limit předejít přetížení balíček rozhraní API pracovního prostoru.

```csharp
private readonly Lazy<IVsSolutionWorkspaceService> _solutionWorkspaceService;

[ImportingConstructor]
public DeferredProjectWorkspaceService(SVsServiceProvider serviceProvider)
{
    _solutionWorkspaceService = new Lazy<IVsSolutionWorkspaceService>(
        () => (IVsSolutionWorkspaceService)serviceProvider.GetService(typeof(SVsSolutionWorkspaceService)));
}
```

>**Poznámka:** následující fragmenty kódu předpokládá _solutionWorkspaceService líné již je inicializován.

### <a name="get-managed-command-line-info-for-deferred-projects-for-active-solution-configuration"></a>Získání informací o spravovaných příkazového řádku pro odložené projekty v aktivním řešení konfigurace

```csharp
/// <summary>
/// Get the managed command line info for active solution configuration
/// </summary>
/// <param name="cancellationToken"> the cancellation token</param>
/// <returns></returns>
public async Task<IReadOnlyDictionary<string, ManagedCommandLineInfo>> GetManagedCommandLineInfoForConfigurationAsyn(CancellationToken cancellationToken)
{
    var dte = ServiceProvider.GetGlobalService(typeof(EnvDTE.DTE)) as EnvDTE.DTE;
    var solutionConfig = (EnvDTE80.SolutionConfiguration2)dte.Solution.SolutionBuild.ActiveConfiguration;

    // Solution configuration is something like "Debug|Any CPU"
    return await _solutionWorkspaceService.Value.GetManagedCommandLineInfoAsync(
        $"{solutionConfig.Name}|{solutionConfig.PlatformName}", cancellationToken).ConfigureAwait(false);
}
```

### <a name="get-the-active-solution-file-in-lsl"></a>Získat soubor active řešení v dolní limit

```csharp
/// <summary>
/// Get the active solution file.
/// </summary>
/// <returns>The solution file.</returns>
public string GetActiveSolutionFile()
{
    return _solutionWorkspaceService.Value.SolutionFile;
}
```

### <a name="get-the-owning-project-of-a-source-file"></a>Získat vlastnícím projektu zdrojového souboru

```csharp
/// <summary>
/// Get the owning projects of a source file.
/// </summary>
/// <param name="filePath">the source file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetOwningProjectAsync(string filePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var result = await indexService.GetFileDependantsAsync(filePath, null, String.Empty, (int)FileReferenceInfoType.Source);
    return result.Select(f => f.Path);
}
```

### <a name="get-all-source-files-from-a-project"></a>Získat všechny zdrojové soubory z projektu

```csharp
/// <summary>
/// Get all source files from a project.
/// </summary>
/// <param name="projectFilePath">the project file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetFileReferenceAsync(string projectFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var fileReferenceResult = await indexService.GetFileReferencesAsync(projectFilePath, referenceTypes: (int)FileReferenceInfoType.Source);
    return fileReferenceResult.Select(f => f.Path);
}
```

### <a name="get-the-p2p-references-in-a-project"></a>Získat odkazy P2P v projektu

```csharp
/// <summary>
/// Get outputs of project.
/// </summary>
/// <param name="projectFilePath">the project file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetFileReferenceAsync(string projectFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var fileReferenceResult = await indexService.GetFileReferencesAsync(projectFilePath, context: "Debug|AnyCPU", referenceTypes: (int)FileReferenceInfoType.Output);
    return fileReferenceResult.Select(f => f.Path);
}
```

### <a name="get-all-the-projects-in-a-solution"></a>Získat všechny projekty v řešení

```csharp
/// <summary>
/// Get the projects in a solution.
/// </summary>
/// <param name="solutionFilePath">the solution file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetProjectsInSolutionAsync(string solutionFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();

    // Passing the configuration|Platform that projects apply to; passing null will return projects with all configurations.
    var result = await indexService.GetFileReferencesAsync(solutionFilePath, context: "Debug|AnyCPU", referenceTypes: (int)FileReferenceInfoType.ProjectReference);
    return result.Select(f => f.Path);
}
```

## <a name="troubleshooting"></a>Poradce při potížích

Vzhledem k povaze dolní limit je úmyslné, že uživatelé neuvidí rozdíl mezi načíst a odložené projekty. To může ztížit funkce vývoje a testování.

Pomocí následujícího postupu můžete povolit visual pomocné parametry v uživatelském rozhraní pro odložené projekty:

1. Zavřete Visual Studio.
2. Regedit.exe
3. Vyberte HKLM
4. Soubor > načíst Hive
5. `%localappdata%\microsoft\visualstudio\15.0_<instance ID>\privateregistry.bin`
6. Zadejte "Visual Studio" jako název klíče
7. Nastavit `HKLM\VisualStudio\Software\Microsoft\VisualStudio\15.0_<instanceID>\FeatureFlags\Solution\Loading\Deferred\Hint\Value=1` (DWORD)
8. Vyberte HKLM\VisualStudio
9. Soubor > podregistr
10. Spuštění sady Visual Studio

Pro všechny další otázky, prosím oslovení [ lslsupport@microsoft.com ](mailto:lslsupport@microsoft.com).






