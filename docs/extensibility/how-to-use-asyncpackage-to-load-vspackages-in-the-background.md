---
title: 'Postupy: Použití AsyncPackage k načtení rozšíření VSPackages na pozadí | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: dedf0173-197e-4258-ae5a-807eb3abc952
author: madskristensen
ms.author: madsk
ms.workload:
- vssdk
ms.openlocfilehash: 64514a6d43d580fbda142dfa65bb3a2d384dff4e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324781"
---
# <a name="how-to-use-asyncpackage-to-load-vspackages-in-the-background"></a>Postupy: Použití AsyncPackage k načtení rozšíření VSPackages na pozadí
V / v disku může způsobit načtením a inicializací balíček VS. V případě takových vstupně-výstupních operací na vlákno uživatelského rozhraní může vést k problémů s rychlostí odezvy. Z toho Visual Studio 2015 zavedené <xref:Microsoft.VisualStudio.Shell.AsyncPackage> třídu, která umožňuje načítání balíčku na vlákně na pozadí.

## <a name="create-an-asyncpackage"></a>Vytvoření AsyncPackage
 Můžete začít tak, že vytvoříte projekt VSIX (**souboru** > **nový** > **projektu** > **Visual C#**   >  **Rozšiřitelnost** > **projekt VSIX**) a VSPackage přidáním do projektu (klikněte pravým tlačítkem na projekt a **přidat**  >  **Nová položka**  >   **C# položky** > **rozšiřitelnost**  >   **Balíček sady Visual Studio**). Můžete vytvořit vaše služby a přidejte tyto služby do vašeho balíčku.

1. Odvození balíček z <xref:Microsoft.VisualStudio.Shell.AsyncPackage>.

2. Pokud poskytujete služby, jejichž dotazování může způsobit, že váš balíček se načíst:

    K označení k sadě Visual Studio, váš balíček je bezpečný pro načítání na pozadí a pro přidání do tohoto chování vašeho <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> měli nastavit **AllowsBackgroundLoading** vlastnost na hodnotu true v konstruktoru atributu.

   ```csharp
   [PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]

   ```

    K označení k sadě Visual Studio, je bezpečný pro vytvoření instance služby na vlákně na pozadí, byste měli nastavit <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttributeBase.IsAsyncQueryable%2A> vlastnost na hodnotu true <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> konstruktoru.

   ```csharp
   [ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]

   ```

3. Pokud se načítají prostřednictvím uživatelského rozhraní kontextů, pak byste měli zadat **PackageAutoLoadFlags.BackgroundLoad** pro <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> nebo hodnoty (0x2) do příznaky zapsat jako hodnotu položky automaticky načíst vašeho balíčku.

   ```csharp
   [ProvideAutoLoad(UIContextGuid, PackageAutoLoadFlags.BackgroundLoad)]

   ```

4. Pokud máte inicializace asynchronní práce, kterou byste měli přepsat <xref:Microsoft.VisualStudio.Shell.AsyncPackage.InitializeAsync%2A>. Odeberte `Initialize()` metodu poskytovanou šablonou VSIX. ( `Initialize()` Metoda **AsyncPackage** je zapečetěná). Můžete použít některý z <xref:Microsoft.VisualStudio.Shell.AsyncPackage.AddService%2A> metody pro přidání asynchronní služby do vašeho balíčku.

    POZNÁMKA: Chcete-li volat `base.InitializeAsync()`, můžete změnit zdrojový kód:

   ```csharp
   await base.InitializeAsync(cancellationToken, progress);
   ```

5. Je musíte pečlivě NEDOVOLTE, aby byly RPC (vzdálené volání procedur) z asynchronní inicializační kód (v **InitializeAsync**). Těm dochází při volání <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> přímo nebo nepřímo.  Při načítání synchronizace jsou požadovány, bude blokovat vlákno uživatelského rozhraní pomocí <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory>. Výchozí model blokování zakáže Vzdálená volání procedur. To znamená, že při pokusu o použití vzdáleného volání Procedur z vašich úloh s modifikátorem async, můžete se zablokování Pokud vlákno uživatelského rozhraní samotného čekání na váš balíček se načíst. Obecné alternativou je zařadit váš kód na vlákno uživatelského rozhraní v případě potřeby pomocí příkazu podobného tomuto **spojitelné továrny úloh**společnosti <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> nebo jiný mechanismus, který nepoužívá vzdáleného volání Procedur.  Nepoužívejte **ThreadHelper.Generic.Invoke** nebo obecně blokovat volající vlákno čeká na vlákně UI.

    POZNÁMKA: Měli byste se vyhnout použití **GetService** nebo **služby QueryService** v vaše `InitializeAsync` metody. Pokud máte použít, musíte nejprve přepnout na vlákno uživatelského rozhraní. Alternativou je použití <xref:Microsoft.VisualStudio.Shell.AsyncServiceProvider.GetServiceAsync%2A> z vaší **AsyncPackage** (pomocí přetypování na <xref:Microsoft.VisualStudio.Shell.Interop.IAsyncServiceProvider>.)

   C#: Vytvoření AsyncPackage:

```csharp
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]
[ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]
public sealed class TestPackage : AsyncPackage
{
    protected override Task InitializeAsync(System.Threading.CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)
    {
        this.AddService(typeof(SMyTestService), CreateService, true);
        return Task.FromResult<object>(null);
    }
}
```

## <a name="convert-an-existing-vspackage-to-asyncpackage"></a>Převod existujícího balíčku VSPackage AsyncPackage
 Většina práce je stejné jako vytvoření nového **AsyncPackage**. Postupujte podle kroků 1 až 5 výše. Také je potřeba provést další upozornění s následující doporučení:

1. Nezapomeňte odebrat `Initialize` přepsání, které jste měli v balíčku.

2. Zabránilo zablokování: To může být skrytá RPC ve vašem kódu. které teď provádělo na vlákně na pozadí. Ujistěte se, že pokud provádíte vzdáleného volání Procedur (například **GetService**), budete muset buď (1) přepněte na hlavním vlákně, nebo (2), použijte asynchronní verze rozhraní API, pokud existuje (například **GetServiceAsync**).

3. Přepnutí mezi vlákny příliš často. Došlo k pokusu o lokalizaci práci, kterou může dojít ve vlákně na pozadí zkrátit čas zatížení.

## <a name="querying-services-from-asyncpackage"></a>Dotazování služby z AsyncPackage
 **AsyncPackage** může nebo nemusí načíst asynchronně v závislosti na volajícího. Pro instanci

- Pokud volající volána **GetService** nebo **služby QueryService** (oběma synchronního rozhraní API) nebo

- Pokud volající volána **IVsShell::LoadPackage** (nebo **IVsShell5::LoadPackageWithContext**) nebo

- Zatížení se aktivuje při kontextu uživatelského rozhraní, ale nezadali jste, že mechanismus kontextu uživatelského rozhraní můžete načíst můžete asynchronně

  váš balíček se potom načte synchronně.

  Váš balíček má stále příležitost (ve fázi asynchronní inicializace) k práci mimo vlákno uživatelského rozhraní, ale pro dokončení, které pracují se zablokuje vlákno uživatelského rozhraní. Pokud volající používá **IAsyncServiceProvider** asynchronně dotazu pro vaši službu, pak zatížení a inicializace se provede asynchronně za předpokladu, že nemusíte okamžitě zablokovat výsledného objektu task.

  C#: Jak provádět dotazy služby asynchronně:

```csharp
using Microsoft.VisualStudio.Shell;
using Microsoft.VisualStudio.Shell.Interop;

IAsyncServiceProvider asyncServiceProvider = Package.GetService(typeof(SAsyncServiceProvider)) as IAsyncServiceProvider;
IMyTestService testService = await asyncServiceProvider.GetServiceAsync(typeof(SMyTestService)) as IMyTestService;
```
