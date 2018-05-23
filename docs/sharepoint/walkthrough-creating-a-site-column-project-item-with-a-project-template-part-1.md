---
title: 'Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint projects, creating custom templates
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f494ef7160d38365643f72cfd1dabfa6cb66d4c3
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1"></a>Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1
  Projekty SharePoint jsou kontejnery pro jednu nebo více položek projektu služby SharePoint. Vytváření vlastních typů položek projektu služby SharePoint a poté je přidružení pomocí šablony projektu můžete rozšířit systému projektu služby SharePoint v sadě Visual Studio. V tomto návodu se definování typu položky projektu pro vytvoření sloupce webu a pak vytvoříte projekt šablonu, která slouží k vytvoření nového projektu, který obsahuje položky projektu sloupce webu.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytváření rozšíření pro Visual Studio, který definuje nový typ položky projektu služby SharePoint pro sloupec lokality. Obsahuje jednoduché vlastní vlastnost, která se zobrazí v typu položky projektu **vlastnosti** okno.  
  
-   Vytváření [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] šablona projektu pro položky projektu.  
  
-   Vytváření [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] rozšíření (VSIX) balíčku pro nasazení v šabloně projektů a rozšíření sestavení.  
  
-   Ladění a testování položky projektu.  
  
 Toto je samostatné návod. Po dokončení tohoto postupu můžete vylepšit položka projektu přidáním průvodce do šablony projektu. Další informace najdete v tématu [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
> [!NOTE]  
>  Můžete si stáhnout ukázku, která obsahuje dokončené projekty, kódu a další soubory v tomto návodu z následujícího umístění: [ http://go.microsoft.com/fwlink/?LinkId=191369 ](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## <a name="prerequisites"></a>Požadavky  
 Následující součásti na vývojovém počítači k dokončení tohoto názorného postupu potřebujete:  
  
-   Podporované edice systému Windows, SharePoint a [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Tento návod používá **projektu VSIX** šablony v sadě SDK k vytvoření balíčku VSIX pro nasazení položka projektu. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Znalostní báze následující konceptu je užitečné, ale není nutné k dokončení průvodce:  
  
-   Sloupce webu ve službě SharePoint. Další informace najdete v tématu [sloupce](http://go.microsoft.com/fwlink/?LinkId=183547).  
  
-   Šablony projektů v sadě Visual Studio. Další informace najdete v tématu [vytváření projektů a šablon položek](/visualstudio/ide/creating-project-and-item-templates).  
  
## <a name="creating-the-projects"></a>Vytváření projektů  
 K dokončení tohoto postupu potřebujete vytvořit tří projektů:  
  
-   Projekt VSIX. Tento projekt vytvoří balíčku VSIX pro nasazení položky projektu sloupce webu a v šabloně projektů.  
  
-   Šablona projektu projektu. Tento projekt vytvoří šablona projektu, který slouží k vytvoření nového projektu služby SharePoint, který obsahuje položky projektu sloupce webu.  
  
-   Projektu knihovny tříd. Tento projekt, který implementuje rozšíření sady Visual Studio, která definuje chování položky projektu sloupce webu.  
  
 Spusťte Průvodce vytvořením projektů.  
  
#### <a name="to-create-the-vsix-project"></a>Vytvoření projektu VSIX  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
3.  V horní části **nový projekt** dialogové okno pole, ujistěte se, že **rozhraní .NET Framework 4.5** je vybrán v seznamu verze rozhraní .NET Framework.  
  
4.  Rozbalte **jazyka Visual Basic** nebo **Visual C#** uzly a potom zvolte **rozšiřitelnost** uzlu.  
  
    > [!NOTE]  
    >  **Rozšiřitelnost** uzel je k dispozici pouze v případě, že nainstalujete Visual Studio SDK. Další informace najdete v části požadavky dříve v tomto tématu.  
  
5.  V seznamu šablon projektu, zvolte **projektu VSIX**.  
  
6.  V **název** zadejte **SiteColumnProjectItem**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **SiteColumnProjectItem** projektu do **Průzkumníku řešení**.  
  
#### <a name="to-create-the-project-template-project"></a>Vytvoření projektu šablony projektu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V horní části **nový projekt** dialogové okno pole, ujistěte se, že **rozhraní .NET Framework 4.5** je vybrán v seznamu verze rozhraní .NET Framework.  
  
3.  Rozbalte **Visual C#** nebo **jazyka Visual Basic** uzel a potom zvolte **rozšiřitelnost** uzlu.  
  
4.  V seznamu šablon projektu, vyberte **šablona projektu C#** nebo **šablona projektu jazyka Visual Basic** šablony.  
  
5.  V **název** zadejte **SiteColumnProjectTemplate**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **SiteColumnProjectTemplate** projektu k řešení.  
  
6.  Odstraňte soubor kódu Class1 z projektu.  
  
7.  Pokud jste vytvořili projektu jazyka Visual Basic, také odstraňte následující soubory z projektu:  
  
    -   MyApplication.Designer.vb  
  
    -   MyApplication.myapp  
  
    -   Resources.Designer.vb  
  
    -   Resources.resx  
  
    -   Settings.Designer.vb  
  
    -   Settings.Settings  
  
#### <a name="to-create-the-extension-project"></a>Vytvoření projektu rozšíření  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V horní části **nový projekt** dialogové okno pole, ujistěte se, že **rozhraní .NET Framework 4.5** je vybrán v seznamu verze rozhraní .NET Framework.  
  
3.  Rozbalte **Visual C#** nebo **jazyka Visual Basic** uzlů, zvolte **Windows** uzel a potom zvolte **knihovny tříd** šablony.  
  
4.  V **název** zadejte **ProjectItemTypeDefinition** a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **ProjectItemTypeDefinition** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
5.  Odstraňte soubor kódu Class1 z projektu.  
  
## <a name="configuring-the-extension-project"></a>Konfigurace projektu rozšíření  
 Přidáte soubory kódu a odkazy na sestavení ke konfiguraci rozšíření projektu.  
  
#### <a name="to-configure-the-project"></a>Konfigurace projektu  
  
1.  V projektu ProjectItemTypeDefinition přidat souboru kódu, který je pojmenován **SiteColumnProjectItemTypeProvider**.  
  
2.  Na řádku nabídek zvolte **projektu**, **přidat odkaz na**.  
  
3.  V **správce odkazů - ProjectItemTypeDefinition** dialogové okno, rozbalte seznam **sestavení** uzlu, vyberte **Framework** uzel a potom vyberte System.ComponentModel.Composition zaškrtávací políčko.  
  
4.  Vyberte **rozšíření** uzlu, zaškrtněte políčko vedle sestavení Microsoft.VisualStudio.SharePoint a zvolte **OK** tlačítko.  
  
## <a name="defining-the-new-sharepoint-project-item-type"></a>Definování nového typu položky projektu SharePoint  
 Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> rozhraní k definování chování nového typu položky projektu. Toto rozhraní implementujte vždy, když chcete k definování nového typu položky projektu.  
  
#### <a name="to-define-the-new-sharepoint-project-item-type"></a>Chcete-li definovat nové typu položky projektu SharePoint  
  
1.  V **SiteColumnProjectItemTypeProvider** kód souboru, ve výchozím kódu nahraďte následujícím kódem a pak soubor uložte.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#1](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projectitemtypedefinition/sitecolumnprojectitemtypeprovider.cs#1)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#1](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projectitemtypedefinition/sitecolumnprojectitemtypeprovider.vb#1)]  
  
## <a name="creating-a-visual-studio-project-template"></a>Vytvoření šablony projektů sady Visual Studio  
 Vytvořením šablony projektu povolíte jinými vývojáři k vytváření projektů služby SharePoint, které obsahují položky projektu sloupce webu. Šablona projektu služby SharePoint obsahuje soubory, které jsou požadovány pro všechny projekty v sadě Visual Studio, jako je například .csproj nebo .vbproj a soubory .vstemplate a soubory, které jsou specifické pro projekty SharePoint. Další informace najdete v tématu [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 V tomto postupu můžete vytvořit prázdný projekt SharePoint pro vygenerování souborů, které jsou specifické pro projekty SharePoint. Potom přidáte tyto soubory do projektu SiteColumnProjectTemplate tak, že jsou zahrnuté v šabloně, které se generují z tohoto projektu. Můžete také nakonfigurovat soubor projektu SiteColumnProjectTemplate k určení, kde se zobrazí v šabloně projektů **nový projekt** dialogové okno.  
  
#### <a name="to-create-the-files-for-the-project-template"></a>Postup vytvoření souborů šablony projektu  
  
1.  Spusťte druhou instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] s přihlašovacími údaji správce.  
  
2.  Vytvoření projektu služby SharePoint 2010 s názvem **BaseSharePointProject**.  
  
    > [!IMPORTANT]  
    >  V **Průvodce vlastním nastavením SharePoint**, nevybírejte **nasadit jako řešení farmy** tlačítko.  
  
3.  Přidání položky prázdný Element do projektu s názvem položka **pole1**.  
  
4.  Uložte projekt a pak zavřete druhou instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
5.  V instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] , otevřete řešení SiteColumnProjectItem, má v **Průzkumníku řešení**, otevřete místní nabídku pro **SiteColumnProjectTemplate** uzel projektu, zvolte  **Přidat**a potom zvolte **existující položka**.  
  
6.  V **přidat existující položku** dialogové okno, otevřete seznam přípon souborů a potom zvolte **všechny soubory (\*.\*)** .  
  
7.  V adresáři, který obsahuje BaseSharePointProject projekt, vyberte soubor key.snk a potom zvolte **přidat** tlačítko.  
  
    > [!NOTE]  
    >  Šablona projektu, který vytvoříte v tomto návodu používá stejný soubor key.snk k podepsání každý projekt, který je vytvořen pomocí šablony. Další způsob, jak rozbalit Tato ukázka vytvořit různé key.snk soubor pro každou instanci projektu najdete v tématu [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
8.  Opakujte kroky 5 až 8 přidejte následující soubory ze zadaného podsložky v adresáři BaseSharePointProject:  
  
    -   \Field1\Elements.XML  
  
    -   \Field1\SharePointProjectItem.spdata  
  
    -   \Features\Feature1\Feature1.Feature  
  
    -   \Features\Feature1\Feature1.template.XML  
  
    -   \Package\Package.Package  
  
    -   \Package\Package.template.XML  
  
     Přidejte tyto soubory přímo do projektu SiteColumnProjectTemplate; nemusíte znovu vytvořit podsložky pole1, funkce nebo balíček v projektu. Další informace o těchto souborech najdete v tématu [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
#### <a name="to-configure-how-developers-discover-the-project-template-in-the-new-project-dialog-box"></a>Ke konfiguraci, jak vývojáři zjistit šablona projektu v dialogovém okně Nový projekt  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **SiteColumnProjectTemplate** uzel projektu a potom zvolte **uvolnit projekt**. Pokud se zobrazí výzva se uložit změny do všechny soubory, vyberte **Ano** tlačítko.  
  
2.  Otevřete místní nabídku pro **SiteColumnProjectTemplate** uzel znovu a potom zvolte **upravit SiteColumnProjectTemplate.csproj** nebo **upravit SiteColumnProjectTemplate.vbproj**.  
  
3.  V souboru projektu, vyhledejte následující `VSTemplate` elementu.  
  
    ```xml  
    <VSTemplate Include="SiteColumnProjectTemplate.vstemplate">  
    ```  
  
4.  Tento element nahraďte následující kód XML.  
  
    ```xml  
    <VSTemplate Include="SiteColumnProjectTemplate.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` Element určuje další složky v cestě, pod kterým je vytvořena šablona projektu při sestavování projektu. Zde určené složky zajistí, že šablona projektu bude k dispozici jenom v případě, že zákazníci otevřete **nový projekt** dialogové okno, rozbalte seznam **SharePoint** uzel a potom vyberte **2010**  uzlu.  
  
5.  Soubor uložte a zavřete.  
  
6.  V **Průzkumníku řešení**, otevřete místní nabídku pro **SiteColumnProjectTemplate** projektu a potom vyberte **znovu načíst projekt**.  
  
## <a name="editing-the-project-template-files"></a>Úpravy souborů projektu šablony  
 V projektu SiteColumnProjectTemplate upravte následující soubory pro definování chování projektu šablony:  
  
-   AssemblyInfo.cs nebo AssemblyInfo.vb  
  
-   Elements.XML  
  
-   SharePointProjectItem.spdata  
  
-   Feature1.Feature  
  
-   Package.Package  
  
-   SiteColumnProjectTemplate.vstemplate  
  
-   ProjectTemplate.csproj nebo ProjectTemplate.vbproj  
  
 V následujících postupech přidáte nahraditelné parametry k některé z těchto souborů. Nahraditelné parametr je token, který se spustí a končí znak dolaru ($). Pokud uživatel používá tato šablona projektu pro vytvoření projektu, Visual Studio automaticky nahradí tyto parametry v novém projektu s konkrétními hodnotami. Další informace najdete v tématu [nahraditelné parametry](../sharepoint/replaceable-parameters.md).  
  
#### <a name="to-edit-the-assemblyinfocs-or-assemblyinfovb-file"></a>Chcete-li upravit soubor AssemblyInfo.cs nebo AssemblyInfo.vb  
  
1.  V projektu SiteColumnProjectTemplate otevřete soubor AssemblyInfo.cs nebo AssemblyInfo.vb a potom přidejte následující příkaz na začátek:  
  
    ```vb  
    Imports System.Security  
    ```  
  
    ```csharp  
    using System.Security;  
    ```  
  
     Při **řešení v izolovaném prostoru** projektu služby SharePoint je nastavena na **True**, Visual Studio. přidá <xref:System.Security.AllowPartiallyTrustedCallersAttribute> do souboru AssemblyInfo kódu. Však nepodporuje import souboru AssemblyInfo kódu v šabloně projektů <xref:System.Security> oboru názvů ve výchozím nastavení. To je nutné přidat **pomocí** nebo **importy** příkaz, aby se zabránilo chyby kompilace.  
  
2.  Soubor uložte a zavřete.  
  
#### <a name="to-edit-the-elementsxml-file"></a>Chcete-li upravit soubor Elements.xml  
  
1.  V projektu SiteColumnProjectTemplate nahraďte obsah souboru Elements.xml následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <Field ID="{$guid5$}"   
          Name="$safeprojectname$"   
          DisplayName="$projectname$"   
          Type="Text"   
          Group="Custom Columns">  
      </Field>  
    </Elements>  
    ```  
  
     Přidá nový soubor XML `Field` element, který definuje název sloupce webu, jeho základní typ a skupinu, ve které seznam sloupec webu v galerii. Další informace o obsahu tohoto souboru najdete v tématu [pole definice schématu](http://go.microsoft.com/fwlink/?LinkId=184290).  
  
2.  Soubor uložte a zavřete.  
  
#### <a name="to-edit-the-sharepointprojectitemspdata-file"></a>Chcete-li upravit soubor SharePointProjectItem.spdata  
  
1.  V projektu SiteColumnProjectTemplate nahraďte obsah souboru SharePointProjectItem.spdata následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <ProjectItem Type="Contoso.SiteColumn" DefaultFile="Elements.xml"   
                 xmlns="http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel">  
      <Files>  
        <ProjectItemFile Source="Elements.xml" Target="$safeprojectname$\" Type="ElementManifest" />  
      </Files>   
    </ProjectItem>  
    ```  
  
     Nové XML provede tyto změny do souboru:  
  
    -   Změny `Type` atribut `ProjectItem` element na stejném řetězci, který je předán <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute> v definici položky projektu ( `SiteColumnProjectItemTypeProvider` třídu, která jste vytvořili dříve v tomto návodu).  
  
    -   Odebere `SupportedTrustLevels` a `SupportedDeploymentScopes` atributy z `ProjectItem` elementu. Tyto hodnoty atributů nejsou potřeba, protože úrovně důvěryhodnosti a nasazení obory jsou určené v `SiteColumnProjectItemTypeProvider` třídy ProjectItemTypeDefinition projektu.  
  
     Další informace o obsahu soubory .spdata najdete v tématu [referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md).  
  
2.  Soubor uložte a zavřete.  
  
#### <a name="to-edit-the-feature1feature-file"></a>Chcete-li upravit soubor Feature1.feature  
  
1.  V projektu SiteColumnProjectTemplate nahraďte obsah souboru Feature1.feature následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <feature xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0" Id="$guid4$" featureId="$guid4$"   
             imageUrl="" solutionId="00000000-0000-0000-0000-000000000000" title="Site Column Feature1" version=""  
             deploymentPath="$SharePoint.Project.FileNameWithoutExtension$_$SharePoint.Feature.FileNameWithoutExtension$"  
             xmlns="http://schemas.microsoft.com/VisualStudio/2008/SharePointTools/FeatureModel">  
      <projectItems>  
        <projectItemReference itemId="$guid2$" />  
      </projectItems>  
    </feature>  
    ```  
  
     Nové XML provede tyto změny do souboru:  
  
    -   Změní hodnoty `Id` a `featureId` atributy `feature` element `$guid4$`.  
  
    -   Změní hodnoty `itemId` atribut `projectItemReference` element `$guid2$`.  
  
     Další informace o souborech .feature najdete v tématu [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
2.  Soubor uložte a zavřete.  
  
#### <a name="to-edit-the-packagepackage-file"></a>Chcete-li upravit soubor Package.package  
  
1.  V projektu SiteColumnProjectTemplate nahraďte obsah souboru Package.package následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <package xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0"   
             Id="$guid3$" solutionId="$guid3$" resetWebServer="false" name="$safeprojectname$"   
             xmlns="http://schemas.microsoft.com/VisualStudio/2008/SharePointTools/PackageModel">  
      <features>  
        <featureReference itemId="$guid4$" />  
      </features>  
    </package>  
    ```  
  
     Nové XML provede tyto změny do souboru:  
  
    -   Změní hodnoty `Id` a `solutionId` atributy `package` element `$guid3$`.  
  
    -   Změní hodnoty `itemId` atribut `featureReference` element `$guid4$`.  
  
     Další informace o souborech .package najdete v tématu [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
2.  Soubor uložte a zavřete.  
  
#### <a name="to-edit-the-sitecolumnprojecttemplatevstemplate-file"></a>Chcete-li upravit soubor SiteColumnProjectTemplate.vstemplate  
  
1.  V projektu SiteColumnProjectTemplate nahraďte obsah souboru SiteColumnProjectTemplate.vstemplate s jedním z těchto částí XML.  
  
    -   Pokud vytváříte šablonu projekt Visual C#, použijte následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Project">  
      <TemplateData>  
        <Name>Site Column</Name>  
        <Description>Creates a new site column in SharePoint</Description>  
        <FrameworkVersion>3.5</FrameworkVersion>  
        <ProjectType>CSharp</ProjectType>  
        <CreateNewFolder>true</CreateNewFolder>  
        <CreateInPlace>true</CreateInPlace>  
        <ProvideDefaultName>true</ProvideDefaultName>  
        <DefaultName>SiteColumn</DefaultName>  
        <LocationField>Enabled</LocationField>  
        <EnableLocationBrowseButton>true</EnableLocationBrowseButton>  
        <PromptForSaveOnCreation>true</PromptForSaveOnCreation>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <Icon>SiteColumnProjectTemplate.ico</Icon>  
        <SortOrder>1000</SortOrder>  
      </TemplateData>  
      <TemplateContent>  
        <Project TargetFileName="SharePointProject1.csproj" File="ProjectTemplate.csproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" TargetFileName="Properties\AssemblyInfo.cs">AssemblyInfo.cs</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.feature">Feature1.feature</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.Template.xml">Feature1.template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.package">Package.package</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.Template.xml">Package.Template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\SharePointProjectItem.spdata">SharePointProjectItem.spdata</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\Elements.xml" OpenInEditor="true">Elements.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
    -   Pokud vytváříte šablonu projektu jazyka Visual Basic, použijte následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Project">  
      <TemplateData>  
        <Name>Site Column</Name>  
        <Description>Creates a new site column in SharePoint</Description>  
        <FrameworkVersion>3.5</FrameworkVersion>  
        <ProjectType>VisualBasic</ProjectType>  
        <CreateNewFolder>true</CreateNewFolder>  
        <CreateInPlace>true</CreateInPlace>  
        <ProvideDefaultName>true</ProvideDefaultName>  
        <DefaultName>SiteColumn</DefaultName>  
        <LocationField>Enabled</LocationField>  
        <EnableLocationBrowseButton>true</EnableLocationBrowseButton>  
        <PromptForSaveOnCreation>true</PromptForSaveOnCreation>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <Icon>SiteColumnProjectTemplate.ico</Icon>  
        <SortOrder>1000</SortOrder>  
      </TemplateData>  
      <TemplateContent>  
        <Project TargetFileName="SharePointProject1.vbproj" File="ProjectTemplate.vbproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" TargetFileName="My Project\AssemblyInfo.vb">AssemblyInfo.vb</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.feature">Feature1.feature</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.Template.xml">Feature1.template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.package">Package.package</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.Template.xml">Package.Template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\SharePointProjectItem.spdata">SharePointProjectItem.spdata</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\Elements.xml" OpenInEditor="true">Elements.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
     Nové XML provede tyto změny do souboru:  
  
    -   Nastaví `Name` prvku na hodnotu **sloupec lokality**. (Tento název se zobrazí v **nový projekt** dialogové okno).  
  
    -   Přidá `ProjectItem` prvky pro každý filethat je součástí každá instance projektu.  
  
    -   Používá obor názvů "http://schemas.microsoft.com/developer/vstemplate/2005". Ostatní soubory projektu v tomto řešení "http://schemas.microsoft.com/developer/msbuild/2003" oboru názvů. Proto se budou generovat zprávy upozornění schématu XML, ale je v tomto návodu můžete ignorovat.  
  
     Další informace o obsahu soubory .vstemplate najdete v tématu [Visual Studio odkaz na schéma šablon](/visualstudio/extensibility/visual-studio-template-schema-reference).  
  
2.  Soubor uložte a zavřete.  
  
#### <a name="to-edit-the-projecttemplatecsproj-or-projecttemplatevbproj-file"></a>Chcete-li upravit soubor ProjectTemplate.csproj nebo ProjectTemplate.vbproj  
  
1.  V projektu SiteColumnProjectTemplate nahraďte obsah souboru ProjectTemplate.csproj nebo ProjectTemplate.vbproj soubor s jedním z těchto částí XML.  
  
    -   Pokud vytváříte šablonu projekt Visual C#, použijte následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <SchemaVersion>2.0</SchemaVersion>  
        <ProjectGuid>{$guid1$}</ProjectGuid>  
        <OutputType>Library</OutputType>  
        <AppDesignerFolder>Properties</AppDesignerFolder>  
        <RootNamespace>$safeprojectname$</RootNamespace>  
        <AssemblyName>$safeprojectname$</AssemblyName>  
        <TargetFrameworkVersion>v3.5</TargetFrameworkVersion>  
        <FileAlignment>512</FileAlignment>  
        <ProjectTypeGuids>{BB1F664B-9266-4fd6-B973-E1E44974B511};{14822709-B5A1-4724-98CA-57A101D1B079};{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}</ProjectTypeGuids>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineConstants>DEBUG;TRACE</DefineConstants>  
        <ErrorReport>prompt</ErrorReport>  
        <WarningLevel>4</WarningLevel>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">  
        <DebugType>pdbonly</DebugType>  
        <Optimize>true</Optimize>  
        <OutputPath>bin\Release\</OutputPath>  
        <DefineConstants>TRACE</DefineConstants>  
        <ErrorReport>prompt</ErrorReport>  
        <WarningLevel>4</WarningLevel>  
      </PropertyGroup>  
      <PropertyGroup>  
        <SignAssembly>true</SignAssembly>  
        <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="System" />  
        <Reference Include="System.Core" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Data.DataSetExtensions" />  
        <Reference Include="System.Web" />  
        <Reference Include="System.Xml" />  
        <Reference Include="System.Xml.Linq" />  
        <Reference Include="Microsoft.SharePoint" />  
        <Reference Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="Properties\AssemblyInfo.cs" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Field1\SharePointProjectItem.spdata">  
          <SharePointProjectItemId>{$guid2$}</SharePointProjectItemId>  
        </None>  
        <None Include="Field1\Elements.xml" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="key.snk" />  
        <None Include="Package\Package.package">  
          <PackageId>{$guid3$}</PackageId>  
        </None>  
        <None Include="Package\Package.Template.xml">  
          <DependentUpon>Package.package</DependentUpon>  
        </None>  
        <None Include="Features\Feature1\Feature1.feature">  
          <FeatureId>{$guid4$}</FeatureId>  
        </None>  
        <None Include="Features\Feature1\Feature1.Template.xml">  
          <DependentUpon>Feature1.feature</DependentUpon>  
        </None>  
      </ItemGroup>  
      <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />  
      <Import Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v10.0\SharePointTools\Microsoft.VisualStudio.SharePoint.targets" />  
    </Project>  
    ```  
  
    1.  Pokud vytváříte šablonu projektu jazyka Visual Basic, použijte následující kód XML.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <ProductVersion>  
        </ProductVersion>  
        <SchemaVersion>  
        </SchemaVersion>  
        <ProjectGuid>{$guid1$}</ProjectGuid>  
        <OutputType>Library</OutputType>  
        <RootNamespace>$safeprojectname$</RootNamespace>  
        <AssemblyName>$safeprojectname$</AssemblyName>  
        <TargetFrameworkVersion>v3.5</TargetFrameworkVersion>  
        <FileAlignment>512</FileAlignment>  
        <ProjectTypeGuids>{BB1F664B-9266-4fd6-B973-E1E44974B511};{D59BE175-2ED0-4C54-BE3D-CDAA9F3214C8};{F184B08F-C81C-45F6-A57F-5ABD9991F28F}</ProjectTypeGuids>  
        <OptionExplicit>On</OptionExplicit>  
        <OptionCompare>Binary</OptionCompare>  
        <OptionStrict>Off</OptionStrict>  
        <OptionInfer>On</OptionInfer>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <OutputPath>bin\Debug\</OutputPath>  
        <WarningLevel>4</WarningLevel>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">  
        <DebugType>pdbonly</DebugType>  
        <DefineDebug>false</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <Optimize>true</Optimize>  
        <OutputPath>bin\Release\</OutputPath>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup>  
        <SignAssembly>true</SignAssembly>  
        <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="System" />  
        <Reference Include="System.Core" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Data.DataSetExtensions" />  
        <Reference Include="System.Xml" />  
        <Reference Include="System.Xml.Linq" />  
        <Reference Include="Microsoft.SharePoint" />  
        <Reference Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Import Include="Microsoft.VisualBasic" />  
        <Import Include="System" />  
        <Import Include="System.Collections" />  
        <Import Include="System.Collections.Generic" />  
        <Import Include="System.Data" />  
        <Import Include="System.Diagnostics" />  
        <Import Include="System.Linq" />  
        <Import Include="System.Xml.Linq" />  
        <Import Include="Microsoft.SharePoint" />  
        <Import Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="My Project\AssemblyInfo.vb" />  
      </ItemGroup>  
      <ItemGroup>  
        <AppDesigner Include="My Project\" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Features\Feature1\Feature1.feature">  
          <FeatureId>{$guid4$}</FeatureId>  
        </None>  
        <None Include="Field1\SharePointProjectItem.spdata">  
          <SharePointProjectItemId>{$guid2$}</SharePointProjectItemId>  
        </None>  
        <None Include="key.snk" />  
        <None Include="Package\Package.package">  
          <PackageId>{$guid3$}</PackageId>  
        </None>  
        <None Include="Package\Package.Template.xml">  
          <DependentUpon>Package.package</DependentUpon>  
        </None>  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Features\Feature1\Feature1.Template.xml">  
          <DependentUpon>Feature1.feature</DependentUpon>  
        </None>  
        <None Include="Field1\Elements.xml" />  
      </ItemGroup>  
      <Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />  
      <Import Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v10.0\SharePointTools\Microsoft.VisualStudio.SharePoint.targets" />  
    </Project>  
    ```  
  
     Nové XML provede tyto změny do souboru:  
  
    -   Používá `TargetFrameworkVersion` elementu, který chcete zadat rozhraní .NET Framework 3.5, ne 4.5.  
  
    -   Přidá `SignAssembly` a `AssemblyOriginatorKeyFile` prvky pro přihlášení výstup projektu.  
  
    -   Přidá `Reference` prvky pro sestavení odkazuje využívající projektů služby SharePoint.  
  
    -   Přidá elementy pro každý soubor výchozí v projektu, například Elements.xml a SharePointProjectItem.spdata.  
  
2.  Soubor uložte a zavřete.  
  
## <a name="creating-a-vsix-package-to-deploy-the-project-template"></a>Vytvoření balíčku VSIX pro nasazení v šabloně projektů  
 Chcete-li nasadit rozšíření, použijte VSIX projekt v **SiteColumnProjectItem** řešení k vytvoření balíčku VSIX. Nejprve nakonfigurujte balíčku VSIX úpravou souboru source.extension.vsixmanifest, který je zahrnutý v projektu VSIX. Pak vytvořte balíčku VSIX vytvořením řešení.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Ke konfiguraci a vytvoření balíčku VSIX  
  
1.  V **Průzkumníku řešení**v **SiteColumnProjectItem** projektu, otevřete soubor source.extension.vsixmanifest v editoru manifestu.  
  
     Soubor source.extension.vsixmanifest je základem pro soubor extension.vsixmanifest, které vyžadují všechny balíčky VSIX. Další informace o tento soubor najdete v tématu [VSIX rozšíření schématu 1.0 odkaz](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  V **název produktu** zadejte **sloupec lokality**.  
  
3.  V **Autor** zadejte **Contoso**.  
  
4.  V **popis** zadejte **projektu služby SharePoint A pro vytváření sloupců webu**.  
  
5.  Vyberte **prostředky** a pak klikněte na příkaz **nový** tlačítko.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
6.  V **typ** vyberte **Microsoft.VisualStudio.ProjectTemplate**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `ProjectTemplate` element v souboru extension.vsixmanifest. Tento element identifikuje podsložku v balíčku VSIX, který obsahuje šablona projektu. Další informace najdete v tématu [ProjectTemplate Element (VSX schéma)](http://msdn.microsoft.com/en-us/87add64c-9dcd-495f-8815-209dab182cb1).  
  
7.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
8.  V **projektu** seznam a vyberte **SiteColumnProjectTemplate**a potom zvolte **OK** tlačítko.  
  
9. Vyberte **nový** tlačítko znovu.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
10. V **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `MefComponent` element v souboru extension.vsixmanifest. Tento element určuje název sestavení rozšíření v balíčku VSIX. Další informace najdete v tématu [MEFComponent Element (VSX schéma)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
11. V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
12. V **projektu** vyberte **ProjectItemTypeDefinition**a potom zvolte **OK** tlačítko.  
  
13. Na řádku nabídek zvolte **sestavení**, **sestavit řešení**a pak se ujistěte, že projekt zkompiluje bez chyb.  
  
## <a name="testing-the-project-template"></a>Testování v šabloně projektů  
 Nyní jste připraveni k testování v šabloně projektů. Nejprve spusťte ladění řešení SiteColumnProjectItem v experimentální instanci sady Visual Studio. Pak test **sloupec lokality** projektu v experimentální instanci sady Visual Studio. Nakonec sestavte a spusťte projektu služby SharePoint k ověření, že sloupec lokality funguje podle očekávání.  
  
#### <a name="to-start-debugging-the-solution"></a>Spustit ladění řešení  
  
1.  Restartujte Visual Studio s přihlašovacími údaji správce a pak otevřete SiteColumnProjectItem řešení.  
  
2.  
  
3.  Do souboru kódu SiteColumnProjectItemTypeProvider přidejte zarážku na první řádek kódu `InitializeType` metoda a potom zvolte **F5** klíč spustit ladění.  
  
     Visual Studio nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\Site Column\1.0 a spustí experimentální instanci sady Visual Studio. Položka projektu budete testovat v této instanci sady Visual Studio.  
  
#### <a name="to-test-the-project-in-visual-studio"></a>K testování projektu v sadě Visual Studio  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  Rozbalte položku **Visual C#** nebo **jazyka Visual Basic** uzlu (v závislosti na jazyce, který podporuje vaše šablona projektu), rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
3.  V seznamu šablon projektu, vyberte **sloupec lokality** šablony.  
  
4.  V **název** zadejte **SiteColumnTest** a potom zvolte **OK** tlačítko.  
  
     V **Průzkumníku řešení**, zobrazí se nový projekt se položka projektu s názvem **pole1**.  
  
5.  Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou jste nastavili výše v `InitializeType` metoda a potom zvolte **F5** klíče a pokračujte ladění projektu.  
  
6.  V **Průzkumníku řešení**, vyberte **pole1** uzel a potom zvolte **F4** klíč.  
  
     **Vlastnosti** otevře se okno.  
  
7.  V seznamu vlastností, ověřte, že vlastnost **Příklad vlastnosti** se zobrazí.  
  
#### <a name="to-test-the-site-column-in-sharepoint"></a>K testování sloupec webu ve službě SharePoint  
  
1.  V **Průzkumníku řešení**, vyberte **SiteColumnTest** uzlu.  
  
2.  V **vlastnosti** okno, do textového pole, která je vedle **adresa URL webu** vlastnost, zadejte **http://localhost**.  
  
     Tento krok určuje místní web služby SharePoint na vývojovém počítači, který chcete použít pro ladění.  
  
    > [!NOTE]  
    >  **Adresa URL webu** vlastnost je prázdná ve výchozím nastavení, protože šablona projektu sloupce webu neposkytuje průvodce pro shromažďování tuto hodnotu, při vytváření projektu. Informace o postupu přidání průvodce, který se vás vývojáře pro tuto hodnotu a pak tato vlastnost nakonfiguruje v novém projektu, najdete v tématu [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
3.  Vyberte **F5** klíč.  
  
     Sloupec lokality se zabalí a nasazené na web služby SharePoint, který je uveden v **adresa URL webu** vlastnosti projektu. Otevře se webový prohlížeč na stránku výchozího tohoto webu.  
  
    > [!NOTE]  
    >  Pokud **ladění skriptů zakázáno** se zobrazí dialogové okno, vyberte **Ano** tlačítka pokračujte ladění projektu.  
  
4.  Na **Akce webu** nabídce zvolte **nastavení lokality**.  
  
5.  Na **nastavení lokality** v části **galerií** seznam, vyberte **sloupce webu** odkaz.  
  
6.  V seznamu sloupců webu, ověřte, že **vlastní sloupce** skupina obsahuje sloupec s názvem **SiteColumnTest**.  
  
7.  Zavřete webový prohlížeč.  
  
## <a name="cleaning-up-the-development-computer"></a>Čištění vývojovém počítači  
 Po dokončení testování projektu, odeberte v šabloně projektů z experimentální instanci sady Visual Studio.  
  
#### <a name="to-clean-up-the-development-computer"></a>Vyčistěte vývojovém počítači  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **nástroje**, **rozšíření a aktualizace**.  
  
     **Rozšíření a aktualizace** otevře se dialogové okno.  
  
2.  V seznamu rozšíření, vyberte **sloupec lokality** rozšíření a potom zvolte **odinstalovat** tlačítko.  
  
3.  V dialogovém okně, které se zobrazí, vyberte **Ano** tlačítko potvrďte, že chcete odinstalovat rozšíření.  
  
4.  Vyberte **Zavřít** tlačítko k dokončení odinstalace.  
  
5.  Zavřete obě instance sady Visual Studio (experimentální instance a instance sady Visual Studio, ve kterém je otevřen SiteColumnProjectItem řešení).  
  
## <a name="next-steps"></a>Další kroky  
 Po dokončení tohoto postupu můžete přidat do šablony projektu průvodce. Když uživatel vytvoří projektu sloupce webu, tento průvodce zobrazí uživatele na adresu URL serveru pro ladění a jestli je nové řešení v izolovaném prostoru a Průvodce konfiguruje nový projekt pomocí těchto informací. Průvodce taky shromažďuje informace o sloupci (například základní typ a skupinu, ve které seznam sloupec v galerii sloupec lokality) a přidá tyto informace do souboru Elements.xml v novém projektu. Další informace najdete v tématu [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Definování typů položek projektu služby SharePoint vlastní](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Vytváření šablon položek a projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [Přidružení vlastních dat k rozšíření nástrojů služby SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  