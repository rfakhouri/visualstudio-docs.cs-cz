---
title: "Postupy: načtení VSPackages na pozadí pomocí AsyncPackage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dedf0173-197e-4258-ae5a-807eb3abc952
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
ms.openlocfilehash: 8adc348553ba613898117f10ccd21a6e5cd02ab8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-asyncpackage-to-load-vspackages-in-the-background"></a>Postupy: použití AsyncPackage načíst VSPackages na pozadí
V/v diskových operací může způsobit načtením a inicializací balíčku VS. V případě takové vstupně-výstupních operací na vlákno uživatelského rozhraní může vést k problémům odezvy. Chcete-li to vyřešit, Visual Studio 2015 zavedená <xref:Microsoft.VisualStudio.Shell.AsyncPackage> třídu, která umožňuje načítání balíčku na vlákna na pozadí.  
  
## <a name="creating-an-asyncpackage"></a>Vytvoření AsyncPackage  
 Můžete spustit vytvořením projektu VSIX (**souboru / New / Project / Visual C# nebo rozšíření nebo VSIX projektu**) a přidávání VSPackage k projektu (klikněte pravým tlačítkem na projekt a **položku Přidat/nový / C# položky nebo rozšíření nebo Visual Balíček Studio**). Pak můžete vytvořit vaše služby a přidejte tyto služby do vašeho balíčku.  
  
1.  Odvození balíček <xref:Microsoft.VisualStudio.Shell.AsyncPackage>.  
  
2.  Pokud se poskytování služeb, jejíž dotazování může způsobit, že váš balíček načíst:  
  
     Chcete-li sady Visual Studio upozornit, že váš balíček je bezpečný pro načítání pozadí a který se přidá do toto chování vaší <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> měli nastavit **AllowsBackgroundLoading** vlastnost na hodnotu true v konstruktoru atributu.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]  
  
    ```  
  
     Chcete-li sady Visual Studio upozornit, že je bezpečné pro vytvoření instance služby v vlákna na pozadí, byste měli nastavit <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttributeBase.IsAsyncQueryable%2A> vlastnost na hodnotu true v <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> konstruktor.  
  
    ```csharp  
    [ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]  
  
    ```  
  
3.  Pokud jsou načítání prostřednictvím uživatelského rozhraní kontexty, pak byste měli zadat **PackageAutoLoadFlags.BackgroundLoad** pro <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> nebo zapsat hodnotu (0x2) do příznaků jako hodnotu položky automaticky načíst vašeho balíčku.  
  
    ```csharp  
    [ProvideAutoLoad(UIContextGuid, PackageAutoLoadFlags.BackgroundLoad)]  
  
    ```  
  
4.  Pokud máte pracovní asynchronní inicializace uděláte, by měly přepsat <xref:Microsoft.VisualStudio.Shell.AsyncPackage.InitializeAsync%2A>. Odeberte **inicializaci()** metoda poskytované VSIX šablony. ( **Inicializaci()** metoda v **AsyncPackage** je zapečetěná). Můžete použít některou z <xref:Microsoft.VisualStudio.Shell.AsyncPackage.AddService%2A> metody pro přidání asynchronní služby do vašeho balíčku.  
  
     Poznámka: K volání **základní. InitializeAsync()**, můžete změnit svůj zdrojový kód:  
  
    ```csharp  
    await base.InitializeAsync(cancellationToken, progress);  
    ```  
  
5.  Můžete pečlivě zajistěte, aby nebyly RPC (vzdálené volání procedur) z vašeho kódu asynchronní inicializace (v **InitializeAsync**). To může dojít, když zavoláte <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> přímo nebo nepřímo.  Při načítání synchronizace jsou požadovány, bude blokovat vlákna uživatelského rozhraní pomocí <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory>. Výchozí model blokování zakáže RPC. To znamená, že pokud se pokusíte použít vzdáleného volání Procedur z asynchronních úloh, můžete se zablokování Pokud vlákna uživatelského rozhraní samotného čekání na váš balíček načíst. Obecné alternativou je zařazování svůj kód vlákna uživatelského rozhraní v případě potřeby pomocí něčeho jako jazyk **spojitelného objekt pro vytváření úloh**na <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> nebo jiný mechanismus, který nepoužívá vzdáleného volání Procedur.  Nepoužívejte **ThreadHelper.Generic.Invoke** nebo obecně blokovat volající vlákno čeká na získání do vlákna uživatelského rozhraní.  
  
     Poznámka: Vyhněte se použití **metody GetService** nebo **služby QueryService** ve vaší **InitializeAsync** metoda. Pokud máte použít, musíte nejprve přepnout vlákna uživatelského rozhraní. Alternativou je použít <xref:Microsoft.VisualStudio.Shell.AsyncServiceProvider.GetServiceAsync%2A> z vaší **AsyncPackage** (podle jeho přetypování <xref:Microsoft.VisualStudio.Shell.Interop.IAsyncServiceProvider>.)  
  
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
  
## <a name="convert-an-existing-vspackage-to-asyncpackage"></a>Převést stávající VSPackage AsyncPackage  
 Většina práce je stejný jako vytvoření nové **AsyncPackage**. Je třeba postupovat podle kroků 1 až 5 výše. Také je třeba provést další upozornění na následujících:  
  
1.  Nezapomeňte odebrat **inicializovat** přepsání, které jste měli v balíčku.  
  
2.  Vyhněte se zablokování: může být skrytý RPC ve vašem kódu, který teď stát při vlákna na pozadí. Budete muset Ujistěte se, že pokud provádíte vzdáleného volání Procedur (například **metody GetService**), je třeba buď (1) přepněte do hlavního vlákna nebo (2) použijte asynchronní verzi rozhraní API, pokud existuje (například **GetServiceAsync**).  
  
3.  Není přepínat mezi vláken příliš často. Došlo k pokusu o lokalizaci práci, kterou může dojít ve vláknu na pozadí. Tím se snižuje čas zatížení.  
  
## <a name="querying-services-from-asyncpackage"></a>Dotazování služby od AsyncPackage  
 **AsyncPackage** může nebo nemusí v závislosti na volající asynchronně zatížení. Pro instanci,  
  
-   Pokud má volající volána **metody GetService** nebo **služby QueryService** (i synchronní rozhraní API) nebo  
  
-   Pokud má volající volána **IVsShell::LoadPackage** (nebo **IVsShell5::LoadPackageWithContext**) nebo  
  
-   Zatížení se aktivuje při kontextu uživatelského rozhraní, ale nebyl určen kontextu mechanismus uživatelského rozhraní můžete zátěže můžete asynchronně  
  
 potom vašeho balíčku načte synchronně.  
  
 Všimněte si, že vašeho balíčku má stále příležitost (ve fázi asynchronní inicializace) pro práci vypnout vlákna uživatelského rozhraní, i když se zablokuje vlákna uživatelského rozhraní pro dokončení této pracovní. Pokud má volající používá **IAsyncServiceProvider** asynchronně dotazu služby, potom zatížení a inicializace bude provedeno asynchronně za předpokladu, že nedošlo k blokování okamžitě na výsledný objekt úlohy.  
  
 C#: Jak dotazovat služby asynchronně:  
  
```csharp  
using Microsoft.VisualStudio.Shell;   
using Microsoft.VisualStudio.Shell.Interop;   
  
IAsyncServiceProvider asyncServiceProvider = Package.GetService(typeof(SAsyncServiceProvider)) as IAsyncServiceProvider;   
IMyTestService testService = await ayncServiceProvider.GetServiceAsync(typeof(SMyTestService)) as IMyTestService;  
```
  
