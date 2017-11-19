---
title: "Nasazování rozšíření pro nástroje služby SharePoint v sadě Visual Studio | Microsoft Docs"
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
helpviewer_keywords: SharePoint development in Visual Studio, deploying extensions
ms.assetid: 69927d95-acdf-4fd8-ac43-28e9a7fa8a38
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0145982781ca3e21229a7af46090ed2addcaccde
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="deploying-extensions-for-the-sharepoint-tools-in-visual-studio"></a>Nasazování rozšíření pro nástroje služby SharePoint v aplikaci Visual Studio
  Chcete-li nasadit rozšíření nástrojů SharePoint, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX), který obsahuje sestavení rozšíření a další soubory, které chcete distribuovat s rozšířením. Balíčku VSIX je komprimovaný soubor, který následuje standardní otevřete balení konvence OPC (). VSIX balíčky mít příponu VSIX.  
  
 Po vytvoření balíčku VSIX mohou ostatní uživatelé spusťte soubor VSIX k instalaci rozšíření. Když uživatel nainstaluje rozšíření, jsou nainstalovány všechny soubory do složky %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0\Extensions. Pokud chcete nasadit rozšíření, můžete nahrát balíčku VSIX pro [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) webové stránky, nebo můžete distribuovat balíček zákazníkům jiným způsobem, jako je například hostování balíček ve sdílené síťové složky nebo jiný webový server.  
  
 Další informace o vytváření balíčků VSIX a jejich nasazení do [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847), najdete v části [přesouvání rozšíření Visual Studia](/visualstudio/extensibility/shipping-visual-studio-extensions).  
  
 Balíčku VSIX můžete vytvořit pomocí **projektu VSIX** balíčku VSIX šablony v sadě Visual Studio, nebo můžete vytvořit ručně.  
  
## <a name="using-vsix-projects-to-create-vsix-packages"></a>Použití VSIX projekty k vytvoření balíčků VSIX  
 Můžete použít **projektu VSIX** šablony poskytované Visual Studio SDK k vytvoření balíčků VSIX pro rozšíření nástrojů služby SharePoint. Použití projektu VSIX poskytuje několik výhod oproti vytváření balíčku VSIX ručně:  
  
-   Visual Studio automaticky vytvoří balíček VSIX při sestavování projektu. Úlohy, jako je například přidávání soubory nasazení do balíčku a vytvoření souboru XML [Content_Types] pro balíček se provádějí za vás.  
  
-   Můžete nakonfigurovat projektu VSIX pro zahrnutí výstupu sestavení projektu rozšíření a další soubory, jako jsou šablony projektů a šablon položek v balíčku VSIX.  
  
 Další informace o použití projektu VSIX najdete v tématu [šablona projektu VSIX](/visualstudio/extensibility/vsix-project-template).  
  
### <a name="organizing-your-projects"></a>Uspořádání vašich projektů  
 Ve výchozím nastavení projekty VSIX generovat jenom balíčky VSIX, není sestavení. Proto je obvykle neimplementují rozšíření nástrojů SharePoint v projektu VSIX. Obecně pracujete s alespoň dva projekty:  
  
-   Projekt VSIX.  
  
-   Projekt knihovny tříd, který implementuje rozšíření.  
  
 Můžete také pracovat s další projekty pro některé typy rozšíření:  
  
-   Projekt knihovny tříd, který implementuje žádné příkazy služby SharePoint, které používají rozšíření. Návod, který ukazuje tento scénář, najdete v části [návod: rozšíření Průzkumníka serveru pro zobrazení webové části](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
-   Položka nebo šablona projektu projekt, který vytvoří položku šablony nebo šablony projektu, pokud rozšíření definuje nový typ položky projektu služby SharePoint. Návod, který ukazuje tento scénář, najdete v části [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  
  
-   Projekt knihovny tříd, který implementuje vlastního průvodce pro šablony položky nebo šablony projektu, pokud vaše rozšíření obsahuje šablonu. Návod, který ukazuje tento scénář, najdete v části [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md).  
  
 Pokud zahrnete všechny projekty v řešení stejné sady Visual Studio, můžete upravit soubor source.extension.vsixmanifest v projektu VSIX pro zahrnutí výstupu sestavení projektů knihovny tříd.  
  
### <a name="editing-the-vsix-manifest"></a>Úpravy VSIX Manifest  
 Musíte upravit soubor source.extension.vsixmanifest v projektu VSIX pro zahrnutí položky pro všechny položky, které chcete zahrnout do rozšíření. Když otevřete soubor source.extension.vsixmanifest ze své místní nabídky, soubor se zobrazí v návrháři, který poskytuje uživatelské rozhraní pro úpravy XML v souboru. Další informace najdete v tématu [Návrhář manifestu VSIX](/visualstudio/extensibility/vsix-manifest-designer).  
  
 Je nutné přidat položky do souboru source.extension.vsixmanifest pro následující položky:  
  
-   Sestavení rozšíření.  
  
-   Sestavení, které implementuje žádné příkazy služby SharePoint, které používají rozšíření.  
  
-   Šablony projektů nebo šablony položek, které jsou přidruženy rozšíření.  
  
-   Vlastní Průvodce pro šablony, která souvisí s rozšíření.  
  
 Následující postupy popisují, jak přidat položky do souboru .vsixmanifest pro každou z těchto položek.  
  
##### <a name="to-include-the-extension-assembly"></a>Chcete-li zahrnout rozšíření sestavení  
  
1.  V projektu VSIX otevřete místní nabídku pro soubor source.extension.vsixmanifest a zvolte **otevřete**.  
  
     Soubor se otevře v Návrháři  
  
2.  Na **prostředky** karta editoru, vyberte **nový** tlačítko.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
3.  V **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
4.  V **zdroj** seznamu, proveďte jednu z následujících kroků:  
  
    -   Pokud sestavení rozšíření je sestaven z projektu, který je ve stejném řešení jako projekt VSIX, zvolte **na projekt v aktuálním řešení**. V **projektu** seznamu, klikněte na název projektu.  
  
    -   Pokud je sestavení rozšíření zahrnuto jako soubor ve vašem projektu, zvolte **souboru v systému souborů**. V **cesta** seznamu, zadejte úplnou cestu k souboru rozšíření sestavení nebo použijte **Procházet** tlačítko vyhledat a vybrat soubor sestavení.  
  
5.  Vyberte **OK** tlačítko.  
  
##### <a name="to-include-a-sharepoint-command-assembly"></a>Zahrnout sestavení příkazu SharePoint  
  
1.  V projektu VSIX otevřete místní nabídku pro soubor source.extension.vsixmanifest a zvolte **otevřete** tlačítko.  
  
     Soubor se otevře v návrháři.  
  
2.  V **prostředky** části editoru, vyberte **nový** tlačítko.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
3.  V **typ** zadejte **SharePoint.Commands.v4**.  
  
4.  V **zdroj** seznamu, proveďte jednu z následujících kroků:  
  
    -   Pokud příkaz sestavení vytvořen z projektu, který je ve stejném řešení jako projekt VSIX, zvolte **na projekt v aktuálním řešení**. V **projektu** seznamu, klikněte na název projektu.  
  
    -   Pokud je příkaz sestavení zahrnuto jako soubor ve vašem projektu, zvolte **souboru v systému souborů**. V **cesta** seznamu, zadejte úplnou cestu k souboru rozšíření sestavení nebo použijte **Procházet** tlačítko vyhledat a vybrat soubor sestavení.  
  
5.  Vyberte **OK** tlačítko.  
  
##### <a name="to-include-a-template-that-you-create"></a>Zahrnout šablonu, kterou vytvoříte  
  
1.  V projektu VSIX otevřete místní nabídku pro soubor source.extension.vsixmanifest a zvolte **otevřete** tlačítko.  
  
     Soubor se otevře v návrháři.  
  
2.  V **prostředky** části editoru, vyberte **nový** tlačítko.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
3.  V **typ** vyberte **Microsoft.VisualStudio.ProjectTemplate** nebo **Microsoft.VisualStudio.ItemTemplate**.  
  
4.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
5.  V **projektu** seznamu, klikněte na název projektu a potom zvolte **OK** tlačítko.  
  
6.  V **Průzkumníku řešení**, otevřete místní nabídky projektu šablony nebo šablony položek projektu a zvolte **uvolnit projekt**.  
  
7.  Znovu otevřete místní nabídku pro uzel projektu a zvolte **upravit***YourTemplateProjectName***.csproj** nebo **upravit**  *YourTemplateProjectName***.vbproj**.  
  
8.  Vyhledejte následující `VSTemplate` element v souboru projektu.  
  
    ```  
    <VSTemplate Include="YourTemplateName.vstemplate">  
    ```  
  
9. Tento element nahraďte následující kód XML.  
  
    ```  
    <VSTemplate Include="YourTemplateName.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` Element určuje další složky v cestě, pod kterým je vytvořena šablona projektu při sestavování projektu. Zde určené složky zajistí, že šablony položky bude k dispozici jenom v případě, že zákazníci otevřete **přidat nový projekt** dialogové okno, rozbalte seznam **SharePoint** uzel a potom vyberte **2010**  uzlu.  
  
10. Soubor uložte a zavřete.  
  
11. V **Průzkumníku řešení**, otevřete místní nabídky projektu šablony nebo šablony položek projektu a zvolte **znovu načíst projekt**.  
  
##### <a name="to-include-a-template-that-you-create-manually"></a>Zahrnout šablonu, kterou vytvoříte ručně  
  
1.  V projektu VSIX přidejte do projektu tak, aby šablona obsahovala novou složku.  
  
2.  V této nové složky, vytvořte následující podsložky a pak přidejte soubor šablony (.zip) na *ID národního prostředí* složky.  
  
     *YourTemplateFolder*  
  
     **SharePoint**  
  
     **SharePoint14**  
  
     *ID národního prostředí*  
  
     *YourTemplateName*.zip  
  
     Například pokud máte šablony položky s názvem ContosoCustomAction.zip, která podporuje národní prostředí Czech (Czech Republic), úplná cesta může být ItemTemplates\SharePoint\SharePoint14\1033\ContosoCustomAction.zip.  
  
3.  V **Průzkumníku řešení**, vyberte soubor šablony (*YourTemplateName*.zip).  
  
4.  V **vlastnosti** nastavte **akce sestavení** vlastnost **obsahu**.  
  
5.  Otevřete místní nabídku pro soubor source.extension.vsixmanifest a zvolte **otevřete**.  
  
     Soubor se otevře v návrháři.  
  
6.  V **prostředky** části editoru, vyberte **nový** tlačítko.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
7.  V **typ** vyberte **Microsoft.VisualStudio.ItemTemplate** nebo **Microsoft.VisualStudio.ProjectTemplate**.  
  
8.  V **zdroj** vyberte **souboru v systému souborů**.  
  
9. V **cesta** pole, zadejte úplnou cestu k sestavení (například **ItemTemplates\SharePoint\SharePoint14\1033\ContosoCustomAction.zip**, nebo použijte **Procházet**tlačítko vyhledejte a vyberte sestavení a potom vyberte **OK** tlačítko.  
  
##### <a name="to-include-a-wizard-for-a-project-template-or-item-template"></a>Zahrnout Průvodce pro šablony projektu nebo šablony položek  
  
1.  V projektu VSIX otevřete místní nabídku pro soubor source.extension.vsixmanifest a zvolte **otevřete**.  
  
     Soubor se otevře v návrháři.  
  
2.  V **prostředky** části editoru, vyberte **nový** tlačítko.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
3.  V **typ** vyberte **Microsoft.VisualStudio.Assembly**.  
  
4.  V **zdroj** seznamu, proveďte jednu z následujících kroků:  
  
    -   Pokud Průvodce sestavení je sestaven z projektu, který je ve stejném řešení jako projekt VSIX, zvolte **na projekt v aktuálním řešení**. V **projektu** seznamu, klikněte na název projektu.  
  
    -   Pokud Průvodce sestavení je uveden jako soubor ve vašem projektu, zvolte **souboru v systému souborů**. V **cesta** pole, zadejte úplnou cestu k souboru sestavení nebo použijte **Procházet** tlačítko vyhledat a vybrat sestavení.  
  
5.  Vyberte **OK** tlačítko.  
  
### <a name="related-walkthroughs"></a>Související návody  
 Následující tabulka uvádí návodů, které ukazují, jak nasadit různé typy rozšíření nástrojů služby SharePoint pomocí projektu VSIX.  
  
|Typ rozšíření.|Související návody|  
|--------------------|--------------------------|  
|Rozšíření, které obsahuje pouze sestavení rozšíření|[Návod: Rozšiřování typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)<br /><br /> [Návod: Vytváření rozšíření projektu SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)<br /><br /> [Návod: Volání do objektového modelu klienta pro SharePoint v rozšíření Průzkumníka serveru](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)|  
|Rozšíření, které obsahuje SharePoint – příkazy|[Návod: Vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)<br /><br /> [Návod: Rozšíření Průzkumníka serveru pro zobrazení webové části](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)<br /><br /> [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)|  
|Rozšíření, které obsahuje šablony sady Visual Studio|[Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)<br /><br /> [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)|  
|Rozšíření, které obsahuje Průvodce pro šablony|[Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)<br /><br /> [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)|  
  
## <a name="creating-vsix-packages-manually"></a>Ruční vytváření balíčků VSIX  
 Pokud chcete ručně vytvořit balíčku VSIX pro rozšíření nástrojů služby SharePoint, proveďte následující kroky:  
  
1.  Vytvořte soubor extension.vsixmanifest a souboru .xml [Content_Types] do nové složky. Další informace najdete v tématu [anatomie balíčku VSIX](/visualstudio/extensibility/anatomy-of-a-vsix-package).  
  
2.  V Průzkumníku Windows klikněte pravým tlačítkem na složku, která obsahuje dva soubory XML, klikněte na tlačítko Odeslat a klikněte na položku komprimované složky. Přejmenujte výsledný soubor ZIP Filename.vsix, kde název souboru je název souboru redistributable, který nainstaluje vašeho balíčku.  
  
3.  Rozšíření sestavení přidáte do balíčku VSIX. Pokud vaše rozšíření obsahuje příkaz SharePoint, přidejte také sestavení, které implementuje příkaz SharePoint balíčku VSIX.  
  
4.  Upravte soubor extension.vsixmanifest:  
  
    -   Přidat `Microsoft.VisualStudio.MefComponent` prvek v rámci `Assets` element a pak nastavte hodnotu nového elementu relativní cestu sestavení, které implementuje rozšíření v balíčku VSIX. Další informace najdete v tématu [MEFComponent Element (VSX schéma)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
    -   Pokud vaše rozšíření obsahuje příkaz SharePoint, který volá do objektový model serveru pro službu SharePoint, přidejte `Microsoft.VisualStudio.Assembly` prvek v rámci `Assets` elementu. Nastavte hodnotu nového elementu relativní cestu sestavení, které implementuje příkaz SharePoint v balíčku VSIX. Další informace najdete v tématu [Element Asset (VSX schéma)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737).  
  
    -   Pokud vaše rozšíření obsahuje projektu šablony nebo šablony položky, přidejte `ProjectTemplate` nebo `ItemTemplate` prvek v rámci `Assets` elementu. Nastavte hodnotu nového elementu na relativní cestu složky, která obsahuje šablony v balíčku VSIX. Další informace najdete v tématu [ProjectTemplate Element (VSX schéma)](http://msdn.microsoft.com/en-us/87add64c-9dcd-495f-8815-209dab182cb1) a [ItemTemplate Element (VSX schéma)](http://msdn.microsoft.com/en-us/1d489e54-c1c5-4f96-a510-6c2640867ff0).  
  
    -   Pokud vaše rozšíření obsahuje vlastní průvodce pro šablony projektu nebo šablony položky, přidejte `Assembly` prvek v rámci `Assets` elementu. Nastavit hodnotu nového elementu relativní cestu sestavení v balíčku VSIX a potom `AssemblyName` atribut úplného názvu sestavení (včetně verze, jazykové verze a tokenu veřejného klíče). Další informace najdete v tématu [Dependency – Element (VSX schéma)](http://msdn.microsoft.com/en-us/1f63f60a-98ad-48ec-8e44-4eba383d3e37).  
  
### <a name="example"></a>Příklad  
 Následující příklad ukazuje obsah souboru extension.vsixmanifest pro rozšíření nástrojů SharePoint. Rozšíření je implementovaná v sestavení s názvem Contoso.ProjectExtension.dll. Rozšíření zahrnuje sestavení příkazu SharePoint s názvem Contoso.ExtensionCommands.dll a šablony položky ve složce, který je pojmenován **šablon položek** v balíčku VSIX. Tento příklad předpokládá, že jsou obě sestavení ve stejné složce jako soubor extension.vsixmanifest v balíčku VSIX.  
  
```  
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">  
  <Metadata>  
    <Identity Id="CustomActionProjectItem.Microsoft.b99efe4d-cef3-4afd-b9af-034ca0c52743" Version="1.0" Language="en-US" Publisher="Microsoft" />  
    <DisplayName>CustomActionProjectItem</DisplayName>  
    <Description>Empty VSIX Project.</Description>  
  </Metadata>  
  <Installation>  
    <InstallationTarget Id="Microsoft.VisualStudio.Pro" Version="11.0" />  
  </Installation>  
  <Dependencies>  
    <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" Version="4.5" />  
  </Dependencies>  
  <Assets>  
    <Asset Type="Microsoft.VisualStudio.ItemTemplate" Path="ItemTemplates" />  
    <Asset Type="Microsoft.VisualStudio.MefComponent" Path="ProjectItemDefinition.dll" />  
  </Assets>  
</PackageManifest>  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Volání do služby SharePoint objektové modely](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Ladění rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  