---
title: Vytvoření systému základní projektu, část 2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- writing a project system
- project system
- tutorial
ms.assetid: aee48fc6-a15f-4fd5-8420-7f18824de220
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f39150f02481e18997035a8027518648fa410f48
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107943"
---
# <a name="creating-a-basic-project-system-part-2"></a>Vytvoření systému základní projektu, část 2
První postup v této série [vytváření základní systému projektu, část 1](../extensibility/creating-a-basic-project-system-part-1.md), ukazuje, jak vytvořit základní projekt systému. Tento názorný postup je založený na systému základní projektu přidáním šablony sady Visual Studio, stránky vlastností a dalších funkcí. První postup musíte provést před zahájením této jeden.  
  
 Tento názorný postup učí, jak vytvořit typ projektu, který má .myproj rozšíření projektu soubor název. K dokončení průvodce, nemáte vytvořit svůj vlastní jazyk, protože návodu vypůjčí z existujícího systému projekt Visual C#.  
  
 Tento názorný postup učí, jak provést tyto úlohy:  
  
-   Vytvoření šablony sady Visual Studio.  
  
-   Nasazení šablony sady Visual Studio.  
  
-   Vytvoření projektu typu podřízený uzel v **nový projekt** dialogové okno.  
  
-   Povolte nahrazení parametrů v šabloně sady Visual Studio.  
  
-   Vytvořte stránce vlastností projektu.  
  
> [!NOTE]
>  Kroky v tomto průvodci jsou založeny na projekt C#. S výjimkou specifika přípony názvů souborů a kód, ale můžete pomocí stejných kroků pro projektu jazyka Visual Basic.  
  
## <a name="creating-a-visual-studio-template"></a>Vytvoření šablony sady Visual Studio  
 [Vytvoření základního systému projektu, část 1](../extensibility/creating-a-basic-project-system-part-1.md) ukazuje, jak vytvořit šablonu základní projekt a přidejte ji do projektu systému. Také ukazuje, jak zaregistrovat pomocí této šablony pomocí sady Visual Studio <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> atribut, který zapíše úplnou cestu ke složce \Templates\Projects\SimpleProject\ v registru systému.  
  
 Pomocí šablony sady Visual Studio (soubor .vstemplate) místo základního projektu šablony, můžete řídit, jak se zobrazí v šabloně **nový projekt** dialogové okno a jak jsou nahrazena parametry šablony.  Soubor .vstemplate je soubor XML, který popisuje, jak mají být zahrnuty při vytvoření projektu pomocí šablony projektu systému zdrojové soubory. Samotného systému projektu je sestavena shromažďování souboru .vstemplate a zdrojových souborů v souboru ZIP a nasazovat tak, že zkopírujete soubor .zip do umístění, ve kterém se ví, Visual Studio. Tento proces je podrobně popsány dále v tomto návodu.  
  
1.  V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otevřete SimpleProject řešení, které jste vytvořili pomocí následujících [vytváření základní systému projektu, část 1](../extensibility/creating-a-basic-project-system-part-1.md).  
  
2.  V souboru SimpleProjectPackage.cs najít atribut ProvideProjectFactory. Nahraďte druhý parametr (název projektu) s hodnotou null a čtvrtého parametru (cesta ke složce šablony projektu) ". \\\NullPath ", a to takto.  
  
    ```  
    [ProvideProjectFactory(typeof(SimpleProjectFactory), null,  
        "Simple Project Files (*.myproj);*.myproj", "myproj", "myproj",  
        ".\\NullPath",  
    LanguageVsTemplate = "SimpleProject")]  
    ```  
  
3.  Přidání souboru XML s názvem SimpleProject.vstemplate ke složce \Templates\Projects\SimpleProject\.  
  
4.  Obsah SimpleProject.vstemplate nahraďte následujícím kódem.  
  
    ```xml  
    <VSTemplate Version="2.0.0" Type="Project"  
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
      <TemplateData>  
        <Name>SimpleProject Application</Name>  
        <Description>  
            A project for creating a SimpleProject application  
         </Description>  
         <Icon>SimpleProject.ico</Icon>  
         <ProjectType>SimpleProject</ProjectType>  
      </TemplateData>  
      <TemplateContent>  
        <Project File="SimpleProject.myproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" OpenInEditor="true">  
              Program.cs  
          </ProjectItem>  
          <ProjectItem ReplaceParameters="true" OpenInEditor="false">  
             AssemblyInfo.cs  
          </ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
5.  V **vlastnosti** okno, vyberte všechny pět souborů ve složce \Templates\Projects\SimpleProject\ a sadu **akce sestavení** k **ZipProject**.  
  
 ![](../extensibility/media/simpproj2.png "SimpProj2")  
  
 \<TemplateData > části určuje umístění a vzhled typ projektu SimpleProject v **nový projekt** dialogové okno, následujícím způsobem:  
  
-   \<Name > element názvy šablona projektu jako SimpleProject aplikace.  
  
-   \<Popis > element obsahuje popis, který se zobrazí v **nový projekt** dialogové okno když je vybraná šablona projektu.  
  
-   \<Ikonu > element určuje ikona, která se zobrazí spolu s SimpleProject typ projektu.  
  
-   \<ProjectType – > typ projektu v názvy elementu **nový projekt** dialogové okno. Tento název nahrazuje parametr název projektu ProvideProjectFactory atributu.  
  
    > [!NOTE]
    >  \<ProjectType > elementu se musí shodovat `LanguageVsTemplate` argument `ProvideProjectFactory` atribut v souboru SimpleProjectPackage.cs.  
  
 \<TemplateContent > část popisuje tyto soubory, které jsou generovány, pokud je vytvořen nový projekt:  
  
-   SimpleProject.myproj  
  
-   Program.cs  
  
-   AssemblyInfo.cs  
  
 Všechny tři soubory `ReplaceParameters` nastavit na hodnotu true, která umožňuje nahrazování parametru.  Soubor Program.cs má `OpenInEditor` nastavit na hodnotu true, což způsobí, že soubor otevřít v editoru kódu při vytvoření projektu.  
  
 Další informace o elementy ve schématu šablony Visual Studio najdete v tématu [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md).  
  
> [!NOTE]
>  Pokud projekt má více než jednu šablonu sady Visual Studio, každá šablona je do samostatné složky. Každý soubor v této složce musí mít **akce sestavení** nastavena na **ZipProject**.  
  
## <a name="adding-a-minimal-vsct-file"></a>Přidání souboru minimální .vsct  
 Visual Studio musí být spuštěn v režimu instalační program rozpozná nové nebo upravené šablonu sady Visual Studio. Režim instalační program vyžaduje soubor .vsct nacházet. Proto musíte přidat soubor minimální .vsct do projektu.  
  
1.  Přidání souboru XML s názvem SimpleProject.vsct SimpleProject projektu.  
  
2.  Nahraďte obsah souboru SimpleProject.vsct následujícím kódem.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CommandTable  
      xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable">  
    </CommandTable>  
    ```  
  
3.  Nastavte **akce sestavení** tohoto souboru do **VSCTCompile**. Můžete k tomu jenom v souboru .csproj není v **vlastnosti** okno. Ujistěte se, že **akce sestavení** tohoto souboru je nastaven na **žádné** v tomto okamžiku.  
  
    1.  Klikněte pravým tlačítkem na uzel SimpleProject a pak klikněte na tlačítko **upravit SimpleProject.csproj**.  
  
    2.  V souboru .csproj vyhledejte položku SimpleProject.vsct.  
  
        ```  
        <None Include="SimpleProject.vsct" />  
        ```  
  
    3.  Změňte akci sestavení na **VSCTCompile**.  
  
        ```  
        <VSCTCompile Include="SimpleProject.vsct" />  
        ```  
  
    4.  soubor projektu a ukončete editor.  
  
    5.  Uložte uzlu SimpleProject a pak v **Průzkumníku řešení** klikněte na tlačítko **znovu načíst projekt**.  
  
## <a name="examining-the-visual-studio-template-build-steps"></a>Zkoumání kroky sestavení šablony sady Visual Studio  
 Systém sestavení projektu VSPackage obvykle běží sada Visual Studio v režimu instalace, když dojde ke změně souboru .vstemplate nebo je znovu sestavit projekt, který obsahuje soubor .vstemplate. Můžete absolvovat podle nastavení úrovně podrobností nástroje MSBuild normální nebo vyšší.  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  Rozbalte **projekty a řešení** uzel a potom vyberte **sestavit a spustit**.  
  
3.  Nastavit **výstup sestavení projektu MSBuild podrobností** k **normální**. Click **OK**.  
  
4.  Znovu sestavte projekt SimpleProject.  
  
 Krok sestavení pro vytvoření projektu souboru .zip, měl by vypadat jako v následujícím příkladu.  
  
```  
ZipProjects:  
1>  Zipping ProjectTemplates  
1>  Zipping <path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip...  
1>  Copying file from "<path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip" to "<%LOCALAPPDATA%>\Microsoft\VisualStudio\14.0Exp\ProjectTemplates\\\\SimpleProject.zip".  
1>  Copying file from "<path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip" to "bin\Debug\\ProjectTemplates\\\\SimpleProject.zip".  
1>  SimpleProject -> <path>\SimpleProject\SimpleProject\bin\Debug\ProjectTemplates\SimpleProject.zip  
1>ZipItems:  
1>  Zipping ItemTemplates  
1>  SimpleProject ->  
```  
  
## <a name="deploying-a-visual-studio-template"></a>Nasazení šablony sady Visual Studio  
 Šablony sady Visual Studio neobsahuje informace o cestě. Proto musí být nasazený soubor .zip šablony do umístění, ve kterém se ví, Visual Studio. Umístění složky ProjectTemplates je obvykle  **\<LOCALAPPDATA % > \Microsoft\VisualStudio\14.0Exp\ProjectTemplates**.  
  
 K nasazení vašeho projektu objekt pro vytváření, instalační program musí mít oprávnění správce. Nasazení šablony pod uzlem instalace sady Visual Studio: **...\Microsoft Visual Studio 14.0\Common7\IDE\ProjectTemplates**.  
  
## <a name="testing-a-visual-studio-template"></a>Testování šablony sady Visual Studio  
 Testovací objekt pro vytváření vašeho projektu zobrazíte zda pomocí šablony sady Visual Studio vytvoří projekt hierarchie.  
  
1.  Resetovat experimentální instanci Visual Studio SDK.  
  
     Na [!INCLUDE[win7](../debugger/includes/win7_md.md)]: V nabídce Start najít **Microsoft Visual Studio nebo Microsoft Visual Studio SDK/Tools** složku a potom vyberte **resetovat Microsoft Visual Studio experimentální instanci**.  
  
     V novějších verzích systému Windows: na the úvodní obrazovka, typ **resetovat sady Microsoft Visual Studio \<verze > experimentální instanci**.  
  
2.  Zobrazí se okno příkazového řádku. Až se zobrazí slova `Press any key to continue`, stiskněte ENTER. Po zavření okna, otevřete Visual Studio.  
  
3.  SimpleProject projekt znovu sestavte a spusťte ladění. Zobrazí se experimentální instanci.  
  
4.  V experimentální instance vytvořte projekt SimpleProject. V **nový projekt** dialogové okno, vyberte **SimpleProject**.  
  
5.  Měli byste vidět novou instanci třídy SimpleProject.  
  
 ![](../extensibility/media/simpproj2_newproj.png "SimpProj2_NewProj")  
  
 ![](../extensibility/media/simpproj2_myproj.png "SimpProj2_MyProj")  
  
## <a name="creating-a-project-type-child-node"></a>Vytváření podřízený uzel typu projektu  
 Podřízený uzel můžete přidat do projektu typu uzlu v **nový projekt** dialogové okno.  Pro typ SimpleProject projektu, například můžete mít podřízené uzly pro konzolové aplikace, okno aplikace, webových aplikací a tak dále.  
  
 Podřízené uzly jsou vytvořeny tak, že změna souboru projektu a přidání \<OutputSubPath > podřízené objekty \<ZipProject > elementy. Po zkopírování šablonu během sestavení nebo nasazení stane každých podřízený uzel podsložkou složky šablon projektu.  
  
 V této části ukazuje, jak vytvořit konzoly podřízený uzel typu SimpleProject projektu.  
  
1.  Přejmenujte složku \Templates\Projects\SimpleProject\ \Templates\Projects\ConsoleApp\\.  
  
2.  V **vlastnosti** okně vyberte všechny pět souborů ve složce \Templates\Projects\ConsoleApp\ a zajistěte, aby **akce sestavení** je nastaven na **ZipProject**.  
  
3.  V souboru SimpleProject.vstemplate, přidejte následující řádek na konci \<TemplateData > části, těsně před uzavírací značku.  
  
    ```  
    <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
    ```  
  
     To způsobí, že Šablona konzolové aplikace se objeví v konzole podřízený uzel i v SimpleProject nadřazeného uzlu, která je jednu úroveň nad podřízený uzel.  
  
4.  Uložte soubor SimpleProject.vstemplate.  
  
5.  Do souboru .csproj přidejte \<OutputSubPath > do jednotlivých prvků ZipProject. Uvolnit projekt jako předtím a upravte soubor projektu.  
  
6.  Vyhledejte \<ZipProject > elementy. Ke každému \<ZipProject > elementu, přidejte \<OutputSubPath > elementu a jako hodnotu konzoly. ZipProject  
  
    ```  
    <ZipProject Include="Templates\Projects\ConsoleApp\AssemblyInfo.cs">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\Program.cs">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.myproj">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.vstemplate">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.ico">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>  
    ```  
  
7.  Přidejte tuto \<PropertyGroup > k souboru projektu:  
  
    ```  
    <PropertyGroup>  
      <VsTemplateLanguage>SimpleProject</VsTemplateLanguage>  
    </PropertyGroup>  
    ```  
  
8.  Uložte soubor projektu a projekt znovu načíst.  
  
## <a name="testing-the-project-type-child-node"></a>Testování podřízený uzel typu projektu  
 Testovací soubor upravené projektu zobrazíte jestli **konzoly** podřízený uzel se zobrazí v **nový projekt** dialogové okno.  
  
1.  Spustit **resetovat Visual Studio experimentální instanci Microsoft** nástroj.  
  
2.  SimpleProject projekt znovu sestavte a spusťte ladění. Experimentální instanci by se měla objevit.  
  
3.  V **nový projekt** dialogové okno, klikněte **SimpleProject** uzlu. **Konzolové aplikace** šablona by se zobrazit v **šablony** podokně.  
  
4.  Rozbalte **SimpleProject** uzlu. **Konzoly** by se měla objevit podřízený uzel. **SimpleProject aplikace** šablony i nadále zobrazovat v **šablony** podokně.  
  
5.  . Klikněte na tlačítko **zrušit** a zastavte ladění  
  
 ![](../extensibility/media/simpproj2_rollup.png "SimpProj2_Rollup")  
  
 ![](../extensibility/media/simpproj2_subfolder.png "SimpProj2_Subfolder")  
  
## <a name="substituting-project-template-parameters"></a>Nahraďte parametry šablony projektu  
 [Vytvoření základního systému projektu, část 1](../extensibility/creating-a-basic-project-system-part-1.md) vám ukázal, jak přepsat `ProjectNode.AddFileFromTemplate` metoda udělat základní typ nahrazení parametru šablony. V této části se dozvíte, jaké použití sofistikovanější parametry šablony sady Visual Studio.  
  
 Když vytvoříte pomocí šablony sady Visual Studio v projektu **nový projekt** dialogové okno, šablony, které jsou nahrazeny parametry řetězce k přizpůsobení projektu. Parametr šablony je speciální token, který začíná a končí dolaru, například $time$. Tyto dva parametry jsou užitečné zejména pro povolení přizpůsobení v projektech, které jsou založené na šabloně:  
  
-   $ $GUID [1 – 10] je nahrazena nový identifikátor Guid. Můžete zadat až 10 jedinečné identifikátory GUID, například $guid1$.  
  
-   $safeprojectname$ je název zadaný uživatelem v **nový projekt** dialogové okno, upravit tak, aby odebrat všechny nebezpečné znaky a mezery.  
  
 Úplný seznam parametrů šablony, najdete v části [parametry šablony](../ide/template-parameters.md).  
  
#### <a name="to-substitute-project-template-parameters"></a>K nahrazení parametrů šablony projektu  
  
1.  V souboru SimpleProjectNode.cs, odeberte `AddFileFromTemplate` metoda.  
  
2.  V souboru \Templates\Projects\ConsoleApp\SimpleProject.myproj vyhledejte \<RootNamespace > Vlastnosti a změňte jeho hodnotu na $safeprojectname$.  
  
    ```  
    <RootNamespace>$safeprojectname$</RootNamespace>  
    ```  
  
3.  V souboru \Templates\Projects\SimpleProject\Program.cs nahraďte obsah souboru následujícím kódem:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Runtime.InteropServices;    // Guid  
  
    namespace $safeprojectname$  
    {  
        [Guid("$guid1$")]  
        public class $safeprojectname$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
4.  SimpleProject projekt znovu sestavte a spusťte ladění. Experimentální instanci by se zobrazit.  
  
5.  Vytvořte novou SimpleProject konzolovou aplikaci. (V **typy projektů** podokně, vyberte **SimpleProject**. V části **Visual Studio – nainstalované šablony**, vyberte **konzolové aplikace**.)  
  
6.  V nově vytvořený projekt otevřete Program.cs. Měl by vypadat nějak takto (identifikátor GUID hodnoty v souboru se budou lišit.):  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Runtime.InteropServices;    // Guid  
  
    namespace Console_Application1  
    {  
        [Guid("00000000-0000-0000-00000000-00000000)"]  
        public class Console_Application1  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
## <a name="creating-a-project-property-page"></a>Vytvoření stránky vlastností projektu  
 Stránky vlastností pro typ vašeho projektu můžete vytvořit tak, aby uživatelé mohou zobrazit a změnit vlastnosti v projektech, které jsou založené na šabloně. V této části se dozvíte, jak vytvořit stránky vlastností konfigurace nezávislé. Tato stránka základní vlastnost používá mřížky vlastnosti pro zobrazení veřejné vlastnosti, které zveřejňují ve vaší třídy stránky vlastností.  
  
 Odvození vaší třídy stránky vlastností z `SettingsPage` základní třídy. Mřížky vlastností poskytované `SettingsPage` třídy si je vědoma nejvíce primitivní datové typy a umí je zobrazit.  Kromě toho `SettingsPage` třída umí zachovat hodnoty vlastností pro soubor projektu.  
  
 Stránka vlastností, které vytvoříte v této části vám umožní změnit a uložit tyto vlastnosti projektu:  
  
-   AssemblyName  
  
-   Element OutputType  
  
-   RootNamespace.  
  
1.  V souboru SimpleProjectPackage.cs, přidejte tuto `ProvideObject` atribut `SimpleProjectPackage` třídy:  
  
    ```  
    [ProvideObject(typeof(GeneralPropertyPage))]  
    public sealed class SimpleProjectPackage : ProjectPackage  
    ```  
  
     Takovém postupu zaregistruje třídy stránky vlastností `GeneralPropertyPage` s COM.  
  
2.  V souboru SimpleProjectNode.cs, přidejte tyto dvě přepsané metody do `SimpleProjectNode` třídy:  
  
    ```  
    protected override Guid[] GetConfigurationIndependentPropertyPages()  
    {  
        Guid[] result = new Guid[1];  
        result[0] = typeof(GeneralPropertyPage).GUID;  
        return result;  
    }  
    protected override Guid[] GetPriorityProjectDesignerPages()  
    {  
        Guid[] result = new Guid[1];  
        result[0] = typeof(GeneralPropertyPage).GUID;  
         return result;  
    }  
    ```  
  
     Obě tyto metody vrátí pole stránky vlastností identifikátory GUID.  Identifikátor GUID GeneralPropertyPage je jediným prvkem v poli, proto **stránky vlastností** dialogové okno se zobrazí pouze jednu stránku.  
  
3.  Přidejte soubor třídy s názvem GeneralPropertyPage.cs SimpleProject projektu.  
  
4.  Nahraďte obsah tohoto souboru pomocí následujícího kódu:  
  
    ```  
    using System;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Project;  
    using System.ComponentModel;  
  
    namespace SimpleProject  
    {  
        [ComVisible(true)]  
        [Guid("6BC7046B-B110-40d8-9F23-34263D8D2936")]  
        public class GeneralPropertyPage : SettingsPage  
        {  
            private string assemblyName;  
            private OutputType outputType;  
            private string defaultNamespace;  
  
            public GeneralPropertyPage()  
            {  
                this.Name = "General";  
            }  
  
            [Category("AssemblyName")]  
            [DisplayName("AssemblyName")]  
            [Description("The output file holding assembly metadata.")]  
            public string AssemblyName  
            {  
                get { return this.assemblyName; }  
            }  
            [Category("Application")]  
            [DisplayName("OutputType")]  
            [Description("The type of application to build.")]  
            public OutputType OutputType  
            {  
                get { return this.outputType; }  
                set { this.outputType = value; this.IsDirty = true; }  
            }  
            [Category("Application")]  
            [DisplayName("DefaultNamespace")]  
            [Description("Specifies the default namespace for added items.")]  
            public string DefaultNamespace  
            {  
                get { return this.defaultNamespace; }  
                set { this.defaultNamespace = value; this.IsDirty = true; }  
            }  
  
            protected override void BindProperties()  
            {  
                this.assemblyName = this.ProjectMgr.GetProjectProperty(  
    "AssemblyName", true);  
                this.defaultNamespace = this.ProjectMgr.GetProjectProperty(  
    "RootNamespace", false);  
  
                string outputType = this.ProjectMgr.GetProjectProperty(  
    "OutputType", false);  
                this.outputType =   
    (OutputType)Enum.Parse(typeof(OutputType), outputType);  
            }  
  
            protected override int ApplyChanges()  
            {  
                this.ProjectMgr.SetProjectProperty(  
    "AssemblyName", this.assemblyName);  
                this.ProjectMgr.SetProjectProperty(  
    "OutputType", this.outputType.ToString());  
                this.ProjectMgr.SetProjectProperty(  
    "RootNamespace", this.defaultNamespace);  
                this.IsDirty = false;  
  
                return VSConstants.S_OK;  
            }  
        }  
    }  
    ```  
  
     `GeneralPropertyPage` Třída zpřístupňuje tři veřejné vlastnosti AssemblyName, OutputType a RootNamespace. Protože AssemblyName má žádná metoda set, se zobrazí jako vlastnost jen pro čtení. Element OutputType je vypočtená konstanta, takže se jeví jako rozevíracího seznamu.  
  
     `SettingsPage` Poskytuje základní třídu `ProjectMgr` k uložení vlastností. `BindProperties` Používá metoda `ProjectMgr` k načtení hodnoty trvalého vlastností a nastavení odpovídající vlastnosti.  `ApplyChanges` Používá metoda `ProjectMgr` k získání hodnoty vlastnosti a je uchoval k souboru projektu. Vlastnost nastavena metoda nastaví `IsDirty` na hodnotu true znamená, že vlastnosti mít natrvalo.  Trvalost nastane, když uložíte na projekt nebo řešení.  
  
5.  Znovu sestavte řešení SimpleProject a spusťte ladění. Experimentální instanci by se zobrazit.  
  
6.  V experimentální instanci vytvořte novou aplikaci SimpleProject.  
  
7.  Visual Studio volá vaše pro vytváření projektu pro vytvoření projektu pomocí šablony sady Visual Studio. Nový soubor Program.cs je otevřen v editoru kódu.  
  
8.  Klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení**a potom klikněte na **vlastnosti**. **Stránky vlastností** se zobrazí dialogové okno.  
  
 ![](../extensibility/media/simpproj2_proppage.png "SimpProj2_PropPage")  
  
## <a name="testing-the-project-property-page"></a>Testování stránce vlastností projektu  
 Nyní můžete zkontrolovat, zda můžete upravit a změňte hodnoty vlastností.  
  
1.  V **stránky vlastností MyConsoleApplication** dialogové okno, změny **DefaultNamespace** k **Moje_aplikace**.  
  
2.  Vyberte **OutputType** vlastnost a potom vyberte **knihovny tříd**.  
  
3.  Klikněte na tlačítko **použít**a potom klikněte na **OK**.  
  
4.  Otevřete **stránky vlastností** dialogové okno pole a ověřte, že jsou držena formou změny.  
  
5.  Ukončete experimentální instanci sady Visual Studio.  
  
6.  Znovu otevřete experimentální instanci.  
  
7.  Otevřete **stránky vlastností** dialogové okno pole a ověřte, že jsou držena formou změny.  
  
8.  Ukončete experimentální instanci sady Visual Studio.  
  
 ![](../extensibility/media/simpproj2_proppage2.png "SimpProj2_PropPage2")