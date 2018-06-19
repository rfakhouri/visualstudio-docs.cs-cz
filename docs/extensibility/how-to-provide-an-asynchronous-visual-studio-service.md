---
title: 'Postupy: poskytování služby asynchronní Visual Studio | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0448274c-d3d2-4e12-9d11-8aca78a1f3f5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8741779cf96cb970f3ebc4907443b85ced5b80c0
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33705070"
---
# <a name="how-to-provide-an-asynchronous-visual-studio-service"></a>Postupy: poskytování služby asynchronní Visual Studio
Pokud chcete získat službu bez blokování vlákna uživatelského rozhraní, doporučujeme vytvoření služby asynchronní a načíst balíček na vlákna na pozadí. Pro tento účel můžete použít <xref:Microsoft.VisualStudio.Shell.AsyncPackage> ne <xref:Microsoft.VisualStudio.Shell.Package>a přidejte službu s asynchronní balíček speciální asynchronních metod.
  
 Informace o poskytování služeb synchronní Visual Studio najdete v tématu [postupy: poskytování služby](../extensibility/how-to-provide-a-service.md).  
  
## <a name="implementing-an-asynchronous-service"></a>Implementace asynchronní služby  
  
1.  Vytvoření projektu VSIX (**soubor > Nový > Projekt > Visual C# > Extensiblity > Projekt VSIX**). Název projektu **TestAsync**.  
  
2.  Do projektu přidejte VSPackage. Vyberte uzel projektu v **Průzkumníku řešení** a klikněte na tlačítko **Přidat > novou položku > Visual C# položky > Rozšíření > Balíček Visual Studio**. Název tohoto souboru **TestAsyncPackage.cs**.  
  
3.  V TestAsyncPackage.cs měnit balíček dědění z AsyncPackage spíše než balíčku:  
  
    ```csharp  
    public sealed class TestAsyncPackage : AsyncPackage  
    ```  
  
4.  K implementaci služby, musíte vytvořit tři typy:  
  
    -   Rozhraní, které identifikují službu. Mnoho z těchto rozhraní jsou prázdné, to znamená, že mají žádné metody i se používají jenom pro dotaz na službu.
  
    -   Rozhraní, které popisuje rozhraní služby. Toto rozhraní obsahuje metody k implementaci.  
  
    -   Třída, která implementuje rozhraní služby a služby.  
  
5.  Následující příklad ukazuje velmi základní implementaci všech tří typů. V konstruktoru třídy služeb, musíte nastavit poskytovatele služeb. V tomto příkladu právě přidáme službu k souboru balíčku kódu.  
  
6.  Přidejte následující příkazy using do souboru balíčku:  
  
    ```csharp  
    using System.Threading;  
    using System.Threading.Tasks;  
    using System.Runtime.CompilerServices;  
    using System.IO;
    using Microsoft.VisualStudio.Threading;
    using IAsyncServiceProvider = Microsoft.VisualStudio.Shell.IAsyncServiceProvider;
    using Task = System.Threading.Tasks.Task;
    ```  
  
7.  Zde je implementace asynchronní služby. Všimněte si, že je nutné nastavit na poskytovatele asynchronní služby spíše než poskytovateli synchronní služby v konstruktoru:  
  
    ```csharp
    public class TextWriterService : STextWriterService, ITextWriterService  
    {  
        private IAsyncServiceProvider asyncServiceProvider;  
        
        public TextWriterService(IAsyncServiceProvider provider)  
        {
            // constructor should only be used for simple initialization
            // any usage of Visual Studio service, expensive background operations should happen in the
            // asynchronous InitializeAsync method for best performance
            asyncServiceProvider = provider;  
        }
        
        public async Task InitializeAsync(CancellationToken cancellationToken)
        {
            await TaskScheduler.Default;
            // do background operations that involve IO or other async methods

            await this.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);               
            // query Visual Studio services on main thread unless they are documented as free threaded explicitly.
            // The reason for this is the final cast to service interface (such as IVsShell) may involve COM operations to add/release references.

            IVsShell vsShell = this.asyncServiceProvider.GetServiceAsync(typeof(SVsShell)) as IVsShell;
            // use Visual Studio services to continue initialization
        }
        
        public async Task WriteLineAsync(string path, string line)  
        {  
            StreamWriter writer = new StreamWriter(path);  
            await writer.WriteLineAsync(line);  
            writer.Close();  
        }  
    }  

    public interface STextWriterService  
    {  
    }  
    
    public interface ITextWriterService   
    {  
        System.Threading.Tasks.Task WriteLineAsync(string path, string line);  
    }  
    ```  
  
## <a name="registering-a-service"></a>Registrace služby  
 Chcete-li zaregistrovat službu, přidejte <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> k balíčku, který poskytuje službu. Různé registraci synchronní služby, je nutné zajistěte, aby balíček a služba podporuje asynchronní načítání:
  
-   Je nutné přidat **AllowsBackgroundLoading = true** do <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> pro zajištění balíčku můžete další informace o PackageRegistrationAttribute inicializují asynchronně, naleznete v [registrace a Zrušení registrace VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
-   Je nutné přidat **IsAsyncQueryable = true** do <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> zajistit instance služby můžete inicializují asynchronně.

 Tady je příklad AsyncPackage s registraci asynchronní služby:
  
```csharp  
[ProvideService((typeof(STextWriterService)), IsAsyncQueryable = true)]  
[ProvideAutoLoad(UIContextGuids80.SolutionExists, PackageAutoLoadFlags.BackgroundLoad)]  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]   
[Guid(TestAsyncPackage.PackageGuidString)]  
public sealed class TestAsyncPackage : AsyncPackage  
{. . . }  
```  
  
## <a name="adding-a-service"></a>Přidání služby  
  
1.  V TestAsyncPackage.cs, odebrat `Initialize()` metoda a přepsání `InitializeAsync()` metoda. Přidání služby a přidejte metody zpětného volání k vytvoření služby. Tady je příklad asynchronní inicializátoru přidání služby:  
  
    ```csharp
    protected override async Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);
    }  
  
    ```  
  
2.  Přidáte odkaz na Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll.  
  
3.  Metoda zpětného volání implementujte jako asynchronní metody, které vytváří a vrátí službu.  
  
    ```csharp  
    public async Task<object> CreateTextWriterService(IAsyncServiceContainer container, CancellationToken cancellationToken, Type serviceType)  
    {  
        TextWriterService service = new TextWriterService(this);  
        await service.InitializeAsync(cancellationToken);
        return service;
    }  
  
    ```  
  
## <a name="using-a-service"></a>Pomocí služby  
 Teď můžete získat službu a použít její metody.  
  
1.  Ukážeme to inicializátoru, ale můžete získat službu kdekoli chcete používat službu.  
  
    ```csharp  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);  
  
        ITextWriterService textService = await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await textService.WriteLineAsync(<userpath>), "this is a test");  
    }  
  
    ```  
  
     Nezapomeňte změnit  *\<userpath >* na název souboru a cesta, která dává smysl v počítači!  
  
2.  Sestavte a spusťte kód. Jakmile se zobrazí experimentální instanci sady Visual Studio, otevřete řešení. To způsobí, že AsyncPackage k autoload. Když se spustí inicializátoru, byste měli najít soubor v zadaném umístění.  
  
## <a name="using-an-asynchronous-service-in-a-command-handler"></a>Použití asynchronní služby v obslužná rutina příkazu  
 Tady je příklad toho, jak pomocí služby asynchronní v příkazu nabídky. Můžete použít postup používání služby v jiné-asynchronní metody tady uvedené.  
  
1.  Do projektu přidejte příkaz nabídky. (V **Průzkumníku řešení**, vyberte uzel projektu, klikněte pravým tlačítkem a vyberte **přidat / novou položku nebo rozšíření nebo postup pomocí příkazového vlastní**.) Název souboru příkaz **TestAsyncCommand.cs.**  
  
2.  Znovu přidá šablona vlastního příkazu `Initialize()` metoda k souboru TestAsyncPackage.cs za účelem inicializace příkaz. V metodě inicializaci() zkopírujte řádek, který inicializuje příkaz. Ho by měl vypadat takto:  
  
    ```csharp
    TestAsyncCommand.Initialize(this);  
    ```  
  
     Přesunout tohoto řádku `InitializeAsync()` metoda v souboru AsyncPackageForService.cs. Vzhledem k tomu, že je v asynchronní inicializace, před inicializací pomocí příkazu, je nutné přepnout do hlavního vlákna <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>. Teď by měl vypadat jako tento:  
  
    ```csharp  
  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);  

        ITextWriterService textService =   
           await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await textService.WriteLineAsync((<userpath>, "this is a test");  
  
        await this.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);  
        TestAsyncCommand.Initialize(this);
    }  
  
    ```  
  
3.  Odstranit `Initialize()` metoda.  
  
4.  V souboru TestAsyncCommand.cs najít `MenuItemCallback()` metoda. Odstraňte text metody.  
  
5.  Přidat pomocí příkazu:  
  
    ```csharp 
    using System.IO;  
    ```  
  
6.  Přidat asynchronní metodu s názvem `UseTextWriterAsync()`, který získá službu a používá jeho metody:  
  
    ```csharp  
    private async System.Threading.Tasks.Task UseTextWriterAsync()  
    {  
        // Query text writer service asynchronously to avoid a blocking call.
        ITextWriterService textService =   
           await AsyncServiceProvider.GlobalProvider.GetServiceAsync(typeof(STextWriterService))  
              as ITextWriterService;  

        // don't forget to change <userpath> to a local path  
        await textService.WriteLineAsync((<userpath>),"this is a test");  
       }  
  
    ```  
  
7.  Volat tuto metodu z `MenuItemCallback()` metoda:  
  
    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        UseTextWriterAsync();  
    }  
  
    ```  
  
8.  Sestavte řešení a spuštění ladění. Jakmile se zobrazí experimentální instanci sady Visual Studio, přejděte na **nástroje** nabídky a podívejte se **vyvolání TestAsyncCommand** položku nabídky. Po kliknutí na tlačítko ji, zapíše TextWriterService soubor, který jste zadali. (Nemusíte otevřete řešení, protože vyvolání příkazu také způsobí, že balíček, který chcete načíst.)  
  
## <a name="see-also"></a>Viz také  
 [Používání a poskytování služeb](../extensibility/using-and-providing-services.md)
