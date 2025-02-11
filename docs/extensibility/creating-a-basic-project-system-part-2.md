---
title: Vytvoření systému základního projektu, část 2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- writing a project system
- project system
- tutorial
ms.assetid: aee48fc6-a15f-4fd5-8420-7f18824de220
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d6dfcae8855c2bdb821f61be65de39282db87dfd
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337000"
---
# <a name="create-a-basic-project-system-part-2"></a>Vytvoření systému základního projektu, část 2
První názorný postup v této sérii [vytvoření systému základního projektu, část 1](../extensibility/creating-a-basic-project-system-part-1.md), ukazuje postup vytvoření systému základního projektu. Tento návod vychází systému základního projektu tak, že přidáte šablony sady Visual Studio, stránky vlastností a další funkce. Prvního průvodce musíte dokončit před zahájením tohoto objektu.

Tento návod vás naučí, jak vytvořit typ projektu, který má příponu názvu souboru projektu *.myproj*. Chcete-li dokončit tohoto průvodce, není nutné vytvořit vlastní jazyk, protože návodu vypůjčí z existující systém projektu Visual C#.

Tento návod se naučíte k provedení následujících úkolů:

- Vytvořte šablonu sady Visual Studio.

- Nasazení šablony sady Visual Studio.

- Vytvořit podřízený uzel typu projektu v **nový projekt** dialogové okno.

- Povolte nahrazení parametrů v šabloně Visual Studio.

- Vytvoření stránky vlastností projektu.

> [!NOTE]
> Kroky v tomto názorném postupu jsou založeny na projektu v jazyce C#. S výjimkou konkrétní přípony názvů souborů a kód, můžete však použít stejný postup pro projekt jazyka Visual Basic.

## <a name="create-a-visual-studio-template"></a>Vytvořte šablonu sady Visual Studio
- [Vytvoření systému základního projektu, část 1](../extensibility/creating-a-basic-project-system-part-1.md) ukazuje, jak vytvořit šablonu základního projektu a přidejte do systém projektu. Také ukazuje, jak zaregistrovat pomocí této šablony pomocí sady Visual Studio <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> atribut, který zapisuje úplnou cestu *\\Templates\Projects\SimpleProject\\* složku v systému registru.

Pomocí šablony sady Visual Studio ( *.vstemplate* souboru) namísto šablonu základního projektu, můžete řídit, jak se šablona zobrazuje v **nový projekt** dialogové okno a jak jsou parametry šablony nahrazena. A *.vstemplate* soubor je soubor XML, který popisuje, jak mají být zahrnuty při vytvoření projektu pomocí šablony projektu systému zdrojové soubory. Samotný systém projektu je sestaven tak, že shromažďují *.vstemplate* souboru a zdrojové soubory v *ZIP* souboru a nasadit tak, že zkopírujete *ZIP* do umístění, která je známé sady Visual Studio. Tento proces je vysvětleno podrobněji dále v tomto návodu.

1. V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otevřete řešení SimpleProject, kterou jste vytvořili pomocí následujících [vytvoření systému základního projektu, část 1](../extensibility/creating-a-basic-project-system-part-1.md).

2. V *SimpleProjectPackage.cs* souboru, nalezení ProvideProjectFactory atributu. Nahraďte druhý parametr (název projektu) s hodnotou null a čtvrtý parametr (cesta ke složce šablony projektu) ". \\\NullPath ", následujícím způsobem.

    ```
    [ProvideProjectFactory(typeof(SimpleProjectFactory), null,
        "Simple Project Files (*.myproj);*.myproj", "myproj", "myproj",
        ".\\NullPath",
    LanguageVsTemplate = "SimpleProject")]
    ```

3. Přidejte soubor XML s názvem *SimpleProject.vstemplate* k *\\Templates\Projects\SimpleProject\\* složky.

4. Nahraďte obsah *SimpleProject.vstemplate* následujícím kódem.

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

5. V **vlastnosti** okna, vyberte všechny pět souborů *\\Templates\Projects\SimpleProject\\* složky a nastavení **akce sestavení** k **ZipProject**.

    ![Simple Project Folder](../extensibility/media/simpproj2.png "SimpProj2")

    \<TemplateData > část určuje umístění a vzhled SimpleProject typů projektů v **nový projekt** dialogové okno, následujícím způsobem:

- \<Name > šablony projektu bude aplikace SimpleProject názvy prvků.

- \<Popis > element obsahuje popis, který se zobrazí **nový projekt** dialogové okno při výběru šablony projektu.

- \<Ikonu > prvek určuje ikonu, která se zobrazí spolu s SimpleProject typ projektu.

- \<ProjectType > element názvy typů projektů v **nový projekt** dialogové okno. Tento název se nahradí parametr název projektu ProvideProjectFactory atributu.

  > [!NOTE]
  > \<ProjectType > element musí odpovídat `LanguageVsTemplate` argument `ProvideProjectFactory` atributu v souboru SimpleProjectPackage.cs.

  \<TemplateContent > část popisuje tyto soubory, které jsou generovány při vytvoření nového projektu:

- *SimpleProject.myproj*

- *Program.cs*

- *AssemblyInfo.cs*

  Všechny tři soubory `ReplaceParameters` nastavena na hodnotu true, což umožňuje nahrazení parametru. *Program.cs* soubor má `OpenInEditor` nastavena na hodnotu true, což způsobí, že soubor, který má být otevřen v editoru kódu při vytvoření projektu.

  Další informace o prvcích ve schématu šablony Visual Studio, najdete v článku [odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md).

> [!NOTE]
> Pokud projekt obsahuje více než jedna šablona Visual Studio, každá šablona je do samostatné složky. Musí mít každý soubor v této složce **akce sestavení** nastavena na **ZipProject**.

## <a name="adding-a-minimal-vsct-file"></a>Přidává se soubor minimálního .vsct
 Visual Studio musí být spuštěn v režimu instalace rozpoznat nové nebo upravené šablony sady Visual Studio. Režim instalace vyžaduje *.vsct* soubor má být k dispozici. Je nutné přidat minimální *.vsct* soubor do projektu.

1. Přidejte soubor XML s názvem *SimpleProject.vsct* SimpleProject projektu.

2. Nahraďte obsah *SimpleProject.vsct* souboru následujícím kódem.

    ```
    <?xml version="1.0" encoding="utf-8" ?>
    <CommandTable
      xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable">
    </CommandTable>
    ```

3. Nastavte **akce sestavení** tohoto souboru do **VSCTCompile**. To lze provést pouze v *.csproj* , nikoli v souboru **vlastnosti** okna. Ujistěte se, že **akce sestavení** tohoto souboru nastavena na **žádný** v tomto okamžiku.

    1. Klikněte pravým tlačítkem na uzel SimpleProject a potom klikněte na tlačítko **upravit SimpleProject.csproj**.

    2. V *.csproj* souboru, vyhledejte *SimpleProject.vsct* položky.

        ```
        <None Include="SimpleProject.vsct" />
        ```

    3. Změňte akci sestavení na **VSCTCompile**.

        ```
        <VSCTCompile Include="SimpleProject.vsct" />
        ```

    4. soubor projektu a zavřete editor.

    5. Uložit SimpleProject uzlu a pak v **Průzkumníka řešení** klikněte na tlačítko **znovu načíst projekt**.

## <a name="examine-the-visual-studio-template-build-steps"></a>Prozkoumejte kroky sestavení šablony sady Visual Studio
 Systém sestavení projektu VSPackage obvykle běží v režimu instalace sady Visual Studio při *.vstemplate* změně souboru nebo projektu, který obsahuje *.vstemplate* je znovu soubor sestavit. Můžete absolvovat tak, že nastavíte úroveň podrobností MSBuild na normální nebo vyšší.

1. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.

2. Rozbalte **projekty a řešení** uzlu a pak vyberte **sestavíte a spustíte**.

3. Nastavte **podrobnosti výstupu sestavení projektu nástroje MSBuild** k **normální**. Klikněte na **OK**.

4. Znovu sestavte projekt SimpleProject.

    Krok sestavení vytvořit *ZIP* soubor projektu by měl vypadat podobně jako v následujícím příkladu.

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

## <a name="deploy-a-visual-studio-template"></a>Nasazení šablony sady Visual Studio
Šablony sady Visual Studio neobsahují informace o cestě. Proto se šablona *ZIP* soubor musí být nasazen do umístění, který znáte Visual Studio. Umístění složky ProjectTemplates je obvykle *< % LOCALAPPDATA % > \Microsoft\VisualStudio\14.0Exp\ProjectTemplates*.

Pokud chcete nasadit svůj projekt objekt pro vytváření, instalační program musí mít oprávnění správce. Nasazení šablony uzlu instalace sady Visual Studio: *...\Microsoft Visual Studio 14.0\Common7\IDE\ProjectTemplates*.

## <a name="test-a-visual-studio-template"></a>Test šablony sady Visual Studio
Otestujte svůj projekt objekt pro vytváření zobrazíte, jestli se vytvoří hierarchii projektu pomocí šablony sady Visual Studio.

1. Resetujte experimentální instanci Visual Studio SDK.

    Na [!INCLUDE[win7](../debugger/includes/win7_md.md)]: Na **Start** nabídce Najít **Microsoft Visual Studio nebo Microsoft Visual Studio SDK/Tools** složku a pak vyberte **resetování Microsoft Visual Studio experimentální instanci**.

    V novějších verzích Windows: Na **Start** zadejte **resetování Microsoft Visual Studio \<verze > experimentální instanci**.

2. Zobrazí se okno příkazového řádku. Pokud vidíte text **stisknutím libovolné klávesy pokračovat**, klikněte na tlačítko **ENTER**. Jakmile okno se zavře, otevřete sadu Visual Studio.

3. SimpleProject projekt znovu sestavte a spusťte ladění. Zobrazí se experimentální instance.

4. V experimentální instanci aplikace vytvořte projekt SimpleProject. V **nový projekt** dialogu **SimpleProject**.

5. Měli byste vidět novou instanci třídy SimpleProject.

    ![Jednoduchý projekt novou instanci](../extensibility/media/simpproj2_newproj.png "SimpProj2_NewProj")

    ![My Project New Instance](../extensibility/media/simpproj2_myproj.png "SimpProj2_MyProj")

## <a name="create-a-project-type-child-node"></a>Vytvořit podřízený uzel typu projektu
Můžete přidat podřízený uzel typu uzlu projektu v **nový projekt** dialogové okno. Například pro typ projektu SimpleProject může mít podřízené uzly pro konzolové aplikace, okno aplikace, webové aplikace a tak dále.

Podřízené uzly jsou vytvořeny tak, že změna souboru projektu a přidání \<OutputSubPath > podřízené objekty \<ZipProject > elementy. Kopírování šablony při sestavení nebo nasazení bude každý podřízený uzel podsložkou složky šablony projektu.

Tato část ukazuje, jak vytvořit podřízený uzel typu projektu SimpleProject konzoly.

1. Přejmenovat *\\Templates\Projects\SimpleProject\\* složku  *\\Templates\Projects\ConsoleApp\\* .

2. V **vlastnosti** okna, vyberte všechny pět souborů *\\Templates\Projects\ConsoleApp\\* složky a ujistěte se, že **akce sestavení**je nastavena na **ZipProject**.

3. V souboru SimpleProject.vstemplate, přidejte následující řádek na konci \<TemplateData > části, těsně před uzavírací značku.

    ```
    <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>
    ```

    To způsobí, že šablony Konzolová aplikace se zobrazí v konzole podřízený uzel i v nadřazeném uzlu SimpleProject, která je jednu úroveň nad podřízený uzel.

4. Uložit *SimpleProject.vstemplate* souboru.

5. V *.csproj* přidejte \<OutputSubPath > pro každý prvek ZipProject. Uvolněte projekt jako předtím a upravte soubor projektu.

6. Vyhledejte \<ZipProject > elementy. U každého \<ZipProject > element, přidejte \<OutputSubPath > element a přiřaďte jí hodnotu konzoly. ZipProject

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

7. Přidejte tuto \<PropertyGroup > do souboru projektu:

    ```
    <PropertyGroup>
      <VsTemplateLanguage>SimpleProject</VsTemplateLanguage>
    </PropertyGroup>
    ```

8. Uložte soubor projektu a znovu načíst projekt.

## <a name="test-the-project-type-child-node"></a>Testování podřízený uzel typu projektu
Soubor projektu zobrazíte testu, zda **konzoly** podřízený uzel se zobrazí v **nový projekt** dialogové okno.

1. Spustit **resetování Microsoft Visual Studio experimentální instanci aplikace** nástroj.

2. SimpleProject projekt znovu sestavte a spusťte ladění. Experimentální instanci aplikace by se měla objevit.

3. V **nový projekt** dialogového okna, klikněte na tlačítko **SimpleProject** uzlu. **Konzolovou aplikaci** by se zobrazit v šabloně **šablony** podokně.

4. Rozbalte **SimpleProject** uzlu. **Konzoly** by se měla objevit podřízený uzel. **SimpleProject aplikace** šablony i nadále zobrazovat v **šablony** podokně.

5. Klikněte na tlačítko **zrušit** a Zastavit ladění.

    ![Simple Project Rollup](../extensibility/media/simpproj2_rollup.png "SimpProj2_Rollup")

    ![Jednoduchý projekt konzoly uzlu](../extensibility/media/simpproj2_subfolder.png "SimpProj2_Subfolder")

## <a name="substitute-project-template-parameters"></a>Nahraďte parametry šablony projektu
- [Vytvoření systému základního projektu, část 1](../extensibility/creating-a-basic-project-system-part-1.md) vám ukázal, jak přepsat `ProjectNode.AddFileFromTemplate` metodu základní typ nahrazení parametru šablony. V této části se naučíte používat složitější parametry šablony sady Visual Studio.

Při vytváření projektu pomocí šablony v sadě Visual Studio **nový projekt** dialogové okno, jsou nahrazeny parametry šablony řetězců k přizpůsobení projektu. Parametr šablony je speciální token, který začíná a končí u dolaru, například $time$. Následující dva parametry jsou obzvláště užitečné pro povolení přizpůsobení v projektech, které jsou založeny na šabloně:

- $ $GUID [1-10] se nahradí nový identifikátor Guid. Můžete zadat až 10 jedinečné identifikátory GUID, například $guid1$.

- $safeprojectname$ je zadaný uživatelem na název **nový projekt** dialogovém okně Upravit a odebrat všechny problematické znaky a mezery.

  Úplný seznam parametrů šablony, najdete v části [parametry šablony](../ide/template-parameters.md).

### <a name="to-substitute-project-template-parameters"></a>K nahrazení parametrů šablony projektu

1. V *SimpleProjectNode.cs* soubor, odeberte `AddFileFromTemplate` metody.

2. V  *\\Templates\Projects\ConsoleApp\SimpleProject.myproj* souboru, vyhledejte \<RootNamespace > Vlastnosti a změňte její hodnotu na $safeprojectname$.

    ```
    <RootNamespace>$safeprojectname$</RootNamespace>
    ```

3. V  *\\Templates\Projects\SimpleProject\Program.cs* souboru, nahraďte obsah souboru následujícím kódem:

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

4. SimpleProject projekt znovu sestavte a spusťte ladění. Experimentální instanci aplikace by se zobrazit.

5. Vytvořte novou SimpleProject konzolovou aplikaci. (V **typy projektů** vyberte **SimpleProject**. V části **instalované šablony sady Visual Studio**vyberte **konzolovou aplikaci**.)

6. V nově vytvořeného projektu, otevřete *Program.cs*. Měl by vypadat nějak takto (identifikátor GUID hodnoty v souboru se bude lišit.):

    ```csharp
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

## <a name="create-a-project-property-page"></a>Vytvoření stránky vlastností projektu
Stránky vlastností pro váš typ projektu můžete vytvořit tak, aby uživatelé mohou zobrazit a změnit vlastnosti v projektech, které jsou založeny na šabloně. Tato část ukazuje, jak vytvořit stránku vlastností nezávislé na konfiguraci. Tuto stránku vlastností základní mřížku vlastností používá k zobrazení veřejné vlastnosti, které vystavíte v vaší třídy stránky vlastností.

Odvození vaší třídy stránky vlastností z `SettingsPage` základní třídy. Mřížky vlastností poskytované `SettingsPage` třídy je seznámen nejvíce primitivní datové typy a ví, jak jejich zobrazení. Kromě toho `SettingsPage` třídy ví, jak zachovat hodnoty vlastností do souboru projektu.

Na stránce vlastností, které vytvoříte v této části vám umožní změnit a uložení těchto vlastností projektu:

- AssemblyName

- OutputType

- RootNamespace.

1. V *SimpleProjectPackage.cs* soubor, přidejte tuto `ProvideObject` atribut `SimpleProjectPackage` třídy:

    ```
    [ProvideObject(typeof(GeneralPropertyPage))]
    public sealed class SimpleProjectPackage : ProjectPackage
    ```

    To zaregistruje třídy stránky vlastností `GeneralPropertyPage` pomocí modelu COM.

2. V *SimpleProjectNode.cs* přidejte tyto dvě přepsané metody `SimpleProjectNode` třídy:

    ```csharp
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

    Obě tyto metody vrátí celou řadu vlastností identifikátory GUID. Identifikátor GUID GeneralPropertyPage je jediným prvkem pole, proto **stránky vlastností** dialogové okno se zobrazí pouze jednu stránku.

3. Přidejte soubor třídy s názvem *GeneralPropertyPage.cs* SimpleProject projektu.

4. Obsah tohoto souboru nahraďte následujícím kódem:

    ```csharp
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
                this.assemblyName = this.ProjectMgr.GetProjectProperty("AssemblyName", true);
                this.defaultNamespace = this.ProjectMgr.GetProjectProperty("RootNamespace", false);

                string outputType = this.ProjectMgr.GetProjectProperty("OutputType", false);
                this.outputType = (OutputType)Enum.Parse(typeof(OutputType), outputType);
            }

            protected override int ApplyChanges()
            {
                this.ProjectMgr.SetProjectProperty("AssemblyName", this.assemblyName);
                this.ProjectMgr.SetProjectProperty("OutputType", this.outputType.ToString());
                this.ProjectMgr.SetProjectProperty("RootNamespace", this.defaultNamespace);
                this.IsDirty = false;

                return VSConstants.S_OK;
            }
        }
    }
    ```

    `GeneralPropertyPage` Třída zveřejňuje tři veřejné vlastnosti AssemblyName, element OutputType a RootNamespace. Protože AssemblyName neobsahuje metodu set, zobrazí se jako vlastnost jen pro čtení. OutputType je výčtové konstanty, takže se zobrazí jako rozevíracího seznamu.

    `SettingsPage` Poskytuje základní třídu `ProjectMgr` zachovat vlastnosti. `BindProperties` Používá metoda `ProjectMgr` načíst hodnoty vlastností trvalý a nastavit odpovídající vlastnosti. `ApplyChanges` Používá metoda `ProjectMgr` k získání hodnoty vlastnosti a uložit je trvale v souboru projektu. Vlastnost nastavit metody nastaví `IsDirty` na hodnotu true označuje, že vlastnosti muset nastavit jako trvalý. Trvalost vyvolá se při uložení projektu nebo řešení.

5. Znovu sestavte řešení SimpleProject a spusťte ladění. Experimentální instanci aplikace by se zobrazit.

6. V experimentální instanci aplikace vytvořte novou aplikaci SimpleProject.

7. Visual Studio volá váš projekt factory k vytvoření projektu pomocí šablony sady Visual Studio. Nové *Program.cs* soubor je otevřen v editoru kódu.

8. Klikněte pravým tlačítkem na uzel projektu v **Průzkumníka řešení**a potom klikněte na tlačítko **vlastnosti**. **Stránky vlastností** se zobrazí dialogové okno.

    ![Simple Project Property Page](../extensibility/media/simpproj2_proppage.png "SimpProj2_PropPage")

## <a name="test-the-project-property-page"></a>Testování stránky vlastností projektu
Nyní můžete zkontrolovat, jestli můžete upravit a změnit hodnoty vlastností.

1. V **stránky vlastností MyConsoleApplication** dialogovém okně Změnit **DefaultNamespace** k **MyApplication**.

2. Vyberte **OutputType** vlastnosti a pak vyberte **knihovny tříd**.

3. Klikněte na tlačítko **použít**a potom klikněte na tlačítko **OK**.

4. Znovu otevřít **stránky vlastností** dialogové okno a zkontrolovat, že vaše změny byly trvale zaznamenány.

5. Ukončete experimentální instanci sady Visual Studio.

6. Znovu otevřete experimentální instanci aplikace.

7. Znovu otevřít **stránky vlastností** dialogové okno a zkontrolovat, že vaše změny byly trvale zaznamenány.

8. Ukončete experimentální instanci sady Visual Studio.
    ![Ukončete experimentální instanci](../extensibility/media/simpproj2_proppage2.png "SimpProj2_PropPage2")
