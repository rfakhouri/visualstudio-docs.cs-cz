---
title: "Postupy: poskytování služby asynchronní Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0448274c-d3d2-4e12-9d11-8aca78a1f3f5
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1bcf34f730411589624075bde4ace0b5457e07a7
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="how-to-provide-an-asynchronous-visual-studio-service"></a>Postupy: poskytování služby asynchronní Visual Studio
Pokud chcete získat službu bez blokování vlákna uživatelského rozhraní, doporučujeme vytvoření služby asynchronní a načíst balíček na vlákna na pozadí. Pro tento účel můžete použít <xref:Microsoft.VisualStudio.Shell.AsyncPackage> ne <xref:Microsoft.VisualStudio.Shell.Package>a přidejte službu s asynchronní balíček speciální asynchronních metod  
  
 Informace o poskytování služeb synchronní Visual Studio najdete v tématu [postupy: poskytování služby](../extensibility/how-to-provide-a-service.md).  
  
## <a name="implementing-an-asynchronous-service"></a>Implementace asynchronní služby  
  
1.  Vytvoření projektu VSIX (**soubor > Nový > Projekt > Visual C# > Extensiblity > Projekt VSIX**). Název projektu **TestAsync**.  
  
2.  Do projektu přidejte VSPackage. Vyberte uzel projektu v **Průzkumníku řešení** a klikněte na tlačítko **Přidat > novou položku > Visual C# položky > Rozšíření > Balíček Visual Studio**. Název tohoto souboru **TestAsyncPackage.cs**.  
  
3.  V TestAsyncPackage.cs měnit balíček dědění z AsyncPackage spíše než balíčku:  
  
    ```csharp  
    public sealed class TestAsyncPackage : AsyncPackage  
    ```  
  
4.  K implementaci služby, musíte vytvořit tři typy:  
  
    -   Rozhraní, které popisuje službu. Mnoho z těchto rozhraní je prázdný, to znamená, že mají žádné metody.  
  
    -   Rozhraní, které popisuje rozhraní služby. Toto rozhraní obsahuje metody k implementaci.  
  
    -   Třída, která implementuje rozhraní služby a služby.  
  
5.  Následující příklad ukazuje velmi základní implementaci všech tří typů. V konstruktoru třídy služeb, musíte nastavit poskytovatele služeb. V tomto příkladu právě přidáme službu k souboru balíčku kódu.  
  
6.  Přidejte následující příkazy using do souboru balíčku:  
  
    ```csharp  
    using System.Threading;  
    using System.Threading.Tasks;  
    using System.Runtime.CompilerServices;  
    using System.IO;  
    ```  
  
7.  Zde je implementace asynchronní služby. Všimněte si, že je nutné nastavit na poskytovatele asynchronní služby spíše než poskytovateli synchronní služby v konstruktoru:  
  
    ```  
    public class TextWriterService : STextWriterService, ITextWriterService  
    {  
        private Microsoft.VisualStudio.Shell.IAsyncServiceProvider serviceProvider;  
        public TextWriterService(Microsoft.VisualStudio.Shell.IAsyncServiceProvider provider)  
        {  
            serviceProvider = provider;  
        }  
        public async System.Threading.Tasks.Task WriteLineAsync(string path, string line)  
        {  
            StreamWriter writer = new StreamWriter(path);  
            await writer.WriteLineAsync(line);  
            writer.Close();  
        }  
        public TaskAwaiter GetAwaiter()  
        {  
            return new TaskAwaiter();  
        }  
    }  
    public interface STextWriterService  
    {  
    }  
    public interface ITextWriterService   
    {  
        System.Threading.Tasks.Task WriteLineAsync(string path, string line);  
        TaskAwaiter GetAwaiter();  
    }  
    ```  
  
## <a name="registering-a-service"></a>Registrace služby  
 Chcete-li zaregistrovat službu, přidejte <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> k balíčku, který poskytuje službu. Existují dva rozdíly registraci synchronní služby:  
  
-   Pokud jste autoloading balíčku, je nutné přidat <xref:Microsoft.VisualStudio.Shell.PackageAutoLoadFlags> BackgroundLoad hodnotu pro atribut. Další informace o autoloading VSPackages najdete v tématu [načítání VSPackages](../extensibility/loading-vspackages.md).  
  
-   Je nutné přidat **AllowsBackgroundLoading = true** do <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>. Další informace o PackageRegistrationAttribute najdete v tématu [registrace a zrušení registrace VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
 Tady je příklad AsyncPackage s registraci asynchronní služby::  
  
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
  
    ```  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
2.  Přidáte odkaz na Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll.  
  
3.  Metoda zpětného volání implementujte jako asynchronní metody, které vytváří a vrátí službu.  
  
    ```csharp  
    public async System.Threading.Tasks.Task<object> CreateService(IAsyncServiceContainer container, CancellationToken cancellationToken, Type serviceType)  
    {  
        STextWriterService service = null;  
        await System.Threading.Tasks.Task.Run(() => {  
                    service = new TextWriterService(this);  
             });  
  
        return service;  
    }  
  
    ```  
  
## <a name="using-a-service"></a>Pomocí služby  
 Teď můžete získat službu a použít její metody.  
  
1.  Ukážeme to inicializátoru, ale můžete získat službu kdekoli chcete používat službu.  
  
    ```csharp  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        ITextWriterService textService = await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await writer.WriteLineAsync(<userpath>), "this is a test");  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
     Nezapomeňte změnit  *\<userpath >* na název souboru a cesta, která dává smysl v počítači!  
  
2.  Sestavte a spusťte kód. Jakmile se zobrazí experimentální instanci sady Visual Studio, otevřete řešení. To způsobí, že AsyncPackage k autoload. Když se spustí inicializátoru, byste měli najít soubor v zadaném umístění.  
  
## <a name="using-an-asynchronous-service-in-a-command-handler"></a>Použití asynchronní služby v obslužná rutina příkazu  
 Tady je příklad toho, jak pomocí služby asynchronní v příkazu nabídky. Můžete použít postup používání služby v jiné-asynchronní metody tady uvedené.  
  
1.  Do projektu přidejte příkaz nabídky. (V **Průzkumníku řešení**, vyberte uzel projektu, klikněte pravým tlačítkem a vyberte **přidat / novou položku nebo rozšíření nebo postup pomocí příkazového vlastní**.) Název souboru příkaz **TestAsyncCommand.cs.**  
  
2.  Znovu přidá šablona vlastního příkazu `Initialize()` metoda k souboru TestAsyncPackage.cs za účelem inicializace příkaz. V metodě inicializaci() zkopírujte řádek, který inicializuje příkaz. Ho by měl vypadat takto:  
  
    ```  
    TestAsyncCommand.Initialize(this);  
    ```  
  
     Přesunout tohoto řádku `InitializeAsync()` metoda v souboru AsyncPackageForService.cs. Vzhledem k tomu, že je v asynchronní inicializace, před inicializací pomocí příkazu, je nutné přepnout do hlavního vlákna <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>. Teď by měl vypadat jako tento:  
  
    ```csharp  
  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        TestAsyncCommand.Initialize(this);    
  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        ITextWriterService textService =   
           await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await writer.WriteLineAsync((<userpath>, "this is a test");  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
3.  Odstranit `Initialize()` metoda.  
  
4.  V souboru TestAsyncCommand.cs najít `MenuItemCallback()` metoda. Odstraňte text metody.  
  
5.  Přidat pomocí příkazu:  
  
    ```  
    using System.IO;  
    ```  
  
6.  Přidat asynchronní metodu s názvem `GetAsyncService()`, který získá službu a používá jeho metody:  
  
    ```csharp  
    private async System.Threading.Tasks.Task GetAsyncService()  
    {  
        ITextWriterService textService =   
           this.ServiceProvider.GetService(typeof(STextWriterService))  
              as ITextWriterService;  
        // don't forget to change <userpath> to a local path  
        await writer.WriteLineAsync((<userpath>),"this is a test");  
       }  
  
    ```  
  
7.  Volat tuto metodu z `MenuItemCallback()` metoda:  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        GetAsyncService();  
    }  
  
    ```  
  
8.  Sestavte řešení a spuštění ladění. Jakmile se zobrazí experimentální instanci sady Visual Studio, přejděte na **nástroje** nabídky a podívejte se **vyvolání TestAsyncCommand** položku nabídky. Po kliknutí na tlačítko ji, zapíše TextWriterService soubor, který jste zadali. (Nemusíte otevřete řešení, protože vyvolání příkazu také způsobí, že balíček, který chcete načíst.)  
  
## <a name="see-also"></a>Viz také  
 [Používání a poskytování služeb](../extensibility/using-and-providing-services.md)