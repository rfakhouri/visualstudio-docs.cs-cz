---
title: Pracovní prostory v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3489592a-dc0c-4cd3-9b08-cd367626980a
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 0230201677fd2422817ca1fbeab6679a424e5c05
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31145968"
---
# <a name="workspaces"></a>Pracovní prostory

Pracovní prostor je, jak Visual Studio představuje všechny kolekce souborů z [otevřít složku](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md), a je zobrazena <xref:Microsoft.VisualStudio.Workspace.IWorkspace> typu. Samostatně pracovním prostoru nerozumí obsah nebo funkce související se soubory ve složce. Místo toho poskytuje obecné sadu rozhraní API pro funkce a rozšíření vytvářet a využívat data, která ostatní mohly pracovat. Producenti se skládají prostřednictvím [spravované rozhraní rozšiřitelnosti](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (MEF) pomocí různých exportovat atributy.

## <a name="workspace-providers-and-services"></a>Zprostředkovatelé prostoru a služby

Zprostředkovatelé prostoru a služby poskytují data a funkce reagování na obsah pracovního prostoru. Se může poskytnout informace kontextové souboru, symboly ve zdrojových souborech nebo sestavení funkce.

Použít obě koncepty [vzor objektu pro vytváření](https://en.wikipedia.org/wiki/Factory_method_pattern) a importují prostřednictvím MEF v pracovním prostoru. Všechny atributy export implementovat `IProviderMetadataBase` nebo `IWorkspaceServiceFactoryMetadata`, ale existují konkrétní typy, které rozšíření by měl použít pro exportovaný typy.

Jeden rozdíl mezi poskytovatelů služeb je jejich relace do pracovního prostoru. Pracovní prostor může mít mnoho poskytovatelů určitého typu, ale pouze jedna služba určitého typu se vytvoří na pracovní prostor. Například pracovního prostoru nemá mnoho poskytovatelů skener soubor ale pracovním prostoru má jenom jeden indexování služby za pracovního prostoru.

Jiné klíčovým rozdílem je spotřeby dat od poskytovatelů a služby. V pracovním prostoru se vstupním bodem k získání dat od poskytovatelů, pro několik důvodů. Nejprve Zprostředkovatelé obvykle mají některé úzké sadu dat, které vytvoří. Může být symboly pro zdrojový soubor C# nebo sestavení kontexty souboru pro data _CMakeLists.txt_ souboru. V pracovním prostoru bude odpovídat příjemce požadavek na poskytovateli, jejichž metadata zarovnat s požadavkem. Druhý, některé scénáře povolit pro mnoho poskytovatelů přispívat k požadavku, zatímco jiné scénáře použití zprostředkovatele s nejvyšší prioritou.

Naproti tomu rozšíření můžete získat instancí a komunikovat přímo s prostoru služby. Rozšiřující metody na `IWorkspace` jsou k dispozici pro služby poskytované sadě Visual Studio, jako například <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetFileWatcherService%2A>. Rozšíření může nabídnout pracovní prostor služby pro součásti v rámci rozšíření nebo pro ostatní rozšíření používat. Příjemce by měl použít <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetServiceAsync%2A> nebo metody rozšíření poskytují na `IWorkspace` typu.

>[!WARNING]
> Není vytvářet služby, které je v konfliktu s Visual Studio. Ho může vést k neočekávaným problémům.

## <a name="disposal-on-workspace-closure"></a>Uvolnění na uzavření pracovního prostoru

Na uzavření pracovního prostoru, může být nutné Extender dispose ale volání asynchronní kódu. <xref:Microsoft.VisualStudio.Threading.IAsyncDisposable> Rozhraní je psaní tento kód snadno dostupné.

## <a name="related-types"></a>Souvisejících typů

- <xref:Microsoft.VisualStudio.Workspace.IWorkspace> je centrální pro pracovní prostor služby otevřenou jako otevřenou složku.
- <xref:Microsoft.VisualStudio.Workspace.IWorkspaceProviderFactory`1> vytvoří zprostředkovatele na instanci pracovního prostoru.
- <xref:Microsoft.VisualStudio.Workspace.IWorkspaceServiceFactory> Vytvoří službu na instanci pracovního prostoru.
- <xref:Microsoft.VisualStudio.Threading.IAsyncDisposable> by měla být implementována na poskytovatelů a službách, které je potřeba spustit asynchronní kód při uvolnění.
- <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper> Poskytuje pomocné metody pro přístup k dobře známým službám nebo libovolný službám.

## <a name="workspace-settings"></a>Nastavení pracovního prostoru

Máte pracovní prostory <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager> služby s jednoduchou, ale výkonnou kontrolu nad pracovním prostoru. Základní přehled nastavení, najdete v tématu [přizpůsobení sestavení a ladění úloh](../ide/customize-build-and-debug-tasks-in-visual-studio.md).

Nastavení pro většinu `SettingsType` typy jsou _.json_ souborů, jako například _VSWorkspaceSettings.json_ a _tasks.vs.json_.

Možnosti nastavení pracovního prostoru se soustředí kolem "obory", které jsou jednoduše cesty v pracovním prostoru. Když příjemce volá <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager.GetAggregatedSettings%2A>, jsou všechny obory, které zahrnují požadovanou cestu a zadejte nastavení agregovat. Priorita agregace obor je následující:

1. "Místní nastavení", která je obvykle kořenu prostoru `.vs` adresáře.
1. Požadovanou cestu sám sebe.
1. Nadřazeném adresáři požadovanou cestu.
1. Všechny další nadřazených adresářů do a včetně kořenové pracovního prostoru.
1. "Globální nastavení", která je v adresáři uživatele.

Výsledkem je instance <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings>. Tento objekt obsahuje nastavení pro konkrétní typ a můžete zadat dotaz na nastavení názvy klíčů uložené jako `string`. <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings.GetProperty%2A> Metody a <xref:Microsoft.VisualStudio.Workspace.Settings.WorkspaceSettingsExtensions> rozšiřující metody očekávat volajícího, aby znát typ požadovanou hodnotu nastavení. Protože většina souborů nastavení jsou nastavené jako trvalé jako _.json_ soubory, budou používat mnoho volání `string`, `bool`, `int`a pole těchto typů. Typy objektů jsou také podporovány. V takových případech můžete použít `IWorkspaceSettings` sám sebe jako argument typu. Příklad:

```json
{
  "intValue": 1,
  "stringValue": "s",
  "boolValue": true,
  "stringArray": [
    "s1",
    "s2"
  ],
  "nestedIWorkspaceSettings": {
    "nestedString": "ns"
  }
}
```

Za předpokladu, že tato nastavení se uživatele _VSWorkspaceSettings.json_, jako je přístupná data:

```csharp
using System.Collections.Generic;
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Settings;

private static void ReadSettings(IWorkspace workspace)
{
    IWorkspaceSettingsManager settingsManager = workspace.GetSettingsManager();
    IWorkspaceSettings settings = settingsManager.GetAggregatedSettings(SettingsTypes.Generic);

    // result == WorkspaceSettingsResult.Success
    WorkspaceSettingsResult result = settings.GetProperty("intValue", out int intValue);
    result = settings.GetProperty("stringValue", out string stringValue);
    result = settings.GetProperty("boolValue", out bool boolValue);
    result = settings.GetProperty("stringArray", out string[] stringArray);
    result = settings.GetProperty("nestedIWorkspaceSettings", out IWorkspaceSettings nestedIWorkspaceSettings);
    result = nestedIWorkspaceSettings.GetProperty("nestedString", out string nestedString);

    // Extension method alternative using default values.
    int intValueOrDefault = settings.Property("intValue", /* default */ 42);

    // Missing key. result == WorkspaceSettingsResult.Undefined
    result = settings.GetProperty("missing", out string missing);

    // Wrong type for a key. result == WorkspaceSettingsResult.Error
    result = settings.GetProperty("intValue", out IWorkspaceSettings notSettings);

    // Special ability to union "stringArray" across all scopes.
    IEnumerable<string> allStringArray = settings.UnionPropertyArray<string>("stringArray");
}
```

>[!NOTE]
>Tato nastavení rozhraní API se nevztahují na rozhraní API dostupná v `Microsoft.VisualStudio.Settings` oboru názvů. Nastavení pracovního prostoru jsou lhostejné hostitele a používat soubory specifické pro pracovní prostor nastavení nebo zprostředkovatele dynamické nastavení.

### <a name="providing-dynamic-settings"></a>Poskytuje dynamické nastavení

Rozšíření můžete zadat <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsProvider>s. Tyto zprostředkovatele v paměti umožňuje rozšíření přidání nastavení nebo jiné přepsání.

Export `IWorkspaceSettingsProvider` se liší od jiných poskytovatelů pracovního prostoru. Objekt factory není `IWorkspaceProviderFactory` a neexistuje žádný typ speciální atribut. Místo toho implementovat <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsProviderFactory> a používat `[Export(typeof(IWorkspaceSettingsProviderFactory))]`.

```csharp
// Common workspace provider factory pattern
[ExportFeatureProvider(some, args, to, export)]
internal class MyProviderFactory : IWorkspaceProviderFactory<IFeatureProvider>
{
     IFeatureProvider CreateProvider(IWorkspace workspace) => new Provider(workspace);
}

// IWorkspaceSettingsProvider pattern
[Export(typeof(IWorkspaceSettingsProviderFactory))]
internal class MySettingsProviderFactory : IWorkspaceSettingsProviderFactory
{
    // 100 is typically the value used by built-in settings providers. Lower value is higher priority.
    int Priority => 100;

    IWorkspaceSettingsProvider CreateSettingsProvider(IWorkspace workspace) => new MySettingsProvider(workspace);
}
```

>[!TIP]
>Při implementaci metody, které vracejí `IWorkspaceSettingsSource` (jako je `IWorkspaceSettingsProvider.GetSingleSettings`), vrátí instanci `IWorkspaceSettings` místo `IWorkspaceSettingsSource`. `IWorkspaceSettings` poskytuje další informace, které mohou být užitečné při některých nastavení agregace.

### <a name="settings-related-apis"></a>Nastavení rozhraní API související s

- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager> čtení a agreguje nastavení pracovního prostoru.
- <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetSettingsManager%2A> Získá `IWorkspaceSettingsManager` pro pracovní prostor.
- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager.GetAggregatedSettings%2A> Získá nastavení pro daný obor agregovat přes všechny překrývající se rozsahy.
- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings> obsahuje nastavení pro konkrétní obor.

## <a name="workspace-suggested-practices"></a>Pracovní prostor navrhované postupy

- Vrací objekty z `IWorkspaceProviderFactory.CreateProvider` podobné rozhraní API, která mějte na paměti, nebo jejich `Workspace` kontext při vytvoření. Zprostředkovatelé rozhraní jsou zapsány očekává, že tento objekt se ukládají na vytvoření.
- Uložte nastavení v této cestě "Místní nastavení" pracovního prostoru nebo konkrétní pracovní prostor mezipaměti. Vytvoření cesty k souboru pomocí `Microsoft.VisualStudio.Workspace.WorkspaceHelper.MakeRootedUnderWorkingFolder` ve Visual Studio 2017 verze 15.6 nebo novější. Verze starší než verze 15,6 operací použijte následující fragment kódu:

```csharp
using System.IO;
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Settings;

private static string MakeRootedUnderWorkingFolder(IWorkspace workspace, string relativePath)
{
    string workingFolder = workspace.GetSettingsManager().GetAggregatedSettings(SettingsTypes.WorkspaceControlSettings).Property<string>("WorkingFolder");
    return Path.Combine(workingFolder, relativePath);
}
```

## <a name="solution-events-and-package-auto-load"></a>Řešení události a automaticky načíst balíček

Načíst balíčky můžete implementovat `IVsSolutionEvents7` a vyvolání `IVsSolution.AdviseSolutionEvents`. Obsahuje eventing na otvírání a zavírání složku v sadě Visual Studio.

Kontext uživatelského rozhraní lze automaticky načíst vašeho balíčku. Hodnota je `4646B819-1AE0-4E79-97F4-8A8176FDD664`.

## <a name="troubleshooting"></a>Poradce při potížích

### <a name="the-sourceexplorerpackage-package-did-not-load-correctly"></a>Balíček SourceExplorerPackage nebyl správně načten

Rozšiřitelnost pracovního prostoru je výraznou na základě MEF a způsobí, že chyby složení hostování otevřít složku selhání načtení balíčku. Například, pokud rozšíření exportuje typu s `ExportFileContextProviderAttribute`, ale typ pouze implementuje `IWorkspaceProviderFactory<IFileContextActionProvider>`, dojde k chybě při pokusu o otevření složky v sadě Visual Studio. Podrobnosti o chybě naleznete v _%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_id\ComponentModelCache\Microsoft.VisualStudio.Default.err_. Vyřešte všechny chyby pro typy implementované rozšíření.

## <a name="next-steps"></a>Další kroky

* [Soubor kontexty](workspace-file-contexts.md) -soubor kontextu zprostředkovatelé přineste intelligence kód pro pracovní prostory otevřít složku. 
* [Indexování](workspace-indexing.md) -prostoru indexování shromažďuje a udržuje informace o pracovní prostor.
