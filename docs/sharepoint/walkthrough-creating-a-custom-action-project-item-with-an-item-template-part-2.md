---
title: "Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 2 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], creating template wizards
- SharePoint project items, creating template wizards
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 55794f7976e90e34ba24654400f755de9244e13e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2"></a>Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 2
  Po definování vlastního typu položky projektu služby SharePoint a přidružit ho pomocí šablony položky v sadě Visual Studio, můžete také poskytnout průvodce pro šablony. Průvodce vám pomůže shromažďovat informace od uživatelů při použití šablony přidat novou instanci položky projektu do projektu. Informace, které slouží k inicializaci položky projektu.  
  
 V tomto návodu budete přidávat Průvodce pro položky projektu vlastní akce, která je znázorněna v [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md). Pokud uživatel přidá vlastní položky projektu akce do projektu služby SharePoint, Průvodce shromažďuje informace o vlastní akci (třeba jeho polohu a adresu URL má přejít při koncový uživatel rozhodne ho) a přidá tyto informace do souboru Elements.xml v novém Položka projektu.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytváření průvodce pro vlastního typu položky projektu služby SharePoint, který je přidružen k šabloně položky.  
  
-   Definování vlastní průvodce uživatelské rozhraní, které nahrazuje vestavěné průvodce pro položky projektu služby SharePoint v sadě Visual Studio.  
  
-   Nahraditelné parametry pomocí k chybě při inicializaci soubory projektu služby SharePoint s daty, která shromažďujete v průvodci.  
  
-   Ladění a testování průvodce.  
  
> [!NOTE]  
>  Můžete si stáhnout ukázku, která obsahuje dokončené projekty, kódu a další soubory v tomto návodu z následujícího umístění: [soubory projektu pro návody pro rozšíření nástrojů SharePoint](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, musíte nejdřív vytvořit řešení CustomActionProjectItem provedením [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  
  
 Potřebujete taky následující součásti na vývojovém počítači k dokončení tohoto názorného postupu:  
  
-   Podporované edice systému Windows, SharePoint a Visual Studio. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK. Tento návod používá **projektu VSIX** šablony v sadě SDK k vytvoření balíčku VSIX pro nasazení položka projektu. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Znalost následující koncepty je užitečné, ale není nutné k dokončení průvodce:  
  
-   Průvodce pro šablony projektů a položek v sadě Visual Studio. Další informace najdete v tématu [postupy: použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md) a <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní.  
  
-   Vlastní akce ve službě SharePoint. Další informace najdete v tématu [vlastní akce](http://go.microsoft.com/fwlink/?LinkId=177800).  
  
## <a name="creating-the-wizard-project"></a>Vytvoření projektu průvodce  
 Pro dokončení tohoto návodu, musíte přidat projekt do CustomActionProjectItem řešení, které jste vytvořili v [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md). Budete implementovat <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní a definovat Průvodce uživatelského rozhraní v tomto projektu.  
  
#### <a name="to-create-the-wizard-project"></a>Vytvoření projektu průvodce  
  
1.  V sadě Visual Studio otevřete CustomActionProjectItem řešení  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **Windows** uzlu.  
  
4.  V horní části **nový projekt** dialogové okno pole, ujistěte se, že **rozhraní .NET Framework 4.5** je vybrán v seznamu verze rozhraní .NET Framework.  
  
5.  Vyberte **knihovny ovládací prvek WPF uživatelského** projektu šablony, název projektu **ItemTemplateWizard**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Přidá **ItemTemplateWizard** projektu k řešení.  
  
6.  Odstraňte položku UserControl1 z projektu.  
  
## <a name="configuring-the-wizard-project"></a>Konfigurace projektu průvodce  
 Než vytvoříte v průvodci, musíte přidat okno Windows Presentation Foundation (WPF), souboru kódu a odkazy na sestavení do projektu.  
  
#### <a name="to-configure-the-wizard-project"></a>Ke konfiguraci projektu průvodce  
  
1.  V **Průzkumníku řešení**, otevřete z místní nabídky **ItemTemplateWizard** uzel projektu a potom zvolte **vlastnosti**.  
  
2.  V **Návrhář projektu**, ujistěte se, že cílový framework je nastavená na rozhraní .NET Framework 4.5.  
  
     Pro projekty Visual C#, můžete tuto hodnotu můžete nastavit na **aplikace** kartě. Pro projekty Visual Basic, můžete tuto hodnotu můžete nastavit na **zkompilovat** kartě. Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
3.  V **ItemTemplateWizard** projekt, přidejte **okno (WPF)** položku do projektu s názvem položka **WizardWindow**.  
  
4.  Přidejte dva soubory kódu, které byly pojmenovány CustomActionWizard a řetězce.  
  
5.  Otevřete místní nabídku pro **ItemTemplateWizard** projektu a potom vyberte **přidat odkaz na**.  
  
6.  V **správce odkazů - ItemTemplateWizard** dialogovém **sestavení** uzlu, vyberte **rozšíření** uzlu.  
  
7.  Zaškrtněte políčka vedle následující sestavení a potom zvolte **OK** tlačítko:  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
8.  V **Průzkumníku řešení**v **odkazy** vyberte složku pro projektu ItemTemplateWizard **EnvDTE** odkaz.  
  
9. V **vlastnosti** okno, změňte hodnotu **vložit zprostředkovatel komunikace s objekty typy** vlastnost **False**.  
  
## <a name="defining-the-default-location-and-id-strings-for-custom-actions"></a>Definování výchozí umístění a ID řetězce pro vlastní akce  
 Každá vlastní akce obsahuje umístění a ID, který je uveden v `GroupID` a `Location` atributy `CustomAction` element v souboru Elements.xml. V tomto kroku definujete některé platné řetězce pro tyto atributy v projektu ItemTemplateWizard. Po dokončení tohoto průvodce, tyto řetězce se zapisují do souboru Elements.xml v položky projektu akce vlastní když uživatelé zadat umístění a ID v průvodci.  
  
 Tato ukázka pro jednoduchost, podporuje pouze podmnožinu identifikátory a dostupná výchozí umístění. Úplný seznam najdete v tématu [výchozí umístění vlastní akce a ID](http://go.microsoft.com/fwlink/?LinkId=181964).  
  
#### <a name="to-define-the-default-location-and-id-strings"></a>Zadat výchozí umístění a ID řetězce  
  
1.  Otevřete.  
  
2.  V **ItemTemplateWizard** projektu, nahraďte kód v souboru kódu řetězce s následujícím kódem.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#6](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/strings.cs#6)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#6](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/strings.vb#6)]  
  
## <a name="creating-the-wizard-ui"></a>Vytvoření uživatelského rozhraní Průvodce  
 Přidejte XAML pro definování uživatelského rozhraní průvodce a přidat kód pro vazbu některé ovládací prvky v průvodci na ID řetězce. Průvodce, který vytvoříte vypadá takto: integrované Průvodce pro projekty SharePoint v sadě Visual Studio.  
  
#### <a name="to-create-the-wizard-ui"></a>Chcete-li vytvořit průvodce uživatelského rozhraní  
  
1.  V **ItemTemplateWizard** projektu, otevřete místní nabídku pro **WizardWindow.xaml** souboru a potom vyberte **otevřete** a otevřete okno v návrháři.  
  
2.  V zobrazení jazyka XAML nahraďte aktuální XAML následující XAML. XAML definuje uživatelského rozhraní, které zahrnuje nadpisu, ovládací prvky pro určení chování vlastní akce a navigačních tlačítek v dolní části okna.  
  
    > [!NOTE]  
    >  Projekt bude mít několik chyb kompilace po přidání tohoto kódu. Tyto chyby zmizí při přidání kódu v dalších krocích.  
  
     [!code-xml[SPExtensibility.ProjectItem.CustomAction#9](../sharepoint/codesnippet/Xaml/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml#9)]  
  
    > [!NOTE]  
    >  Okno, který je vytvořen v této XAML je odvozený od <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> základní třídy. Když přidáte vlastní dialogové okno WPF k sadě Visual Studio, doporučujeme z této třídy tak, aby měl konzistentní stylů s další dialogová okna v sadě Visual Studio a abyste předešli problémům, které by jinak mohlo dojít s modální dialogová okna jsou odvozeny vašem dialogovém okně. Další informace najdete v tématu [vytváření a správa modální dialogová okna](/visualstudio/extensibility/creating-and-managing-modal-dialog-boxes).  
  
3.  Pokud vyvíjíte projekt Visual Basic, odeberte `ItemTemplateWizard` oboru názvů z `WizardWindow` název třídy v `x:Class` atribut `Window` elementu. Tento element má na prvním řádku XAML. Když jste hotovi, první řádek by měl vypadat následující kód:  
  
    ```  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  V souboru kódu na pozadí pro soubor WizardWindow.xaml nahraďte následujícím kódem aktuálního kódu.  
  
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#7](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml.vb#7)]
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#7](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml.cs#7)]  
  
## <a name="implementing-the-wizard"></a>Implementace průvodce  
 Definujte funkci Průvodce implementací <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní.  
  
#### <a name="to-implement-the-wizard"></a>K implementaci Průvodce  
  
1.  V **ItemTemplateWizard** projekt, otevřete **CustomActionWizard** kód souboru a aktuálního kódu v tomto souboru nahraďte následujícím kódem:  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#8](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/customactionwizard.cs#8)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#8](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/customactionwizard.vb#8)]  
  
## <a name="checkpoint"></a>Kontrolní bod  
 V tomto okamžiku návodu, je celý kód pro průvodce v projektu. Sestavte projekt a ujistěte se, že se zkompiluje bez chyb.  
  
#### <a name="to-build-your-project"></a>K sestavení projektu  
  
1.  Na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
## <a name="associating-the-wizard-with-the-item-template"></a>Průvodce přidružením šablony položky  
 Teď, když jste implementovali průvodce, musíte přidružíte **vlastní akce** šablony položky provedením tři hlavní kroky:  
  
1.  Podepsání sestavení silným názvem průvodce.  
  
2.  Získání tokenu veřejného klíče pro sestavení průvodce.  
  
3.  Přidat odkaz na sestavení průvodce v souboru .vstemplate **vlastní akce** šablony položky.  
  
#### <a name="to-sign-the-wizard-assembly-with-a-strong-name"></a>K podepsání Průvodce sestavení se silným názvem  
  
1.  V **Průzkumníku řešení**, otevřete z místní nabídky **ItemTemplateWizard** uzel projektu a potom zvolte **vlastnosti**.  
  
2.  Na **podpisování** vyberte **podepsání sestavení** zaškrtávací políčko.  
  
3.  V **vyberte soubor klíče se silným názvem** vyberte ** \<nová... >**.  
  
4.  V **vytvořit klíč se silným názvem** dialogovém okně zadejte název, zrušte **chránit Moje soubor klíče s heslem** zaškrtněte políčko a potom vyberte **OK** tlačítko.  
  
5.  Na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
#### <a name="to-get-the-public-key-token-for-the-wizard-assembly"></a>K získání tokenu veřejného klíče pro sestavení průvodce  
  
1.  V okně příkazového řádku Visual Studia, spusťte následující příkaz, nahraďte *PathToWizardAssembly* s úplnou cestou k integrovaný ItemTemplateWizard.dll pro ItemTemplateWizard projekt na váš vývojový počítač.  
  
    ```  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     Token veřejného klíče pro sestavení ItemTemplateWizard.dll je zapsán do okna příkazového řádku Visual Studia.  
  
2.  Nechte okno příkazového řádku Visual Studia otevřené. Token veřejného klíče pro dokončení dalšího postupu budete potřebovat.  
  
#### <a name="to-add-a-reference-to-the-wizard-assembly-in-the-vstemplate-file"></a>Chcete-li přidat odkaz na sestavení průvodce v souboru .vstemplate  
  
1.  V **Průzkumníku řešení**, rozbalte **ItemTemplate** uzel projektu a pak otevřete soubor ItemTemplate.vstemplate.  
  
2.  U konce souboru, přidejte následující `WizardExtension` element mezi `</TemplateContent>` a `</VSTemplate>` značky. Nahraďte *YourToken* hodnotu `PublicKeyToken` atributem, token veřejného klíče, který jste získali v předchozím postupu.  
  
    ```  
    <WizardExtension>  
      <Assembly>ItemTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=YourToken</Assembly>  
      <FullClassName>ItemTemplateWizard.CustomActionWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     Další informace o `WizardExtension` elementu, najdete v části [WizardExtension – Element & #40; Šablony sady Visual Studio & #41; ](/visualstudio/extensibility/wizardextension-element-visual-studio-templates).  
  
3.  Soubor uložte a zavřete.  
  
## <a name="adding-replaceable-parameters-to-the-elementsxml-file-in-the-item-template"></a>Přidání do souboru Elements.xml v šabloně položky nahraditelné parametry  
 Přidejte do souboru Elements.xml v projektu ItemTemplate několik nahraditelné parametry. Tyto parametry jsou inicializovány v `PopulateReplacementDictionary` metoda v `CustomActionWizard` třídu, která je definována dříve. Pokud uživatel přidá do projektu položka projektu vlastní akce, Visual Studio automaticky nahradí tyto parametry v souboru Elements.xml v nové položky projektu hodnot zadaných v průvodci.  
  
 Nahraditelné parametr je token, který se spustí a končí znak dolaru ($). Kromě definování vlastní nahraditelné parametry, můžete použít předdefinované parametry, které definuje systému projektu služby SharePoint a inicializuje. Další informace najdete v tématu [nahraditelné parametry](../sharepoint/replaceable-parameters.md).  
  
#### <a name="to-add-replaceable-parameters-to-the-elementsxml-file"></a>Chcete-li přidat do souboru Elements.xml nahraditelné parametry  
  
1.  V projektu ItemTemplate nahraďte obsah souboru Elements.xml následující kód XML.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Elements Id="$guid8$" xmlns="http://schemas.microsoft.com/sharepoint/">  
      <CustomAction Id="$IdValue$"  
                    GroupId="$GroupIdValue$"  
                    Location="$LocationValue$"  
                    Sequence="1000"  
                    Title="$TitleValue$"  
                    Description="$DescriptionValue$" >  
        <UrlAction Url="$UrlValue$"/>  
      </CustomAction>  
    </Elements>  
    ```  
  
     Nové XML změní hodnoty `Id`, `GroupId`, `Location`, `Description`, a `Url` atributy nahraditelné parametry.  
  
2.  Soubor uložte a zavřete.  
  
## <a name="adding-the-wizard-to-the-vsix-package"></a>Průvodce přidáním balíčku VSIX  
 V souboru source.extension.vsixmanifest v projektu VSIX přidejte odkaz na projekt průvodce tak, aby se nasazuje s balíčku VSIX, který obsahuje položky projektu.  
  
#### <a name="to-add-the-wizard-to-the-vsix-package"></a>Chcete-li přidat průvodce balíčku VSIX  
  
1.  V **Průzkumníku řešení**, otevřete z místní nabídky **source.extension.vsixmanifest** v projektu CustomActionProjectItem soubor a potom vyberte **otevřete** otevřete soubor v editoru manifestu.  
  
2.  V editoru manifestu zvolte **prostředky** a potom zvolte **nový** tlačítko.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
3.  V **typ** vyberte **Microsoft.VisualStudio.Assembly**.  
  
4.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
5.  V **projektu** vyberte **ItemTemplateWizard**a potom zvolte **OK** tlačítko.  
  
6.  Na řádku nabídek zvolte **sestavení**, **sestavit řešení**a pak se ujistěte, že řešení zkompiluje bez chyb.  
  
## <a name="testing-the-wizard"></a>Testování průvodce  
 Nyní jste připraveni k testování průvodce. Nejprve spusťte ladění řešení CustomActionProjectItem v experimentální instanci sady Visual Studio. Otestujte průvodce pro položky projektu vlastní akce v projektu služby SharePoint v experimentální instanci sady Visual Studio. Nakonec sestavte a spusťte projektu služby SharePoint k ověření, že vlastní akce funguje podle očekávání.  
  
#### <a name="to-start-to-debug-the-solution"></a>Spusťte ladění řešení  
  
1.  Restartujte Visual Studio s přihlašovacími údaji správce a pak otevřete CustomActionProjectItem řešení.  
  
2.  V projektu ItemTemplateWizard otevřete soubor kódu CustomActionWizard a pak přidejte zarážku na první řádek kódu `RunStarted` metoda.  
  
3.  Na řádku nabídek zvolte **ladění**, **výjimky**.  
  
4.  V **výjimky** dialogové okno pole, ujistěte se, že **vyvolaná** a **neošetřené uživatelem** zaškrtnutí políček u **běžné výjimky za běhu jazyka**jsou vymazány a potom vyberte **OK** tlačítko.  
  
5.  Spuštění ladění výběrem klávesu F5, nebo na panelu nabídek, výběr **ladění**, **spustit ladění**.  
  
     Visual Studio nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Custom akce Project Item\1. 0 a spustí experimentální instanci sady Visual Studio. Položka projektu budete testovat v této instanci sady Visual Studio.  
  
#### <a name="to-test-the-wizard-in-visual-studio"></a>K testování průvodce v sadě Visual Studio  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  Rozbalte položku **Visual C#** nebo **jazyka Visual Basic** uzlu (v závislosti na jazyce, který podporuje vaše šablony položky), rozbalte **SharePoint** uzel a potom zvolte **2010** uzlu.  
  
3.  V seznamu šablon projektu, zvolte **projektu služby SharePoint 2010**, název projektu **CustomActionWizardTest**a potom zvolte **OK** tlačítko.  
  
4.  V **Průvodce vlastním nastavením SharePoint**, zadejte adresu URL webu, který chcete použít pro ladění a potom zvolte **Dokončit** tlačítko.  
  
5.  V **Průzkumníku řešení**, otevřete místní nabídce uzlu projektu, zvolte **přidat**a potom zvolte **novou položku**.  
  
6.  V **přidat novou položku – CustomItemWizardTest** dialogové okno, rozbalte seznam **SharePoint** uzel a potom rozbalte **2010** uzlu.  
  
7.  V seznamu položek projektu, vyberte **vlastní akce** položku a potom vyberte **přidat** tlačítko.  
  
8.  Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou jste nastavili výše v `RunStarted` metoda.  
  
9. Pokračujte výběrem klávesy F5 nebo v nabídce panelu Výběr ladění projektu **ladění**, **pokračovat**.  
  
     Zobrazí se Průvodce nastavením služby SharePoint.  
  
10. V části **umístění**, vyberte **úprava seznamu** tlačítko.  
  
11. V **ID skupiny** vyberte **komunikace**.  
  
12. V **název** zadejte **SharePoint Developer Center**.  
  
13. V **popis** zadejte **otevře na webu SharePoint Developer Center**.  
  
14. V **URL** zadejte **http://msdn.microsoft.com/sharepoint/default.aspx**a potom zvolte **Dokončit** tlačítko.  
  
     Visual Studio přidá položku s názvem **CustomAction1** projektu a otevře Elements.xml souboru v editoru. Ověřte, zda Elements.xml obsahuje hodnoty, které jste zadali v průvodci.  
  
#### <a name="to-test-the-custom-action-in-sharepoint"></a>K testování vlastní akce ve službě SharePoint  
  
1.  V experimentální instanci sady Visual Studio, vyberte klávesy F5 nebo v řádku nabídek zvolte **ladění**, **spustit ladění**.  
  
     Vlastní akce se zabalí a nasazené na web služby SharePoint určeného **adresa URL webu** vlastností projektu a webový prohlížeč otevře na stránku výchozího tohoto webu.  
  
    > [!NOTE]  
    >  Pokud **ladění skriptů zakázáno** se zobrazí dialogové okno, vyberte **Ano** tlačítko.  
  
2.  V oblasti seznamy webu služby SharePoint, zvolte **úlohy** odkaz.  
  
     **Úlohy – všechny úlohy** se zobrazí stránka.  
  
3.  Na **nástroje seznamu** karty na pásu karet vyberte **seznamu** kartě a pak na **nastavení** skupiny, vyberte **nastavení seznamu**.  
  
     **Nastavení seznamu** se zobrazí stránka.  
  
4.  V části **komunikace** záhlaví v horní části stránky, vyberte **SharePoint Developer Center** propojit, ověřte, že prohlížeči se otevře http://msdn.microsoft.com/sharepoint/ webu default.aspx a pak zavřete prohlížeč.  
  
## <a name="cleaning-up-the-development-computer"></a>Čištění vývojovém počítači  
 Po dokončení testování položky projektu odeberte položku Šablona projektu z experimentální instanci sady Visual Studio.  
  
#### <a name="to-clean-up-the-development-computer"></a>Vyčistěte vývojovém počítači  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **nástroje**, **rozšíření a aktualizace**.  
  
     **Rozšíření a aktualizace** otevře se dialogové okno.  
  
2.  V seznamu rozšíření, vyberte **vlastní položky projektu akce** rozšíření a potom zvolte **odinstalovat** tlačítko.  
  
3.  V dialogovém okně, které se zobrazí, vyberte **Ano** tlačítko potvrďte, že chcete odinstalovat rozšíření a potom vyberte **restartovat nyní** tlačítko k dokončení odinstalace.  
  
4.  Zavřete obě instance sady Visual Studio (experimentální instance a instance sady Visual Studio, ve kterém je otevřen CustomActionProjectItem řešení).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Definování typů položek projektu služby SharePoint vlastní](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Vytváření šablon položek a projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Odkaz na schéma šablon sady Visual Studio](/visualstudio/extensibility/visual-studio-template-schema-reference)   
 [Postupy: použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md)   
 [Výchozí umístění vlastní akce a ID](http://go.microsoft.com/fwlink/?LinkId=181964)  
  
  