---
title: "Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, creating custom templates
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
ms.assetid: 41ed9c1c-4239-4d80-934b-975fde744288
caps.latest.revision: "152"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 70a307fe1eb68cb6e1409d0a43178795f0d9421c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1"></a>Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1
  Systému projektu služby SharePoint v sadě Visual Studio můžete rozšířit vytvořením vlastní projektu typu položky. V tomto návodu vytvoříte položky projektu, který lze přidat do projektu služby SharePoint k vytvoření vlastní akce na web služby SharePoint. Vlastní akce přidá položku nabídky **Akce webu** nabídky Web služby SharePoint.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytváření rozšíření pro Visual Studio, který definuje nový typ položky projektu služby SharePoint pro vlastní akci. Nového typu položky projektu implementuje několik vlastní funkce:  
  
    -   Místní nabídky, která slouží jako výchozí bod pro další úlohy související s položkou projektu, například zobrazení návrháře pro vlastní akci v sadě Visual Studio.  
  
    -   Kód, který se spustí v případě, že vývojář změní určité vlastnosti položky projektu a projekt, který jej obsahuje.  
  
    -   Vlastní ikonu, která se zobrazí vedle položky projektu v **Průzkumníku řešení**.  
  
-   Vytváření šablony sady Visual Studio položky pro položku projektu.  
  
-   Vytváření rozšíření pro Visual Studio (VSIX) balíčku pro nasazení šablony položek projektu a sestavení rozšíření.  
  
-   Ladění a testování položky projektu.  
  
 Toto je samostatné návod. Po dokončení tohoto postupu můžete vylepšit položka projektu přidáním Průvodce pro šablony položky. Další informace najdete v tématu [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md).  
  
> [!NOTE]  
>  Můžete si stáhnout ukázku, která obsahuje dokončené projekty, kódu a další soubory v tomto návodu z následujícího umístění: [http://go.microsoft.com/fwlink/?LinkId=191369](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## <a name="prerequisites"></a>Požadavky  
 Následující součásti na vývojovém počítači k dokončení tohoto názorného postupu potřebujete:  
  
-   Podporované edice systému Microsoft Windows, SharePoint a Visual Studio. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Tento návod používá **projektu VSIX** šablony v sadě SDK k vytvoření balíčku VSIX pro nasazení položka projektu. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Znalost následující koncepty je užitečné, ale není nutné k dokončení průvodce:  
  
-   Vlastní akce ve službě SharePoint. Další informace najdete v tématu [vlastní akce](http://go.microsoft.com/fwlink/?LinkId=177800).  
  
-   Šablony položek v sadě Visual Studio. Další informace najdete v tématu [vytváření projektů a šablon položek](/visualstudio/ide/creating-project-and-item-templates).  
  
## <a name="creating-the-projects"></a>Vytváření projektů  
 K dokončení tohoto postupu potřebujete vytvořit tří projektů:  
  
-   Projekt VSIX. Tento projekt vytvoří balíčku VSIX pro nasazení položky projektu služby SharePoint.  
  
-   Projekt šablony položky. Tento projekt vytvoří šablonu položky, které je možné přidat položky projektu služby SharePoint do projektu služby SharePoint.  
  
-   Projektu knihovny tříd. Tento projekt implementuje rozšíření sady Visual Studio, která definuje chování položky projektu služby SharePoint.  
  
 Spusťte Průvodce vytvořením projektů.  
  
#### <a name="to-create-the-vsix-project"></a>Vytvoření projektu VSIX  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
3.  V seznamu v horní části **nový projekt** dialogové okno pole, ujistěte se, že **rozhraní .NET Framework 4.5** je vybrána.  
  
4.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **rozšiřitelnost** uzlu.  
  
    > [!NOTE]  
    >  **Rozšiřitelnost** uzel je k dispozici pouze v případě, že nainstalujete Visual Studio SDK. Další informace najdete v části požadavky dříve v tomto tématu.  
  
5.  Vyberte **projektu VSIX** šablony.  
  
6.  V **název** zadejte **CustomActionProjectItem**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Přidá **CustomActionProjectItem** projektu do **Průzkumníku řešení**.  
  
#### <a name="to-create-the-item-template-project"></a>Chcete-li vytvořit šablonu položky projektu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V seznamu v horní části **nový projekt** dialogové okno pole, ujistěte se, že **rozhraní .NET Framework 4.5** je vybrána.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **rozšiřitelnost** uzlu.  
  
4.  V seznamu šablon projektu, vyberte **šablony položky C#** nebo **šablony položky Visual Basic** šablony.  
  
5.  V **název** zadejte **ItemTemplate**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Přidá **ItemTemplate** projektu k řešení.  
  
#### <a name="to-create-the-extension-project"></a>Vytvoření projektu rozšíření  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V seznamu v horní části **nový projekt** dialogové okno pole, ujistěte se, že **rozhraní .NET Framework 4.5** je vybrána.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzlů, zvolte **Windows** uzel a potom vyberte  **Třídy knihovny** šablona projektu.  
  
4.  V **název** zadejte **ProjectItemDefinition**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Přidá **ProjectItemDefinition** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
5.  Odstraňte soubor kódu Class1 z projektu.  
  
## <a name="configuring-the-extension-project"></a>Konfigurace projektu rozšíření  
 Než napíšete kód pro definování typu položky projektu služby SharePoint, budete muset přidat soubory kódu a odkazy na sestavení na projekt.  
  
#### <a name="to-configure-the-project"></a>Konfigurace projektu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ProjectItemDefinition** projektu, zvolte **přidat**, zvolte **novou položku**.  
  
2.  V seznamu položek projektu, vyberte **souboru kódu**.  
  
3.  V **název** pole, zadejte název **CustomAction** s příslušnou příponu názvu souboru a potom vyberte **přidat** tlačítko.  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ProjectItemDefinition** projektu a potom vyberte **přidat odkaz na**.  
  
5.  V **správce odkazů - ProjectItemDefinition** dialogovém okně vyberte **sestavení** uzel a potom zvolte **Framework** uzlu.  
  
6.  Zaškrtněte políčko vedle každého z následujících sestavení:  
  
    -   System.ComponentModel.Composition  
  
    -   System.Windows.Forms  
  
7.  Vyberte **rozšíření** uzlu, zaškrtněte políčko vedle sestavení Microsoft.VisualStudio.Sharepoint a zvolte **OK** tlačítko.  
  
## <a name="defining-the-new-sharepoint-project-item-type"></a>Definování nového typu položky projektu SharePoint  
 Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> rozhraní k definování chování nového typu položky projektu. Toto rozhraní implementujte vždy, když chcete k definování nového typu položky projektu.  
  
#### <a name="to-define-the-new-sharepoint-project-item-type"></a>Chcete-li definovat nové typu položky projektu SharePoint  
  
1.  V projektu ProjectItemDefinition otevřete soubor kódu CustomAction.  
  
2.  Nahraďte kód v tomto souboru následujícím kódem.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#1](../sharepoint/codesnippet/CSharp/customactionprojectitem/projectitemtypedefinition/customaction.cs#1)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#1](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/projectitemdefinition/customaction.vb#1)]  
  
## <a name="creating-an-icon-for-the-project-item-in-solution-explorer"></a>Vytvoření ikony pro položku projekt v Průzkumníku řešení  
 Když vytvoříte vlastní položky projektu služby SharePoint, můžete přidružit položka projektu bitovou kopii (ikony nebo rastrový obrázek). Zobrazuje se vedle položky projektu v **Průzkumníku řešení**.  
  
 V následujícím postupu vytvoříte ikonu pro položku projektu a na ikonu pro vložení do sestavení rozšíření. Tato ikona se odkazuje <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemIconAttribute> z `CustomActionProjectItemTypeProvider` třídu, která jste vytvořili dříve.  
  
#### <a name="to-create-a-custom-icon-for-the-project-item"></a>Chcete-li vytvořit vlastní ikonou pro položky projektu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ProjectItemDefinition** projektu, zvolte **přidat**a potom zvolte **novou položku...** .  
  
2.  V seznamu položek projektu, vyberte **soubor ikony** položky.  
  
    > [!NOTE]  
    >  Projekty Visual Basic, je nutné vybrat **Obecné** uzel k zobrazení **soubor ikony** položky.  
  
3.  V **název** zadejte **CustomAction_SolutionExplorer.ico**a potom zvolte **přidat** tlačítko.  
  
     Nová ikona se otevře v **Editor obrázků**.  
  
4.  Upravte velikosti 16 x 16 verzi soubor ikony tak, aby měl návrh rozpoznají a potom uložte soubor ikony.  
  
5.  V **Průzkumníku řešení**, zvolte **CustomAction_SolutionExplorer.ico**.  
  
6.  V **vlastnosti** okně vyberte šipku vedle položky **akce sestavení** vlastnost.  
  
7.  V seznamu, který se zobrazí, vyberte **vložený prostředek**.  
  
## <a name="checkpoint"></a>Kontrolní bod  
 V tomto okamžiku návodu, je veškerý kód pro položku projektu v projektu. Sestavte projekt a ověřte, že se zkompiluje bez chyb.  
  
#### <a name="to-build-your-project"></a>K sestavení projektu  
  
1.  Otevřete místní nabídku pro **ProjectItemDefinition** projektu a zvolte **sestavení**.  
  
## <a name="creating-a-visual-studio-item-template"></a>Vytvoření položky šablony sady Visual Studio  
 Pokud chcete povolit jiné vývojářům používat vaše položky projektu, musíte vytvořit projekt šablony nebo šablony položky. Vývojáři použít tyto šablony v sadě Visual Studio k vytvoření instance položky projektu vytvořením nového projektu nebo přidání položky do existujícího projektu. Pro účely tohoto postupu použijte ke konfiguraci položky projektu ItemTemplate projektu.  
  
#### <a name="to-create-the-item-template"></a>Vytvoření šablony položek  
  
1.  Odstraňte soubor kódu Class1 z projektu ItemTemplate.  
  
2.  V projektu ItemTemplate otevřete soubor ItemTemplate.vstemplate.  
  
3.  Následující kód XML, nahraďte obsah souboru a uložte a zavřete soubor.  
  
    > [!NOTE]  
    >  Následující kód XML je pro šablony položky Visual C#. Pokud vytváříte šablonu položky Visual Basic, nahraďte hodnotu `ProjectType` element s `VisualBasic`.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
      <TemplateData>  
        <DefaultName>CustomAction</DefaultName>  
        <Name>Custom Action</Name>  
        <Description>SharePoint Custom Action by Contoso</Description>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>1000</SortOrder>  
        <Icon>ItemTemplate.ico</Icon>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
      <TemplateContent>  
        <ProjectItem ReplaceParameters="true" TargetFileName="$fileinputname$\Elements.xml">Elements.xml</ProjectItem>  
        <ProjectItem ReplaceParameters="true" TargetFileName="$fileinputname$\SharePointProjectItem.spdata">CustomAction.spdata</ProjectItem>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
     Tento soubor definuje obsahu a chování šablony položky. Další informace o obsahu tohoto souboru najdete v tématu [Visual Studio odkaz na schéma šablon](/visualstudio/extensibility/visual-studio-template-schema-reference).  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ItemTemplate** projektu, zvolte **přidat**a potom zvolte **novou položku**.  
  
5.  V **přidat novou položku** dialogovém okně vyberte **textový soubor** šablony.  
  
6.  V **název** zadejte **CustomAction.spdata**a potom zvolte **přidat** tlačítko.  
  
7.  Přidejte následující kód XML do souboru CustomAction.spdata a potom uložte a zavřete soubor.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ProjectItem Type="Contoso.CustomAction" DefaultFile="Elements.xml"   
     xmlns="http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel">  
      <Files>  
        <ProjectItemFile Source="Elements.xml" Target="$fileinputname$\" Type="ElementManifest" />  
      </Files>  
    </ProjectItem>  
    ```  
  
     Tento soubor obsahuje informace o souborech, které jsou obsaženy v položce projektu. `Type` Atribut `ProjectItem` element musí být nastaven na stejném řetězci, který je předán <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute> v definici položky projektu ( `CustomActionProjectItemTypeProvider` třídy, které jste vytvořili dříve v tomto návodu). Další informace o obsahu soubory .spdata najdete v tématu [referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md).  
  
8.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ItemTemplate** projektu, zvolte **přidat**a potom zvolte **novou položku**.  
  
9. V **přidat novou položku** dialogovém okně vyberte **souboru XML** šablony.  
  
10. V **název** zadejte **Elements.xml**a potom zvolte **přidat** tlačítko.  
  
11. Nahraďte obsah souboru Elements.xml následující kód XML a potom uložte a zavřete soubor.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Elements Id="$guid8$" xmlns="http://schemas.microsoft.com/sharepoint/">  
      <CustomAction Id="Replace this with a GUID or some other unique string"  
                    GroupId="SiteActions"  
                    Location="Microsoft.SharePoint.StandardMenu"  
                    Sequence="1000"  
                    Title="Replace this with your title"  
                    Description="Replace this with your description" >  
        <UrlAction Url="~site/Lists/Tasks/AllItems.aspx"/>  
      </CustomAction>  
    </Elements>  
    ```  
  
     Definuje vlastní výchozí akci, která vytvoří položku nabídky na tento soubor **Akce webu** nabídky Web služby SharePoint. Pokud uživatel vybere položku nabídky, adresa URL zadaná v `UrlAction` element otevře ve webovém prohlížeči. Další informace o elementy XML, která můžete použít k definování vlastní akce najdete v tématu [definice vlastní akce](http://go.microsoft.com/fwlink/?LinkId=177801).  
  
12. Volitelně můžete otevřít soubor ItemTemplate.ico a upravit ji tak, aby měl návrh, který dokáže rozpoznat. Tato ikona se zobrazí vedle položky projektu v **přidat novou položku** dialogové okno.  
  
13. V **Průzkumníku řešení**, otevřete místní nabídku pro **ItemTemplate** projektu a potom vyberte **uvolnit projekt**.  
  
14. Otevřete místní nabídku pro **ItemTemplate** projekt znovu a potom vyberte **Úprava ItemTemplate.csproj** nebo **Úprava ItemTemplate.vbproj**.  
  
15. Vyhledejte následující `VSTemplate` element v souboru projektu.  
  
    ```  
    <VSTemplate Include="ItemTemplate.vstemplate">  
    ```  
  
16. Nahraďte ho `VSTemplate` element s následující kód XML a pak uložit a zavřít soubor.  
  
    ```  
    <VSTemplate Include="ItemTemplate.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` Element určuje další složky v cestě, pod kterým šablony položky se vytvoří při sestavování projektu. Zde určené složky zajistí, že šablony položky bude k dispozici jenom v případě, že zákazníci otevřete **přidat novou položku** dialogové okno, rozbalte seznam **SharePoint** uzel a potom vyberte **2010**  uzlu.  
  
17. V **Průzkumníku řešení**, otevřete místní nabídku pro **ItemTemplate** projektu a potom vyberte **znovu načíst projekt**.  
  
## <a name="creating-a-vsix-package-to-deploy-the-project-item"></a>Vytvoření balíčku VSIX k nasazení položky projektu  
 K nasazení rozšíření, použijte k vytvoření balíčku VSIX VSIX projekt ve vašem řešení. Nejprve nakonfigurujte balíčku VSIX úpravou souboru source.extension.vsixmanifest, který je zahrnutý v projektu VSIX. Pak vytvořte balíčku VSIX vytvořením řešení.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Ke konfiguraci a vytvoření balíčku VSIX  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **source.extension.vsixmanifest** v projektu CustomActionProjectItem soubor a potom vyberte **otevřete**.  
  
     Visual Studio otevře soubor v editoru manifestu. Soubor source.extension.vsixmanifest je základem pro soubor extension.vsixmanifest, které vyžadují všechny balíčky VSIX. Další informace o tento soubor najdete v tématu [VSIX rozšíření schématu 1.0 odkaz](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  V **název produktu** zadejte **vlastní položky projektu akce**.  
  
3.  V **Autor** zadejte **Contoso**.  
  
4.  V **popis** zadejte **položky projektu služby SharePoint A, který představuje vlastní akce**.  
  
5.  Na **prostředky** , zvolte **nový** tlačítko.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
6.  V **typ** vyberte **Microsoft.VisualStudio.ItemTemplate**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `ItemTemplate` element v souboru extension.vsixmanifest. Tento element identifikuje podsložku v balíčku VSIX, který obsahuje šablony položek projektu. Další informace najdete v tématu [ItemTemplate Element (VSX schéma)](http://msdn.microsoft.com/en-us/1d489e54-c1c5-4f96-a510-6c2640867ff0).  
  
7.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
8.  V **projektu** vyberte **ItemTemplate**a potom zvolte **OK** tlačítko.  
  
9. V **prostředky** , zvolte **nový** tlačítko znovu.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
10. V **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `MefComponent` element v souboru extension.vsixmanifest. Tento element určuje název sestavení rozšíření v balíčku VSIX. Další informace najdete v tématu [MEFComponent Element (VSX schéma)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
11. V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
12. V **projektu** vyberte **ProjectItemDefinition**.  
  
13. Vyberte **OK** tlačítko.  
  
14. Na řádku nabídek zvolte **sestavení**, **sestavit řešení**a pak se ujistěte, že projekt zkompiluje bez chyb.  
  
15. Ujistěte se, že složku výstupu sestavení pro projekt CustomActionProjectItem obsahuje soubor CustomActionProjectItem.vsix.  
  
     Ve výchozím nastavení, je složku výstupu sestavení... \bin\Debug složku na složku obsahující projekt CustomActionProjectItem.  
  
## <a name="testing-the-project-item"></a>Testování položky projektu  
 Nyní jste připraveni k testování položka projektu. Nejprve spusťte ladění řešení CustomActionProjectItem v experimentální instanci sady Visual Studio. Pak test **vlastní akce** položka projektu v projektu služby SharePoint v experimentální instanci sady Visual Studio. Nakonec sestavte a spusťte projektu služby SharePoint k ověření, že vlastní akce funguje podle očekávání.  
  
#### <a name="to-start-debugging-the-solution"></a>Spustit ladění řešení  
  
1.  Restartujte Visual Studio s přihlašovacími údaji správce a pak otevřete CustomActionProjectItem řešení.  
  
2.  Otevřete soubor kódu CustomAction a pak přidejte zarážku na první řádek kódu `InitializeType` metoda.  
  
3.  Vyberte **F5** klíč spustit ladění.  
  
     Visual Studio nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\Custom akce Project Item\1. 0 a spustí experimentální instanci sady Visual Studio. Položka projektu budete testovat v této instanci sady Visual Studio.  
  
#### <a name="to-test-the-project-item-in-visual-studio"></a>K testování položky projektu v sadě Visual Studio  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  Rozbalte položku **Visual C#** nebo **jazyka Visual Basic** (v závislosti na jazyce, který podporuje vaše šablony položky), rozbalte položku **SharePoint**a potom vyberte **2010**  uzlu.  
  
3.  V seznamu šablon projektu, zvolte **projektu služby SharePoint 2010**.  
  
4.  V **název** zadejte **CustomActionTest**a potom zvolte **OK** tlačítko.  
  
5.  V **Průvodce vlastním nastavením SharePoint**, zadejte adresu URL webu, který chcete použít pro ladění a potom zvolte **Dokončit** tlačítko.  
  
6.  V **Průzkumníku řešení**, otevřete místní nabídce uzlu projektu, zvolte **přidat**a potom zvolte **novou položku**.  
  
7.  V **přidat novou položku** dialogovém okně vyberte **2010** pod uzlem **SharePoint** uzlu.  
  
     Ověřte, zda **vlastní akce** položka se zobrazí v seznamu položek projektu.  
  
8.  Vyberte **vlastní akce** položku a potom vyberte **přidat** tlačítko.  
  
     Visual Studio. přidá položku s názvem **CustomAction1** projektu a otevře Elements.xml souboru v editoru.  
  
9. Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou jste nastavili výše v `InitializeType` metoda.  
  
10. Vyberte **F5** klíče a pokračujte ladění projektu.  
  
11. V experimentální instanci sady Visual Studio v **Průzkumníku řešení**, otevřete místní nabídku pro **CustomAction1** uzel a potom zvolte **zobrazení návrháře vlastní akce**.  
  
12. Ověřte, zda se zobrazí okno se zprávou a potom zvolte **OK** tlačítko.  
  
     Tato nabídka zástupce můžete poskytnout další možnosti nebo příkazy pro vývojáře, například zobrazení návrháře pro vlastní akci.  
  
13. Na řádku nabídek zvolte **zobrazení**, **výstup**.  
  
     **Výstup** otevře se okno.  
  
14. V **Průzkumníku řešení**, otevřete místní nabídku pro **CustomAction1** položky a poté změňte její název **MyCustomAction**.  
  
     V **výstup** okně zobrazí potvrzovací zpráva. Tato zpráva je vytvořena systémem <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemNameChanged> obslužné rutiny události, který jste zadali v `CustomActionProjectItemTypeProvider` třídy. Může zpracovávat této události a dalších událostí položky projektu implementovat vlastní chování, když vývojáři změní položka projektu.  
  
#### <a name="to-test-the-custom-action-in-sharepoint"></a>K testování vlastní akce ve službě SharePoint  
  
1.  V experimentální instanci sady Visual Studio, otevřete soubor Elements.xml, který je podřízená **MyCustomAction** položka projektu.  
  
2.  V souboru Elements.xml proveďte následující změny a pak soubor uložte:  
  
    -   V `CustomAction` , nastavena `Id` atribut identifikátor GUID nebo jiný jedinečný řetězec jako na následujícím příkladu:  
  
        ```  
        Id="cd85f6a7-af2e-44ab-885a-0c795b52121a"  
        ```  
  
    -   V `CustomAction` , nastavena `Title` atribut jako na následujícím příkladu:  
  
        ```  
        Title="SharePoint Developer Center"  
        ```  
  
    -   V `CustomAction` , nastavena `Description` atribut jako na následujícím příkladu:  
  
        ```  
        Description="Opens the SharePoint Developer Center Web site."  
        ```  
  
    -   V `UrlAction` , nastavena `Url` atribut jako na následujícím příkladu:  
  
        ```  
        Url="http://msdn.microsoft.com/sharepoint/default.aspx"  
        ```  
  
3.  Zvolte klávesy F5.  
  
     Vlastní akce se zabalí a nasazené na web služby SharePoint, který je uveden v **adresa URL webu** vlastnosti projektu. Otevře se webový prohlížeč na stránku výchozího tohoto webu.  
  
    > [!NOTE]  
    >  Pokud **ladění skriptů zakázáno** se zobrazí dialogové okno, vyberte **Ano** tlačítka pokračujte ladění projektu.  
  
4.  Na **Akce webu** nabídce zvolte **SharePoint Developer Center**, ověřte, že prohlížeči se otevře http://msdn.microsoft.com/sharepoint/default.aspx webu a pak zavřete webový prohlížeč.  
  
## <a name="cleaning-up-the-development-computer"></a>Čištění vývojovém počítači  
 Po dokončení testování položky projektu odeberte položku Šablona projektu z experimentální instanci sady Visual Studio.  
  
#### <a name="to-clean-up-the-development-computer"></a>Vyčistěte vývojovém počítači  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **nástroje**, **rozšíření a aktualizace**.  
  
     **Rozšíření a aktualizace** otevře se dialogové okno.  
  
2.  V seznamu rozšíření, vyberte **vlastní položky projektu akce**a potom zvolte **odinstalovat** tlačítko.  
  
3.  V dialogovém okně, které se zobrazí, vyberte **Ano** tlačítko potvrďte, že chcete odinstalovat rozšíření.  
  
4.  Vyberte **restartovat nyní** tlačítko k dokončení odinstalace.  
  
5.  Zavřete experimentální instanci sady Visual Studio a instance, ve kterém je otevřen CustomActionProjectItem řešení.  
  
## <a name="next-steps"></a>Další kroky  
 Po dokončení tohoto postupu můžete přidat průvodce pro šablony položky. Pokud uživatel přidá vlastní položky projektu akce projektu služby SharePoint, Průvodce shromažďuje informace o akci (třeba jeho polohu a adresu URL, přejděte na při výběru akce) a přidá tyto informace do souboru Elements.xml v nové položky projektu. Další informace najdete v tématu [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [Definování typů položek projektu služby SharePoint vlastní](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Vytváření šablon položek a projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Použití služby projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md)   
 [Odkaz na schéma šablon sady Visual Studio](/visualstudio/extensibility/visual-studio-template-schema-reference)   
 [Editor obrázků pro ikony](/cpp/windows/image-editor-for-icons)   
 [Vytvoření ikony nebo jiného obrázku &#40; Editor obrázků pro ikony &#41;](/cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  