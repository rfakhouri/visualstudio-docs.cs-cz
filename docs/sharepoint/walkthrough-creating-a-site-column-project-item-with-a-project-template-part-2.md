---
title: "Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2 | Microsoft Docs"
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
ms.openlocfilehash: f0472688f9f36d2b14c89cc904bf6ce4badd6ca6
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2"></a>Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2
  Po definování vlastního typu položky projektu služby SharePoint a přidružit ho pomocí šablony projektu v sadě Visual Studio, můžete také poskytnout průvodce pro šablony. Průvodce vám pomůže shromažďovat informace od uživatelů, když používat šablony pro vytvoření nového projektu, který obsahuje položky projektu. Informace, které slouží k inicializaci položky projektu.  
  
 V tomto návodu budete přidávat průvodce k šabloně projektu sloupce webu, která je znázorněn v [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md). Když uživatel vytvoří projektu sloupce webu, Průvodce shromažďuje informace o sloupci lokality (například základní typ a skupina) a přidá tyto informace do souboru Elements.xml v novém projektu.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytváření průvodce pro vlastního typu položky projektu služby SharePoint, která je přidružena k šabloně projektu.  
  
-   Definování vlastní průvodce uživatelské rozhraní, které nahrazuje vestavěné průvodce pro projekty SharePoint v sadě Visual Studio.  
  
-   Vytvoření dvou *SharePoint – příkazy* používané k volání do místní web služby SharePoint, je-li spuštěn průvodce. SharePoint – příkazy jsou metody, které můžete využít k volání rozhraní API v objektovém modelu serveru SharePoint rozšířeními sady Visual Studio. Další informace najdete v tématu [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
-   Nahraditelné parametry pomocí k chybě při inicializaci soubory projektu služby SharePoint s daty, která shromažďujete v průvodci.  
  
-   Vytvoření nového souboru .snk v každé nové instance projektu sloupce webu. Tento soubor se používá k podepsání projektu výstup tak, aby sestavení řešení služby SharePoint můžete nasadit do globální mezipaměti sestavení.  
  
-   Ladění a testování průvodce.  
  
> [!NOTE]  
>  Můžete si stáhnout ukázku, která obsahuje dokončené projekty, kódu a další soubory v tomto návodu z následujícího umístění: [http://go.microsoft.com/fwlink/?LinkId=191369](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, musíte nejdřív vytvořit řešení SiteColumnProjectItem provedením [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).  
  
 Potřebujete taky následující součásti na vývojovém počítači k dokončení tohoto názorného postupu:  
  
-   Podporované edice systému Windows, SharePoint a Visual Studio. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK. Tento návod používá **projektu VSIX** šablony v sadě SDK k vytvoření balíčku VSIX pro nasazení položka projektu. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Znalost následující koncepty je užitečné, ale není nutné k dokončení průvodce:  
  
-   Průvodce pro šablony projektů a položek v sadě Visual Studio. Další informace najdete v tématu [postupy: použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md) a <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní.  
  
-   Sloupce webu ve službě SharePoint. Další informace najdete v tématu [sloupce](http://go.microsoft.com/fwlink/?LinkId=183547).  
  
##  <a name="wizardcomponents"></a>Seznámení se s komponentami Průvodce  
 Průvodce, který je ukázáno v tomto návodu obsahuje několik komponent. Následující tabulka popisuje tyto součásti.  
  
|Součást|Popis|  
|---------------|-----------------|  
|Průvodce implementací|Toto je třída, s názvem `SiteColumnProjectWizard`, který implementuje <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní. Toto rozhraní definuje metody, které Visual Studio volá při spuštění a dokončení a v určitou dobu během průvodce spouští Průvodce.|  
|Průvodce uživatelského rozhraní|Je to na základě WPF okno, s názvem `WizardWindow`. Toto okno obsahuje dvě uživatelských ovládacích prvků s názvem `Page1` a `Page2`. Tyto uživatelské ovládací prvky představují dvou stránkách průvodce.<br /><br /> V tomto návodu <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> metoda implementace Průvodce zobrazí Průvodce uživatelského rozhraní.|  
|Průvodce datový model|Jedná se o zprostředkující třídu s názvem `SiteColumnWizardModel`, který poskytuje vrstva mezi Průvodce uživatelského rozhraní a Průvodce implementací. Tato ukázka používá tuto třídu můžete abstraktní implementace průvodce a Průvodce uživatelského rozhraní od sebe navzájem; Tato třída není požadovaná součást všechny průvodců.<br /><br /> V tomto návodu implementace průvodce předá `SiteColumnWizardModel` objektu do okna průvodce, pokud se zobrazí v Průvodci uživatelského rozhraní. Uživatelské rozhraní Průvodce používá metody tohoto objektu uložit hodnoty ovládacích prvků v uživatelském rozhraní a provádět úlohy, jako je ověření, že vstupní adresa URL je neplatná. Po dokončení Průvodce uživatele implementace Průvodce používá `SiteColumnWizardModel` objektem pro určení konečného stavu uživatelského rozhraní.|  
|Podpisový vedoucího projektu|Toto je pomocná třída s názvem `ProjectSigningManager`, který se používá Průvodce implementací k vytvoření nového souboru key.snk v každé nové instance projektu.|  
|SharePoint – příkazy|Toto jsou metody, které jsou používány v datovém modelu průvodce provést volání do místní web služby SharePoint, je-li spuštěn průvodce. Protože SharePoint – příkazy musí mít jako cíl pro rozhraní .NET Framework 3.5, tyto příkazy jsou implementované v jiném sestavení než zbytek kód průvodce.|  
  
## <a name="creating-the-projects"></a>Vytváření projektů  
 K dokončení tohoto postupu je nutné přidat několik projektů do řešení SiteColumnProjectItem, které jste vytvořili v [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md):  
  
-   Projekt WPF. Budete implementovat <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní a definovat Průvodce uživatelského rozhraní v tomto projektu.  
  
-   Projekt knihovny tříd, která definuje příkazy služby SharePoint. Tento projekt musí mít jako cíl rozhraní.NET Framework 3.5.  
  
 Spusťte Průvodce vytvořením projektů.  
  
#### <a name="to-create-the-wpf-project"></a>Vytvoření projektu WPF  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete SiteColumnProjectItem řešení.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro **SiteColumnProjectItem** uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
3.  V horní části **přidat nový projekt** dialogové okno pole, ujistěte se, že **rozhraní .NET Framework 4.5** je vybrán v seznamu verze rozhraní .NET Framework.  
  
4.  Rozbalte **Visual C#** uzlu nebo **jazyka Visual Basic** uzel a vyberte **Windows** uzlu.  
  
5.  V seznamu šablon projektu, zvolte **knihovny ovládací prvek WPF uživatelského**, název projektu **ProjectTemplateWizard**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Přidá **ProjectTemplateWizard** projektu a řešení a otevře výchozí UserControl1.xaml soubor.  
  
6.  Odstraňte soubor UserControl1.xaml z projektu.  
  
#### <a name="to-create-the-sharepoint-commands-project"></a>Chcete-li vytvořit příkazy projektu služby SharePoint  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel SiteColumnProjectItem řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V horní části **přidat nový projekt** dialogovém okně vyberte **rozhraní .NET Framework 3.5** v seznamu verze rozhraní .NET Framework.  
  
3.  Rozbalte **Visual C#** uzlu nebo **jazyka Visual Basic** uzel a potom zvolte **Windows** uzlu.  
  
4.  Vyberte **knihovny tříd** projektu šablony, název projektu **SharePointCommands**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Přidá **SharePointCommands** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
5.  Odstraňte soubor kódu Class1 z projektu.  
  
## <a name="configuring-the-projects"></a>Konfigurace projektů  
 Než vytvoříte v průvodci, musíte přidat některé soubory kódu a odkazy na sestavení do projektů.  
  
#### <a name="to-configure-the-wizard-project"></a>Ke konfiguraci projektu průvodce  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ProjectTemplateWizard** uzel projektu a potom zvolte **vlastnosti**.  
  
2.  V **Návrhář projektu**, vyberte **aplikace** kartu pro projekt Visual C# nebo **zkompilovat** Karta projektu jazyka Visual Basic.  
  
3.  Ujistěte se, že cílový framework je nastavená na rozhraní .NET Framework 4.5, není rozhraní .NET Framework 4.5 profil klienta.  
  
     Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
4.  Otevřete místní nabídku pro **ProjectTemplateWizard** projektu, zvolte **přidat**a potom zvolte **novou položku**.  
  
5.  Vyberte **okno (WPF)** položky, název položky **WizardWindow**a potom zvolte **přidat** tlačítko.  
  
6.  Přidejte dva **uživatelského ovládacího prvku (WPF)** položek do projektu a název je **Page1** a **strany Page2**.  
  
7.  Do projektu přidejte čtyři soubory kódu a řekněte jim tyto názvy:  
  
    -   SiteColumnProjectWizard  
  
    -   SiteColumnWizardModel  
  
    -   ProjectSigningManager  
  
    -   CommandIds  
  
8.  Otevřete místní nabídku pro **ProjectTemplateWizard** uzel projektu a potom zvolte **přidat odkaz na**.  
  
9. Rozbalte **sestavení** uzlu, vyberte **rozšíření** uzel a potom vyberte zaškrtnutí políček vedle následující sestavení:  
  
    -   EnvDTE  
  
    -   Sestavení Microsoft.VisualStudio.OLE.Interop  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.Shell.Interop.10.0  
  
    -   Microsoft.VisualStudio.Shell.Interop.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
10. Vyberte **OK** tlačítko Přidat sestavení do projektu.  
  
11. V **Průzkumníku řešení**v části **odkazy** složku **ProjectTemplateWizard** projektu, zvolte **EnvDTE**.  
  
12. V **vlastnosti** okno, změňte hodnotu **vložit zprostředkovatel komunikace s objekty typy** vlastnost **False**.  
  
13. Pokud vyvíjíte projekt Visual Basic, importujte obor názvů ProjectTemplateWizard do projektu pomocí **Návrhář projektu**.  
  
     Další informace najdete v tématu [postupy: Přidání nebo odebrání oborů názvů importovaný &#40; Visual Basic &#41; ](../ide/how-to-add-or-remove-imported-namespaces-visual-basic.md).  
  
#### <a name="to-configure-the-sharepointcommands-project"></a>Ke konfiguraci projektu SharePointCommands  
  
1.  V **Průzkumníku řešení**, vyberte **SharePointCommands** uzel projektu.  
  
2.  Na řádku nabídek zvolte **projektu**, **přidat existující položku**.  
  
3.  V **přidat existující položku** dialogové okno, přejděte do složky, která obsahuje soubory kódu pro ProjectTemplateWizard projekt a zvolte **CommandIds** souboru kódu.  
  
4.  Vyberte šipku vedle položky **přidat** tlačítko a potom vyberte **přidat jako odkaz** v nabídce, která se zobrazí.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Přidá do souboru kódu **SharePointCommands** projektu jako odkazu. Kód soubor je umístěný ve **ProjectTemplateWizard** projektu, ale kód v souboru také kompiluje v **SharePointCommands** projektu.  
  
5.  V **SharePointCommands** projekt, přidejte jiný kód soubor s názvem příkazy.  
  
6.  Zvolte SharePointCommands projekt a potom na panelu nabídek **projektu**, **přidat odkaz na**.  
  
7.  Rozbalte **sestavení** uzlu, vyberte **rozšíření** uzel a potom vyberte zaškrtnutí políček vedle následující sestavení:  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
8.  Vyberte **OK** tlačítko Přidat sestavení do projektu.  
  
## <a name="creating-the-wizard-model-signing-manager-and-sharepoint-command-ids"></a>Vytvoření modelu průvodce, správce a ID příkazu SharePoint  
 Přidejte do projektu ProjectTemplateWizard implementovat následující součásti v ukázce kód:  
  
-   Identifikátory příkazů služby SharePoint. Tyto řetězce Identifikujte příkazy služby SharePoint, které používá průvodce. Dále v tomto návodu přidáte kód do projektu SharePointCommands implementovat příkazy.  
  
-   Průvodce datový model.  
  
-   Podpisový správce projektu.  
  
 Další informace o těchto součástí naleznete v tématu [seznámení se s komponentami průvodce](#wizardcomponents).  
  
#### <a name="to-define-the-sharepoint-command-ids"></a>Chcete-li definovat identifikátory příkazů služby SharePoint  
  
1.  V projektu ProjectTemplateWizard otevření souboru kódu CommandIds a celý obsah souboru nahraďte následujícím kódem.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#5](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/commandids.cs#5)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#5](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/commandids.vb#5)]  
  
#### <a name="to-create-the-wizard-model"></a>Pro vytvoření modelu průvodce  
  
1.  Otevřete soubor kódu SiteColumnWizardModel a celý obsah souboru nahraďte následujícím kódem.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#6](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/sitecolumnwizardmodel.vb#6)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#6](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/sitecolumnwizardmodel.cs#6)]  
  
#### <a name="to-create-the-project-signing-manager"></a>Chcete-li vytvořit správce podpisový projektu  
  
1.  Otevřete soubor kódu ProjectSigningManager a celý obsah souboru nahraďte následujícím kódem.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#8](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/projectsigningmanager.vb#8)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#8](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/projectsigningmanager.cs#8)]  
  
## <a name="creating-the-wizard-ui"></a>Vytvoření uživatelského rozhraní Průvodce  
 Přidejte XAML pro definování uživatelského rozhraní Průvodce okna a dva uživatelské ovládací prvky, které poskytují rozhraní pro stránky průvodce a přidejte kód, který definuje chování ovládacích prvků okno a uživatele. Průvodce, který vytvoříte vypadá takto: integrované Průvodce pro projekty SharePoint v sadě Visual Studio.  
  
> [!NOTE]  
>  V následujících krocích projekt bude mít několik chyb kompilace po přidání jazyka XAML nebo kódu do projektu. Tyto chyby zmizí při přidání kódu v dalších krocích.  
  
#### <a name="to-create-the-wizard-window-ui"></a>Chcete-li vytvořit okno Průvodce uživatelského rozhraní  
  
1.  V projektu ProjectTemplateWizard otevřete místní nabídku pro soubor WizardWindow.xaml a zvolte **otevřete** a otevřete okno v návrháři.  
  
2.  V zobrazení XAML návrháře nahraďte aktuální XAML následující XAML. XAML definuje uživatelské rozhraní, které obsahuje záhlaví, <xref:System.Windows.Controls.Grid> obsahující stránky průvodce a navigační tlačítka v dolní části okna.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#10](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml#10)]  
  
    > [!NOTE]  
    >  Okno, který je vytvořen v této XAML je odvozený od <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> základní třídy. Když přidáte vlastní dialogové okno WPF k sadě Visual Studio, doporučujeme odvozování vašem dialogovém okně z této třídy tak, aby měl konzistentní stylů s další dialogová okna Visual Studio a abyste předešli problémům modální dialogové okno, které by jinak mohlo dojít. Další informace najdete v tématu [vytváření a správa modální dialogová okna](/visualstudio/extensibility/creating-and-managing-modal-dialog-boxes).  
  
3.  Pokud vyvíjíte projekt Visual Basic, odeberte `ProjectTemplateWizard` oboru názvů z `WizardWindow` název třídy v `x:Class` atribut `Window` elementu. Tento element má na prvním řádku XAML. Když jste hotovi, první řádek by měl vypadat jako v následujícím příkladu.  
  
    ```  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  Otevřete soubor kódu pro soubor WizardWindow.xaml.  
  
5.  Nahraďte obsah souboru za důvěryhodný, s výjimkou `using` deklarace v horní části souboru, s následujícím kódem.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#4](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml.vb#4)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#4](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml.cs#4)]  
  
#### <a name="to-create-the-first-wizard-page-ui"></a>Chcete-li vytvořit první stránku průvodce uživatelského rozhraní  
  
1.  V projektu ProjectTemplateWizard otevřete místní nabídku pro soubor Page1.xaml a zvolte **otevřete** otevřete uživatelského ovládacího prvku v návrháři.  
  
2.  V zobrazení XAML návrháře nahraďte aktuální XAML následující XAML. XAML definuje uživatelské rozhraní, které obsahuje textové pole, kde mohou uživatelé zadat adresu URL místních webů, které chcete použít pro ladění. Uživatelské rozhraní obsahuje také možnost tlačítka, pomocí kterého mohou uživatelé zadat, zda je projekt v izolovaném prostoru.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#11](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/page1.xaml#11)]  
  
3.  Pokud vyvíjíte projekt Visual Basic, odeberte `ProjectTemplateWizard` oboru názvů z `Page1` název třídy v `x:Class` atribut `UserControl` elementu. Toto je první řádek XAML. Až skončíte, první řádek by měla vypadat podobně jako tento.  
  
    ```  
    <UserControl x:Class="Page1"  
    ```  
  
4.  Nahraďte obsah souboru Page1.xaml, s výjimkou `using` deklarace v horní části souboru, s následujícím kódem.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#2](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/page1.xaml.vb#2)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#2](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/page1.xaml.cs#2)]  
  
#### <a name="to-create-the-second-wizard-page-ui"></a>Chcete-li vytvořit druhé stránce průvodce uživatelského rozhraní  
  
1.  V projektu ProjectTemplateWizard otevřete místní nabídku pro soubor Page2.xaml a zvolte **otevřete**.  
  
     Otevře se v Návrháři uživatelského ovládacího prvku.  
  
2.  V zobrazení jazyka XAML nahraďte aktuální XAML následující XAML. XAML definuje uživatelské rozhraní, které zahrnuje rozevíracího seznamu pro výběr základní typ sloupce webu, pole se seznamem pro zadání vestavěná nebo vlastní skupinu, do které chcete zobrazit v galerii sloupec lokality a textové pole pro zadání názvu sloupce webu.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#12](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/page2.xaml#12)]  
  
3.  Pokud vyvíjíte projekt Visual Basic, odeberte `ProjectTemplateWizard` oboru názvů z `Page2` název třídy v `x:Class` atribut `UserControl` elementu. Toto je první řádek XAML. Až skončíte, první řádek by měla vypadat podobně jako tento.  
  
    ```  
    <UserControl x:Class="Page2"  
    ```  
  
4.  Nahraďte obsah souboru kódu na pozadí pro soubor Page2.xaml, s výjimkou `using` deklarace v horní části souboru, s následujícím kódem.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#3](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/page2.xaml.vb#3)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#3](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/page2.xaml.cs#3)]  
  
## <a name="implementing-the-wizard"></a>Implementace průvodce  
 Definujte hlavní funkce Průvodce implementací <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní. Toto rozhraní definuje metody, které Visual Studio volá při spuštění a dokončení a v určitou dobu během průvodce spouští Průvodce.  
  
#### <a name="to-implement-the-wizard"></a>K implementaci Průvodce  
  
1.  V projektu ProjectTemplateWizard otevřete soubor SiteColumnProjectWizard kódu.  
  
2.  Celý obsah souboru nahraďte následujícím kódem.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#7](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/sitecolumnprojectwizard.vb#7)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#7](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/sitecolumnprojectwizard.cs#7)]  
  
## <a name="creating-the-sharepoint-commands"></a>Vytváření příkazů služby SharePoint  
 Vytvořte dva vlastní příkazy, které volají do objektový model serveru SharePoint. Jeden příkaz určuje, zda je adresa URL webu, že uživatel zadá v Průvodci platný. Další příkaz načte všechny typy polí z zadaném webu SharePoint tak, aby mohou uživatelé vybrat, která z nich chcete použít jako základ pro jejich nový sloupec webu.  
  
#### <a name="to-define-the-sharepoint-commands"></a>Chcete-li definovat příkazy služby SharePoint  
  
1.  V **SharePointCommands** projektu, otevřete soubor kódu příkazy.  
  
2.  Celý obsah souboru nahraďte následujícím kódem.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#9](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/sharepointcommands/commands.vb#9)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#9](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/sharepointcommands/commands.cs#9)]  
  
## <a name="checkpoint"></a>Kontrolní bod  
 V tomto okamžiku návodu, je celý kód pro průvodce v projektu. Sestavte projekt a ujistěte se, že se zkompiluje bez chyb.  
  
#### <a name="to-build-your-project"></a>K sestavení projektu  
  
1.  Na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
## <a name="removing-the-keysnk-file-from-the-project-template"></a>Odstraňuje se soubor key.snk z šablony projektu  
 V [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md), šablona projektu, který jste vytvořili obsahuje key.snk soubor, který se používá k podepisování každá instance projektu sloupce webu. Tento soubor key.snk již není nezbytné, protože Průvodce nyní vytvoří nový soubor key.snk pro každý projekt. Odeberte soubor key.snk z šablony projektu a odebrat odkazy na tento soubor.  
  
#### <a name="to-remove-the-keysnk-file-from-the-project-template"></a>Chcete-li odebrat soubor key.snk z šablony projektu  
  
1.  V **Průzkumníku řešení**v části **SiteColumnProjectTemplate** uzlu, otevřete místní nabídku pro **key.snk** souboru a potom vyberte **odstranit**.  
  
2.  V dialogovém okně potvrzení zvolte **OK** tlačítko.  
  
3.  V části **SiteColumnProjectTemplate** uzlu, otevřete soubor SiteColumnProjectTemplate.vstemplate a potom z něj odebrat následující element.  
  
    ```  
    <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
    ```  
  
4.  Soubor uložte a zavřete.  
  
5.  V části **SiteColumnProjectTemplate** uzlu, otevřete soubor ProjectTemplate.csproj nebo ProjectTemplate.vbproj a pak odeberte následující `PropertyGroup` element z něj.  
  
    ```  
    <PropertyGroup>  
      <SignAssembly>true</SignAssembly>  
      <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
    </PropertyGroup>  
    ```  
  
6.  Odebrat následující `None` elementu.  
  
    ```  
    <None Include="key.snk" />  
    ```  
  
7.  Soubor uložte a zavřete.  
  
## <a name="associating-the-wizard-with-the-project-template"></a>Přidružení průvodce pomocí šablony projektu  
 Teď, když jste implementovali průvodce, je nutné přidružit průvodce **sloupec lokality** šablona projektu. Existují tři postupy, které je třeba provést k tomu:  
  
1.  Podepsání sestavení silným názvem průvodce.  
  
2.  Získání tokenu veřejného klíče pro sestavení průvodce.  
  
3.  Přidat odkaz na sestavení průvodce v souboru .vstemplate **sloupec lokality** šablona projektu.  
  
#### <a name="to-sign-the-wizard-assembly-with-a-strong-name"></a>K podepsání Průvodce sestavení se silným názvem  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ProjectTemplateWizard** projektu a potom vyberte **vlastnosti**.  
  
2.  Na **podpisování** vyberte **podepsání sestavení** zaškrtávací políčko.  
  
3.  V **vyberte soubor klíče se silným názvem** vyberte  **\<nová... >**.  
  
4.  V **vytvořit klíč se silným názvem** dialogovém okně zadejte název pro nový soubor klíče, zrušte **chránit Moje soubor klíče s heslem** zaškrtněte políčko a potom vyberte **OK** tlačítko.  
  
5.  Otevřete místní nabídku pro **ProjectTemplateWizard** projektu a potom vyberte **sestavení** k vytvoření souboru ProjectTemplateWizard.dll.  
  
#### <a name="to-get-the-public-key-token-for-the-wizard-assembly"></a>K získání tokenu veřejného klíče pro sestavení průvodce  
  
1.  Na **nabídce Start**, zvolte **všechny programy**, zvolte **Microsoft Visual Studio**, zvolte **nástroje sady Visual Studio**a potom zvolte  **Příkazový řádek vývojáře**.  
  
     Otevře se okno příkazového řádku Visual Studia.  
  
2.  Spusťte následující příkaz, nahraďte *PathToWizardAssembly* s úplnou cestou integrovaný ProjectTemplateWizard.dll sestavení projektu ProjectTemplateWizard ve svém vývojovém počítači:  
  
    ```  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     Token veřejného klíče pro sestavení ProjectTemplateWizard.dll se zapíše do okna příkazového řádku Visual Studia.  
  
3.  Nechte okno příkazového řádku Visual Studia otevřené. Token veřejného klíče budete potřebovat při dalším postupu.  
  
#### <a name="to-add-a-reference-to-the-wizard-assembly-in-the-vstemplate-file"></a>Chcete-li přidat odkaz na sestavení průvodce v souboru .vstemplate  
  
1.  V **Průzkumníku řešení**, rozbalte **SiteColumnProjectTemplate** uzel projektu a otevřete soubor SiteColumnProjectTemplate.vstemplate.  
  
2.  U konce souboru, přidejte následující `WizardExtension` element mezi `</TemplateContent>` a `</VSTemplate>` značky. Nahraďte *tokenu* hodnotu `PublicKeyToken` atributem, token veřejného klíče, který jste získali v předchozím postupu.  
  
    ```  
    <WizardExtension>  
      <Assembly>ProjectTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=your token</Assembly>  
      <FullClassName>ProjectTemplateWizard.SiteColumnProjectWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     Další informace o `WizardExtension` elementu, najdete v části [WizardExtension – Element &#40; Šablony sady Visual Studio &#41; ](/visualstudio/extensibility/wizardextension-element-visual-studio-templates).  
  
3.  Soubor uložte a zavřete.  
  
## <a name="adding-replaceable-parameters-to-the-elementsxml-file-in-the-project-template"></a>Přidání do souboru Elements.xml v šabloně projektů nahraditelné parametry  
 Přidejte do souboru Elements.xml v projektu SiteColumnProjectTemplate několik nahraditelné parametry. Tyto parametry jsou inicializovány v `RunStarted` metoda v `SiteColumnProjectWizard` třídu, která je definována dříve. Když uživatel vytvoří projektu sloupce webu, Visual Studio automaticky nahradí tyto parametry v souboru Elements.xml v novém projektu hodnot zadaných v průvodci.  
  
 Nahraditelné parametr je token, který začíná a končí znak dolaru ($). Kromě definování vlastní nahraditelné parametry, můžete použít předdefinované parametry, které jsou definovány a inicializuje pomocí systému projektu služby SharePoint. Další informace najdete v tématu [nahraditelné parametry](../sharepoint/replaceable-parameters.md).  
  
#### <a name="to-add-replaceable-parameters-to-the-elementsxml-file"></a>Chcete-li přidat do souboru Elements.xml nahraditelné parametry  
  
1.  V projektu SiteColumnProjectTemplate nahraďte obsah souboru Elements.xml následující kód XML.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <Field ID="{$guid5$}"   
             Name="$fieldname$"   
             DisplayName="$fieldname$"   
             Type="$selectedfieldtype$"   
             Group="$selectedgrouptype$">  
      </Field>  
    </Elements>  
    ```  
  
     Nové XML změní hodnoty `Name`, `DisplayName`, `Type`, a `Group` atributy pro vlastní nahraditelné parametry.  
  
2.  Soubor uložte a zavřete.  
  
## <a name="adding-the-wizard-to-the-vsix-package"></a>Průvodce přidáním balíčku VSIX  
 K nasazení průvodce k balíčku VSIX, který obsahuje šablona projektu sloupce webu, přidejte do souboru source.extension.vsixmanifest v projektu VSIX odkazy na projekt průvodce a příkazy projektu služby SharePoint.  
  
#### <a name="to-add-the-wizard-to-the-vsix-package"></a>Chcete-li přidat průvodce balíčku VSIX  
  
1.  V **Průzkumníku řešení**v **SiteColumnProjectItem** projektu, otevřete místní nabídku pro **source.extension.vsixmanifest** souboru a potom vyberte **Otevřete**.  
  
     Visual Studio otevře soubor v editoru manifestu.  
  
2.  Na **prostředky** karta editoru, vyberte **nový** tlačítko.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
3.  V **typ** vyberte **Microsoft.VisualStudio.Assembly**.  
  
4.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
5.  V **projektu** vyberte **ProjectTemplateWizard**a potom zvolte **OK** tlačítko.  
  
6.  Na **prostředky** karta editoru, vyberte **nový** tlačítko znovu.  
  
     **Přidat nový prostředek** otevře se dialogové okno.  
  
7.  V **typ** seznamu, zadejte **SharePoint.Commands.v4**.  
  
8.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
9. V **projektu** seznam, vyberte **SharePointCommands** projektu a potom vyberte **OK** tlačítko.  
  
10. Na řádku nabídek zvolte **sestavení**, **sestavit řešení**a pak se ujistěte, že sestavení řešení bez chyb.  
  
## <a name="testing-the-wizard"></a>Testování průvodce  
 Nyní jste připraveni k testování průvodce. Nejprve spusťte ladění řešení SiteColumnProjectItem v experimentální instanci sady Visual Studio. Otestujte Průvodce projektu sloupce webu v experimentální instanci sady Visual Studio. Nakonec sestavte a spusťte projekt ověřte, že sloupec lokality funguje podle očekávání.  
  
#### <a name="to-start-debugging-the-solution"></a>Spustit ladění řešení  
  
1.  Restartujte Visual Studio s přihlašovacími údaji správce a pak otevřete SiteColumnProjectItem řešení.  
  
2.  V projektu ProjectTemplateWizard otevřete soubor SiteColumnProjectWizard kódu a pak přidejte zarážku na první řádek kódu `RunStarted` metoda.  
  
3.  Na řádku nabídek zvolte **ladění**, **výjimky**.  
  
4.  V **výjimky** dialogové okno pole, ujistěte se, že **vyvolaná** a **neošetřené uživatelem** zaškrtnutí políček u **běžné výjimky za běhu jazyka**jsou vymazány a potom vyberte **OK** tlačítko.  
  
5.  Spuštění ladění výběrem **F5** klíč, nebo v nabídce panelu Výběr **ladění**, **spustit ladění**.  
  
     Visual Studio nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Site Column\1.0 a spustí experimentální instanci sady Visual Studio. Položka projektu budete testovat v této instanci sady Visual Studio.  
  
#### <a name="to-test-the-wizard-in-visual-studio"></a>K testování průvodce v sadě Visual Studio  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  Rozbalte položku **Visual C#** uzlu nebo **jazyka Visual Basic** uzlu (v závislosti na jazyce, který podporuje vaše šablona projektu), rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
3.  V seznamu šablon projektu, zvolte **sloupec lokality**, název projektu **SiteColumnWizardTest**a potom zvolte **OK** tlačítko.  
  
4.  Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou jste nastavili výše v `RunStarted` metoda.  
  
5.  Pokračujte výběrem ladění projektu **F5** klíč, nebo v nabídce panelu Výběr **ladění**, **pokračovat**.  
  
6.  V **Průvodce vlastním nastavením SharePoint**, zadejte adresu URL webu, který chcete použít pro ladění a potom zvolte **Další** tlačítko.  
  
7.  Na druhé stránce **Průvodce vlastním nastavením SharePoint**, proveďte následující výběr:  
  
    -   V **typ** vyberte **Boolean**.  
  
    -   V **skupiny** vyberte **vlastní logická sloupce**.  
  
    -   V **název** zadejte **Moje sloupec Logická**a potom zvolte **Dokončit** tlačítko.  
  
     V **Průzkumníku řešení**, se zobrazí nový projekt a obsahuje položka projektu s názvem **pole1**, a otevře se v editoru Visual Studio Elements.xml souboru projektu.  
  
8.  Ověřte, zda Elements.xml obsahuje hodnoty, které jste zadali v průvodci.  
  
#### <a name="to-test-the-site-column-in-sharepoint"></a>K testování sloupec webu ve službě SharePoint  
  
1.  V experimentální instanci sady Visual Studio vyberte klávesy F5.  
  
     Sloupec lokality se zabalí a nasazené na webu služby SharePoint lokality, který **adresa URL webu** určuje vlastnosti projektu. Otevře se webový prohlížeč na stránku výchozího tohoto webu.  
  
    > [!NOTE]  
    >  Pokud **ladění skriptů zakázáno** se zobrazí dialogové okno, vyberte **Ano** tlačítka pokračujte ladění projektu.  
  
2.  Na **Akce webu** nabídce zvolte **nastavení lokality**.  
  
3.  Na stránce Nastavení lokality pod **galerií**, vyberte **sloupce webu** odkaz.  
  
4.  V seznamu sloupců webu, ověřte, že **vlastní logická sloupce** skupina obsahuje sloupec s názvem **Moje sloupec Logická**a pak zavřete webový prohlížeč.  
  
## <a name="cleaning-up-the-development-computer"></a>Čištění vývojovém počítači  
 Po dokončení testování položky projektu odebrání šablona projektu experimentální instanci sady Visual Studio.  
  
#### <a name="to-clean-up-the-development-computer"></a>Vyčistěte vývojovém počítači  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **nástroje**, **rozšíření a aktualizace**.  
  
     **Rozšíření a aktualizace** otevře se dialogové okno.  
  
2.  V seznamu rozšíření, vyberte **sloupec lokality**a potom zvolte **odinstalovat** tlačítko.  
  
3.  V dialogovém okně, které se zobrazí, vyberte **Ano** tlačítko potvrďte, že chcete odinstalovat rozšíření a potom vyberte **restartovat nyní** tlačítko k dokončení odinstalace.  
  
4.  Zavřete experimentální instanci sady Visual Studio a instance, ve kterém je otevřen CustomActionProjectItem řešení.  
  
     Informace o tom, jak nasadit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] rozšíření, najdete v části [přesouvání rozšíření Visual Studia](/visualstudio/extensibility/shipping-visual-studio-extensions).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Definování typů položek projektu služby SharePoint vlastní](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Vytváření šablon položek a projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Odkaz na schéma šablon sady Visual Studio](/visualstudio/extensibility/visual-studio-template-schema-reference)   
 [Postupy: Použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md)  
  
  