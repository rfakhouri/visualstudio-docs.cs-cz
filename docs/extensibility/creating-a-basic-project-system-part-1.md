---
title: "Vytvoření systému základní projektu, část 1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- writing a project system
- project system
- tutorial
ms.assetid: 882a10fa-bb1c-4b01-943a-7a3c155286dd
caps.latest.revision: "47"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e61c0d681dac52e85c3854325ee20ada29d74d4c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-basic-project-system-part-1"></a>Vytvoření systému základní projektu, část 1
Projekty v sadě Visual Studio jsou kontejnery, které vývojáři použít k uspořádání soubory zdrojového kódu a další prostředky. Projekty zobrazí jako podřízené objekty řešení **Průzkumníku řešení**. Projekty umožňují uspořádat, vytváření, ladění a zavádění zdrojového kódu a vytvořit odkazy na webové služby, databáze a dalším prostředkům.  
  
 Projekty jsou definovány v souborech projektu, například souboru .csproj pro projekt Visual C#. Můžete vytvořit vlastní typ projektu, který má vlastní příponu názvu souboru projektu. Další informace o typech projektů najdete v tématu [typy projektů](../extensibility/internals/project-types.md).  
  
> [!NOTE]
>  Pokud potřebujete rozšířit s typem vlastních projektů sady Visual Studio, doporučujeme využívat [systému projektu Visual Studio](https://github.com/Microsoft/VSProjectSystem) které má několik výhod oproti sestavení projektu systému od začátku:  
>   
>  -   Jednodušší registrace.  I systému základní projektu vyžaduje desetitisíce řádků kódu.  Využití CPS snižuje náklady registrace na několik kliknutí, než se budete chtít přizpůsobit svým potřebám.  
> -   Snazší údržby.  S využitím CPS, stačí udržovat vlastní scénáře.  Nemůžeme zpracovat provoz všech infrastruktury systému projektu.  
>   
>  Pokud budete potřebovat cílové verze sady Visual Studio, které jsou starší než Visual Studio 2013, nebudete moct využít prohlášení CPS v rozšíření sady Visual Studio.  Pokud je to tento případ, Tento názorný postup je dobrým místem, kde začít pracovat.  
  
 Tento návod ukazuje, jak vytvořit typu projektu, který má .myproj rozšíření projektu soubor název. Tento názorný postup vypůjčí z existujícího systému projekt Visual C#.  
  
> [!NOTE]
>  Další příklady projekty rozšíření najdete v tématu [VSSDK ukázky](http://aka.ms/vs2015sdksamples).  
  
 Tento názorný postup učí, jak provést tyto úlohy:  
  
-   Vytvoření základního projektu typu.  
  
-   Vytvoření základního projektu šablony.  
  
-   Zaregistrujte v šabloně projektů pomocí sady Visual Studio.  
  
-   Vytvoření projektu instance otevřením **nový projekt** dialogové okno a potom pomocí vlastní šablony.  
  
-   Vytvořte objekt pro vytváření projektu pro váš systém projektu.  
  
-   Vytvoření projektu uzel pro váš systém projektu.  
  
-   Přidáte vlastní ikony pro projekt systému.  
  
-   Implementovat nahrazování parametru základní šablony.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
 Je nutné také stáhnout zdrojový kód [spravované rozhraní balíčku pro projekty](http://mpfproj12.codeplex.com/). Extrahujte soubor do umístění, které je přístupné pro řešení, které chcete vytvořit.  
  
## <a name="creating-a-basic-project-type"></a>Vytvoření základního projektu typu  
 Vytvoření projektu C# VSIX s názvem **SimpleProject**. (**Soubor nové, projektu** a potom **balíčku sady Visual Studio C#, rozšiřitelnosti,**). Přidání šablony položek projektu balíček Visual Studio (v Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**, pak přejděte na **rozšiřitelnost nebo balíček Visual Studio**). Název souboru **SimpleProjectPackage**.  
  
## <a name="creating-a-basic-project-template"></a>Vytvoření základního projektu šablony  
 Nyní můžete upravit tento základní VSPackage implementovat nový typ .myproj projektu. Pro vytvoření projektu, který je založený na typu projektu .myproj musí vědět, které soubory, zdroje a odkazy na přidejte do nového projektu sady Visual Studio. Poskytnout tyto informace, uveďte projektu soubory ve složce projektu šablony. Pokud uživatel používá k vytvoření projektu .myproj projektu, soubory se zkopírují do nového projektu.  
  
#### <a name="to-create-a-basic-project-template"></a>Vytvoření základního projektu šablony  
  
1.  Přidejte do projektu, jeden v jiné tři složky: **Templates\Projects\SimpleProject**. (V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **SimpleProject** uzel projektu, přejděte na **přidat**a potom klikněte na **novou složku**. Název složky `Templates`. V **šablony** složky, přidejte do složky s názvem `Projects`. V **projekty** složky, přidejte do složky s názvem `SimpleProject`.)  
  
2.  V **Projects\SimpleProject** složky přidat soubor ikony s názvem `SimpleProject.ico`. Když kliknete na tlačítko **přidat**, otevře se editor ikonu.  
  
3.  Ujistěte se, ikonu rozlišovací. Tato ikona se objeví v **nový projekt** dialogové okno později v tomto návodu.  
  
     ![Ikona Jednoduchý projekt](../extensibility/media/simpleprojicon.png "SimpleProjIcon")  
  
4.  Ikona uložte a zavřete editor ikon.  
  
5.  V **Projects\SimpleProject** složky, přidejte **třída** položka s názvem `Program.cs`.  
  
6.  Nahraďte stávající kód následující řádky.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace $nameSpace$  
    {  
        public class $className$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
    > [!IMPORTANT]
    >  Toto není poslední formu kód Program.cs; nahrazující parametry se rozhodne do pozdějšího kroku. Může se zobrazit nějaké chyby, ale stejně dlouho jako souboru **BuildAction** je **obsahu**, byste měli mít sestavit a spustit projekt jako obvykle.  
  
1.  Uložte soubor.  
  
2.  Kopírování souboru AssemblyInfo.cs z **vlastnosti** složka, v níž **Projects\SimpleProject** složky.  
  
3.  V **Projects\SimpleProject** složky přidat soubor XML s názvem `SimpleProject.myproj`.  
  
    > [!NOTE]
    >  Přípona názvu souboru pro všechny projekty tohoto typu je .myproj. Pokud chcete změnit, pak je nutné změnit všude, kde je uveden v návodu.  
  
4.  Nahradí existující obsah s následujícími řádky.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <SchemaVersion>2.0</SchemaVersion>  
        <ProjectGuid></ProjectGuid>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>MyRootNamespace</RootNamespace>  
        <AssemblyName>MyAssemblyName</AssemblyName>  
        <EnableUnmanagedDebugging>false</EnableUnmanagedDebugging>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
        <DebugSymbols>true</DebugSymbols>  
        <OutputPath>bin\Debug\</OutputPath>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">  
        <DebugSymbols>false</DebugSymbols>  
        <OutputPath>bin\Release\</OutputPath>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="mscorlib" />  
        <Reference Include="System" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Xml" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="AssemblyInfo.cs">  
          <SubType>Code</SubType>  
        </Compile>  
        <Compile Include="Program.cs">  
          <SubType>Code</SubType>  
        </Compile>  
      </ItemGroup>  
      <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />  
    </Project>  
    ```  
  
5.  Uložte soubor.  
  
6.  V **vlastnosti** nastavte **akce sestavení** AssemblyInfo.cs, Program.cs, SimpleProject.ico a SimpleProject.myproj k **obsahu**a nastavte jejich  **Zahrnout do VSIX** vlastnosti, které chcete **True**.  
  
 Tato šablona projektu popisuje základní Visual C# projektu, který má konfiguraci ladění a vydání konfigurace. Projekt obsahuje dvě zdrojové soubory, AssemblyInfo.cs a Program.cs a několik sestavení odkazů. Při vytvoření projektu ze šablony, je hodnota ProjectGuid automaticky nahrazena nový identifikátor GUID.  
  
 V **Průzkumníku řešení**, rozšířená **šablony** složky by měly vypadat následovně:  
  
 Šablony  
  
 Projekty  
  
 SimpleProject  
  
 AssemblyInfo.cs  
  
 Program.cs  
  
 SimpleProject.ico  
  
 SimpleProject.myproj  
  
## <a name="creating-a-basic-project-factory"></a>Vytvoření základního projektu Factory  
 Visual Studio se musí zjistit umístění složky šablony projektu. K tomuto účelu přidání atributu do VSPackage třídu, která implementuje objektu pro vytváření projektů tak, aby umístění šablon je zapsán do systémového registru, když je založený VSPackage. Začněte vytvořením projektu základní objekt factory, který je identifikována objekt pro vytváření projektu identifikátor GUID. Použití <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> atribut pro připojení k třídě SimpleProjectPackage objektu pro vytváření projektu.  
  
#### <a name="to-create-a-basic-project-factory"></a>Vytvořte objekt pro vytváření základního projektu  
  
1.  Otevřete SimpleProjectPackageGuids.cs v editoru kódu.  
  
2.  Vytvoření identifikátory GUID objektu pro vytváření vašeho projektu (na **nástroje** nabídky, klikněte na tlačítko **vytvořit GUID**), nebo použijte v následujícím příkladu. Přidejte identifikátory GUID pro třídu SimpleProjectPackageGuids. Identifikátory GUID musí být ve formátu identifikátoru GUID a formátu řetězce. Výsledný kód by měl podobat následujícímu příkladu.  
  
    ```  
    static class SimpleProjectPackageGuids  
    {  
        public const string guidSimpleProjectPkgString =   
            "96bf4c26-d94e-43bf-a56a-f8500b52bfad";  
        public const string guidSimpleProjectCmdSetString =   
            "72c23e1d-f389-410a-b5f1-c938303f1391";  
        public const string guidSimpleProjectFactoryString =   
            "471EC4BB-E47E-4229-A789-D1F5F83B52D4";  
  
        public static readonly Guid guidSimpleProjectCmdSet =   
            new Guid(guidSimpleProjectCmdSetString);  
        public static readonly Guid guidSimpleProjectFactory =   
            new Guid(guidSimpleProjectFactoryString);  
    }  
    ```  
  
3.  Do horní části přidejte třídu **SimpleProject** složku s názvem `SimpleProjectFactory.cs`.  
  
4.  Přidejte následující příkazy:  
  
    ```  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
5.  Přidá k třídě SimpleProjectFactory atribut Guid. Hodnota atributu je nový objekt factory projektu identifikátor GUID.  
  
    ```  
    [Guid(SimpleProjectGuids.guidSimpleProjectFactoryString)]  
    class SimpleProjectFactory  
    {  
    }  
    ```  
  
 Nyní můžete zaregistrovat vaše šablona projektu.  
  
#### <a name="to-register-the-project-template"></a>K registraci v šabloně projektů  
  
1.  V SimpleProjectPackage.cs, přidejte <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> atribut k třídě SimpleProjectPackage následujícím způsobem.  
  
    ```  
    [ProvideProjectFactory(    typeof(SimpleProjectFactory),     "Simple Project",   
        "Simple Project Files (*.myproj);*.myproj", "myproj", "myproj",   
        @"Templates\Projects\SimpleProject",     LanguageVsTemplate = "SimpleProject")]  
    [Guid(SimpleProjectGuids.guidSimpleProjectPkgString)]  
    public sealed class SimpleProjectPackage : Package  
    ```  
  
2.  Znovu sestavte řešení a ověřte, že sestavení bez chyb.  
  
     Opětovné sestavení zaregistruje v šabloně projektů.  
  
 Parametry `defaultProjectExtension` a `possibleProjectExtensions` jsou nastaveny na příponu názvu souboru projektu (.myproj). `projectTemplatesDirectory` Parametr nastavený na relativní cestu ke složce šablony. Během vytváření sestavení bude tato cesta převést na úplné sestavení a přidat do registru k registraci systému projektu.  
  
## <a name="testing-the-template-registration"></a>Testování registrace šablony  
 Šablona registrace informuje Visual Studio umístění složky šablony projektu tak, aby Visual Studio může zobrazit název šablony a ikona **nový projekt** dialogové okno.  
  
#### <a name="to-test-the-template-registration"></a>Testování registrace šablony  
  
1.  Stisknutím klávesy F5 spusťte ladění experimentální instanci sady Visual Studio.  
  
2.  V experimentální instanci vytvořte nový projekt typu vaše nově vytvořený projekt. V **nový projekt** dialogové okno, měli byste vidět **SimpleProject** pod **– nainstalované šablony**.  
  
 Nyní máte projekt objekt factory, který je zaregistrován. Však nelze vytvořit ještě projektu. Balíček projektu a objektu pro vytváření projektu vzájemně spolupracují a vytvoření a inicializace projektu.  
  
## <a name="add-the-managed-package-framework-code"></a>Přidejte kód spravované Framework balíčku  
 Implementujte propojení projektu balíček a objektu pro vytváření projektu.  
  
-   Naimportujte soubory zdrojového kódu pro balíček Framework spravované.  
  
    1.  Uvolnit projekt SimpleProject (v **Průzkumníku řešení**, vyberte uzel projektu a v místní nabídce klikněte na **uvolnit projekt**.) a otevřete soubor projektu v editoru XML.  
  
    2.  Přidejte následující bloky do souboru projektu (právě vyšší \<Import > bloky). Nastavte ProjectBasePath na umístění souboru ProjectBase.files v spravované Framework balíček kódu, kterou jste právě stáhli. Možná budete muset přidat k názvu cesty zpětné lomítko. Pokud ho použít nechcete, může selhat projekt najít kód spravované Framework balíčku.  
  
        ```  
        <PropertyGroup>  
             <ProjectBasePath>your path here\</ProjectBasePath>  
             <RegisterWithCodebase>true</RegisterWithCodebase>  
          </PropertyGroup>  
          <Import Project="$(ProjectBasePath)\ProjectBase.Files" />  
        ```  
  
        > [!IMPORTANT]
        >  Nezapomeňte zpětné lomítko na konci cesty.  
  
    3.  Znovu načte projekt.  
  
    4.  Přidejte odkazy na následující sestavení:  
  
        -   Microsoft.VisualStudio.Designer.Interfaces (v \<instalace VSSDK > \VisualStudioIntegration\Common\Assemblies\v2.0)  
  
        -   WindowsBase  
  
        -   Microsoft.Build.Tasks.v4.0  
  
#### <a name="to-initialize-the-project-factory"></a>K chybě při inicializaci objektu pro vytváření projektu  
  
1.  V souboru SimpleProjectPackage.cs, přidejte následující `using` příkaz.  
  
    ```  
    using Microsoft.VisualStudio.Project;  
    ```  
  
2.  Odvození `SimpleProjectPackage` třídy z `Microsoft.VisualStudio.Package.ProjectPackage`.  
  
    ```  
    public sealed class SimpleProjectPackage : ProjectPackage  
    ```  
  
3.  Zaregistrujte objekt pro vytváření projektu. Přidejte následující řádek na `SimpleProjectPackage.Initialize` metoda, hned za `base.Initialize`.  
  
    ```  
    base.Initialize();  
    this.RegisterProjectFactory(new SimpleProjectFactory(this));  
    ```  
  
4.  Implementovat abstraktní vlastnost `ProductUserContext`:  
  
    ```csharp  
    public override string ProductUserContext  
        {  
            get { return ""; }  
    }  
    ```  
  
5.  V SimpleProjectFactory.cs, přidejte následující `using` příkaz po existující `using` příkazy.  
  
    ```  
    using Microsoft.VisualStudio.Project;  
    ```  
  
6.  Odvození `SimpleProjectFactory` třídy z `ProjectFactory`.  
  
    ```  
    class SimpleProjectFactory : ProjectFactory  
    ```  
  
7.  Přidejte následující metodu fiktivní do `SimpleProjectFactory` třídy. Tato metoda se implementovat v další části.  
  
    ```  
    protected override ProjectNode CreateProject()  
    {  
        return null;  
    }  
    ```  
  
8.  Přidejte následující pole a konstruktor `SimpleProjectFactory` třídy. To `SimpleProjectPackage` odkaz je uložené v mezipaměti v soukromé pole tak, aby může sloužit nastavení lokality poskytovatele služby.  
  
    ```  
    private SimpleProjectPackage package;  
  
    public SimpleProjectFactory(SimpleProjectPackage package)  
        : base(package)  
    {  
        this.package = package;  
    }  
    ```  
  
9. Znovu sestavte řešení a ověřte, že sestavení bez chyb.  
  
## <a name="testing-the-project-factory-implementation"></a>Testování implementace objektu Factory projektu  
 Ověřte, zda je volána v konstruktoru pro implementaci objekt pro vytváření projektu.  
  
#### <a name="to-test-the-project-factory-implementation"></a>Pro testování implementace objektu pro vytváření projektu  
  
1.  V souboru SimpleProjectFactory.cs nastavit zarážky na následujícím řádku `SimpleProjectFactory` konstruktor.  
  
    ```  
    this.package = package;  
    ```  
  
2.  Stisknutím klávesy F5 spusťte experimentální instanci sady Visual Studio.  
  
3.  V experimentální instanci spusťte pro vytvoření nového projektu. V **nový projekt** dialogové okno, vyberte SimpleProject typ projektu a pak klikněte na **OK**. Provádění zastaví u zarážky.  
  
4.  Vymažte zarážce a zastavte ladění. Vzhledem k tomu, že jsme uzel projektu ještě nevytvořili, vyvolá kód pro vytvoření projektu stále výjimek.  
  
## <a name="extending-the-project-node-class"></a>Rozšíření třídy uzlu projektu  
 Teď můžete implementovat `SimpleProjectNode` třída, která je odvozena z `ProjectNode` třídy. `ProjectNode` Základní třída zpracovává následující úlohy vytváření projektu:  
  
-   Soubor šablony projektu SimpleProject.myproj, zkopíruje do nové složky projektu. Kopie je přejmenovat podle názvu, která je zadána v **nový projekt** dialogové okno. `ProjectGuid` Hodnota vlastnosti je nahrazena nový identifikátor GUID.  
  
-   Prochází MSBuild elementy soubor šablony projektu SimpleProject.myproj a hledá `Compile` elementy. Pro každou `Compile` cílový soubor zkopíruje soubor do nové složky projektu.  
  
 Odvozené `SimpleProjectNode` třída zpracovává tyto úlohy:  
  
-   Umožňuje ikony pro projekt a soubor uzly v **Průzkumníku řešení** má být vytvořen nebo vybrané.  
  
-   Povoluje nahrazení parametru šablony další projektu zadat.  
  
#### <a name="to-extend-the-project-node-class"></a>Rozšíření třídy uzlu projektu  
  
1.  
  
2.  Přidejte třídu s názvem `SimpleProjectNode.cs`.  
  
3.  Existujícího kódu nahraďte následujícím kódem.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Project;  
  
    namespace SimpleProject  
    {  
        public class SimpleProjectNode : ProjectNode  
        {  
            private SimpleProjectPackage package;  
  
            public SimpleProjectNode(SimpleProjectPackage package)  
            {  
                this.package = package;  
            }  
            public override Guid ProjectGuid  
            {  
                get { return SimpleProjectGuids.guidSimpleProjectFactory; }  
            }  
            public override string ProjectType  
            {  
                get { return "SimpleProjectType"; }  
            }  
  
            public override void AddFileFromTemplate(  
                string source, string target)  
            {  
                this.FileTemplateProcessor.UntokenFile(source, target);  
                this.FileTemplateProcessor.Reset();  
            }  
        }  
    }  
    ```  
  
 To `SimpleProjectNode` třída implementace má tyto přepsané metody:  
  
-   `ProjectGuid`, která vrací objekt pro vytváření projektu identifikátor GUID.  
  
-   `ProjectType`, která vrací lokalizovaný název typu projektu.  
  
-   `AddFileFromTemplate`, který zkopíruje vybrané soubory ve složce šablony do cílového projektu. Tato metoda je další implementována v další části.  
  
 `SimpleProjectNode` Konstruktor, například `SimpleProjectFactory` konstruktoru, ukládá do mezipaměti `SimpleProjectPackage` odkaz v soukromé pole pro pozdější použití.  
  
 Pro připojení `SimpleProjectFactory` třídy k `SimpleProjectNode` třídy, je nutné vytvořit novou instanci `SimpleProjectNode` v `SimpleProjectFactory.CreateProject` metoda a uložení do mezipaměti v soukromé pole pro pozdější použití.  
  
#### <a name="to-connect-the-project-factory-class-and-the-node-class"></a>Pro připojení třídu objektů factory projektu a třída uzlu  
  
1.  V souboru SimpleProjectFactory.cs, přidejte následující `using` příkaz:  
  
    ```  
    using IOleServiceProvider =    Microsoft.VisualStudio.OLE.Interop.IServiceProvider;  
    ```  
  
2.  Nahraďte `SimpleProjectFactory.CreateProject` metoda pomocí následující kód.  
  
    ```  
    protected override ProjectNode CreateProject()  
    {  
        SimpleProjectNode project = new SimpleProjectNode(this.package);  
  
        project.SetSite((IOleServiceProvider)        ((IServiceProvider)this.package).GetService(            typeof(IOleServiceProvider)));  
        return project;  
    }  
    ```  
  
3.  Znovu sestavte řešení a ověřte, že sestavení bez chyb.  
  
## <a name="testing-the-project-node-class"></a>Testování třída uzlu projektu  
 Testovací objekt pro vytváření vašeho projektu zobrazíte, zda vytvoří hierarchii projektu.  
  
#### <a name="to-test-the-project-node-class"></a>K testování třída uzlu projektu  
  
1.  Stisknutím klávesy F5 spusťte ladění. V experimentální instance vytvořte nový SimpleProject.  
  
2.  Visual Studio by měly volat vaše pro vytváření projektu pro vytvoření projektu.  
  
3.  Ukončete experimentální instanci sady Visual Studio.  
  
## <a name="adding-a-custom-project-node-icon"></a>Přidání uzlu ikonou vlastních projektů  
 Ikona uzlu projektu v dřívější části, je výchozí ikona. Můžete ho změnit na vlastní ikonou.  
  
#### <a name="to-add-a-custom-project-node-icon"></a>Chcete-li přidat uzel ikonou vlastních projektů  
  
1.  V **prostředky** složky, přidejte soubor rastrového obrázku s názvem SimpleProjectNode.bmp.  
  
2.  V **vlastnosti** windows, snižte bitmapy na 16 × 16 pixelů. Ujistěte se, bitmapy rozlišovací.  
  
     ![Jednoduchý projekt – příkaz](../extensibility/media/simpleprojprojectcomm.png "SimpleProjProjectComm")  
  
3.  V **vlastnosti** změňte **akce sestavení** bitmapy k **vložený prostředek**.  
  
4.  V SimpleProjectNode.cs, přidejte následující `using` příkazy:  
  
    ```  
    using System.Drawing;  
    using System.Windows.Forms;  
    ```  
  
5.  Přidejte následující statické pole a konstruktor `SimpleProjectNode` třídy.  
  
    ```  
    private static ImageList imageList;  
  
    static SimpleProjectNode()  
    {  
        imageList =        Utilities.GetImageList(            typeof(SimpleProjectNode).Assembly.GetManifestResourceStream(                "SimpleProject.Resources.SimpleProjectNode.bmp"));  
    }  
    ```  
  
6.  Přidejte následující vlastnost na začátek `SimpleProjectNode` třídy.  
  
    ```  
    internal static int imageIndex;  
       public override int ImageIndex  
       {  
           get { return imageIndex; }  
       }  
    ```  
  
7.  V konstruktoru instance nahraďte následujícím kódem.  
  
    ```  
    public SimpleProjectNode(SimpleProjectPackage package)  
    {  
        this.package = package;  
  
        imageIndex = this.ImageHandler.ImageList.Images.Count;  
  
        foreach (Image img in imageList.Images)  
        {  
            this.ImageHandler.AddImage(img);  
        }  
    }  
    ```  
  
 Během vytváření statické `SimpleProjectNode` načte bitovou mapu uzlu projektu z manifestu prostředků sestavení a ukládá do mezipaměti v soukromé pole pro pozdější použití. Všimněte si syntaxe <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> cestu k bitové kopii. Pokud chcete zobrazit názvy manifestu prostředků, které jsou součástí sestavení, použijte <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> metoda. Když tato metoda se použije na `SimpleProject` sestavení, výsledky by měl vypadat takto:  
  
-   SimpleProject.Resources.resources  
  
-   VisualStudio.Project.resources  
  
-   SimpleProject.VSPackage.resources  
  
-   Resources.imagelis.bmp  
  
-   Microsoft.VisualStudio.Project.DontShowAgainDialog.resources  
  
-   Microsoft.VisualStudio.Project.SecurityWarningDialog.resources  
  
-   SimpleProject.Resources.SimpleProjectNode.bmp  
  
 Při vytváření instance `ProjectNode` Resources.imagelis.bmp, ve kterém jsou embedded běžně používané velikosti 16 x 16 bitmap z Resources\imagelis.bmp načte základní třídy. Tento seznam rastrového obrázku je k dispozici na `SimpleProjectNode` jako ImageHandler.ImageList. `SimpleProjectNode`připojí rastrový obrázek uzlu projektu do seznamu. Posun projektu bitmapa uzlu v seznamu obrázků se uloží do mezipaměti pro pozdější použití jako hodnota veřejnosti `ImageIndex` vlastnost. Visual Studio používá tuto vlastnost k určení které rastrový obrázek zobrazuje jako ikonu uzlu projektu.  
  
## <a name="testing-the-custom-project-node-icon"></a>Testování ikonu uzlu vlastních projektů  
 Testování vaší vytváření projektu zobrazíte, zda vytvoří projekt hierarchie, která má ikonu uzlu vaše vlastní projektu.  
  
#### <a name="to-test-the-custom-project-node-icon"></a>K testování ikonu uzlu vlastních projektů  
  
1.  Spuštění ladění a v experimentální instanci vytvořte nové SimpleProject.  
  
2.  V nově vytvořený projekt Všimněte si, že SimpleProjectNode.bmp slouží jako ikonu uzlu projektu.  
  
     ![Jednoduché projektu nový uzel projektu](../extensibility/media/simpleprojnewprojectnode.png "SimpleProjNewProjectNode")  
  
3.  Otevřete Program.cs v editoru kódu. Měli byste vidět zdrojového kódu, která se podobá následující kód.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace $nameSpace$  
    {  
        public class $className$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
     Všimněte si, že parametry šablony $nameSpace$ a $className$ nemají nové hodnoty. Se dozvíte, jak implementovat nahrazování parametru šablony v další části.  
  
## <a name="substituting-template-parameters"></a>Nahraďte parametry šablony  
 V předchozí části, je zaregistrován v šabloně projektů pomocí sady Visual Studio pomocí `ProvideProjectFactory` atribut. Registrace cestu složky pro šablony tímto způsobem umožňuje povolit nahrazování parametru základní šablony přepsání a rozšíření `ProjectNode.AddFileFromTemplate` třídy. Další informace najdete v tématu [nové generace projektu: pod pokličkou, část dvě](../extensibility/internals/new-project-generation-under-the-hood-part-two.md).  
  
 Teď přidejte kód nahrazení, který `AddFileFromTemplate` třídy.  
  
#### <a name="to-substitute-template-parameters"></a>Nahradit parametry šablony  
  
1.  V souboru SimpleProjectNode.cs, přidejte následující `using` příkaz.  
  
    ```  
    using System.IO;  
    ```  
  
2.  Nahraďte `AddFileFromTemplate` metoda pomocí následující kód.  
  
    ```  
    public override void AddFileFromTemplate(  
        string source, string target)  
    {  
        string nameSpace =   
            this.FileTemplateProcessor.GetFileNamespace(target, this);  
        string className = Path.GetFileNameWithoutExtension(target);  
  
        this.FileTemplateProcessor.AddReplace("$nameSpace$", nameSpace);  
        this.FileTemplateProcessor.AddReplace("$className$", className);  
  
        this.FileTemplateProcessor.UntokenFile(source, target);  
        this.FileTemplateProcessor.Reset();  
    }  
    ```  
  
3.  Nastavte zarážky v metodě, bezprostředně za `className` příkaz přiřazení.  
  
 Příkazy přiřazení určit rozumné hodnoty pro obor názvů a nový název třídy. Dva `ProjectNode.FileTemplateProcessor.AddReplace` volání metod nahrazení hodnot parametrů šablony odpovídající pomocí tyto nové hodnoty.  
  
## <a name="testing-the-template-parameter-substitution"></a>Testování nahrazování parametru šablony  
 Nyní můžete otestovat nahrazování parametru šablony.  
  
#### <a name="to-test-the-template-parameter-substitution"></a>K testování nahrazování parametru šablony  
  
1.  Spuštění ladění a v experimentální instanci vytvořte nové SimpleProject.  
  
2.  Spuštění zastaví na zarážka v `AddFileFromTemplate` metoda.  
  
3.  Zkontrolujte hodnoty `nameSpace` a `className` parametry.  
  
    -   `nameSpace`je zadána hodnota \<RootNamespace > element v souboru \Templates\Projects\SimpleProject\SimpleProject.myproj projektu šablony. V takovém případě je hodnota "MyRootNamespace".  
  
    -   `className`je zadána hodnota název třídy zdrojového souboru bez přípony názvu souboru. V takovém případě je první soubor, který se má zkopírovat do cílové složky AssemblyInfo.cs; Hodnota className tedy "AssemblyInfo".  
  
4.  Odeberte zarážce a stisknutím klávesy F5 pro pokračování v provádění.  
  
     Visual Studio by měl dokončit vytváření projektu.  
  
5.  Otevřete Program.cs v editoru kódu. Měli byste vidět zdrojového kódu, která se podobá následující kód.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace MyRootNamespace  
    {  
        public class Program  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
     Všimněte si, že obor názvů je nyní "MyRootNamespace" a název třídy je nyní "Program".  
  
6.  Spusťte ladění projektu. Nový projekt by měla kompilovat, spustit a zobrazit "text Hello VSX!" v okně konzoly.  
  
     ![Jednoduchý projekt – příkaz](../extensibility/media/simpleprojcommand.png "SimpleProjCommand")  
  
 Blahopřejeme! Byla implementována základní spravovaný projekt systému.