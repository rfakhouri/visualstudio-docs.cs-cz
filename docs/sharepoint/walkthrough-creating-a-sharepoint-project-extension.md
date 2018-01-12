---
title: "Návod: Vytváření rozšíření projektu služby SharePoint | Microsoft Docs"
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
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a03dd09525d29aaea31ef5c376814bd09747f90e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-a-sharepoint-project-extension"></a>Návod: Vytváření rozšíření projektu SharePoint
  Tento návod ukazuje postup vytvoření rozšíření pro projekty SharePoint. Můžete použít rozšíření projektu reakce na události na úrovni projektu například pokud je projekt přidat, odstranit nebo přejmenovat. Můžete také přidat vlastní vlastnosti nebo reagovat, když se změní hodnota vlastnosti. Na rozdíl od rozšíření položek projektu rozšíření nemůže být přidružena konkrétní typ projektu služby SharePoint. Při vytváření rozšíření projektu rozšíření načte, když jakýkoli druh projektu služby SharePoint je otevřen v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
 V tomto návodu vytvoříte vlastní vlastnost typu Boolean, který je přidán do jakéhokoli projektu SharePoint vytvořeného v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Pokud nastavíte hodnotu **True**, nové vlastnosti přidá nebo mapuje složku prostředků bitové kopie do projektu. Pokud nastavíte hodnotu **False**, složky bitových kopií je odebrána, pokud existuje. Další informace najdete v tématu [postupy: Přidání a odebrání mapované složky](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytváření [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] rozšíření pro projekty SharePoint, které provede následující akce:  
  
    -   Přidá vlastnost vlastních projektů do okna vlastností. Vlastnost se vztahuje na všechny projektu služby SharePoint.  
  
    -   Objektový model projektu služby SharePoint se používá k přidání mapované složky do projektu.  
  
    -   Používá [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] automatizace objektový model (DTE) pro odstranění mapované složky z projektu.  
  
-   Vytváření [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] rozšíření (VSIX) balíčku pro nasazení sestavení rozšíření vlastnosti projektu.  
  
-   Ladění a testování vlastnosti projektu.  
  
## <a name="prerequisites"></a>Požadavky  
 Následující součásti na vývojovém počítači k dokončení tohoto názorného postupu potřebujete:  
  
-   Podporované edice systému [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)], SharePoint a [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Tento návod používá **projektu VSIX** šablonu [!INCLUDE[TLA2#tla_sdk](../sharepoint/includes/tla2sharptla-sdk-md.md)] k vytvoření balíčku VSIX pro nasazení rozšíření vlastnosti projektu. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="creating-the-projects"></a>Vytváření projektů  
 K dokončení tohoto postupu je nutné vytvořit dva projekty:  
  
-   Projekt VSIX k vytvoření balíčku VSIX pro rozšíření projektu nasazení.  
  
-   Projekt knihovny tříd, který implementuje rozšíření projektu.  
  
 Spusťte Průvodce vytvořením projektů.  
  
#### <a name="to-create-the-vsix-project"></a>Vytvoření projektu VSIX  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **rozšiřitelnost** uzlu.  
  
    > [!NOTE]  
    >  Tento uzel je k dispozici pouze v případě, že nainstalujete Visual Studio SDK. Další informace najdete v části požadavky dříve v tomto tématu.  
  
4.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 4.5** v seznamu verze rozhraní .NET Framework a potom zvolte **projektu VSIX** šablony.  
  
5.  V **název** zadejte **ProjectExtensionPackage**a potom zvolte **OK** tlačítko.  
  
     **ProjectExtensionPackage** projektu se zobrazí v **Průzkumníku řešení**.  
  
#### <a name="to-create-the-extension-project"></a>Vytvoření projektu rozšíření  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **Windows**.  
  
3.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 4.5** v seznamu verze rozhraní .NET Framework a potom zvolte **knihovny tříd** šablona projektu.  
  
4.  V **název** zadejte **ProjectExtension**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Přidá **ProjectExtension** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
5.  Odstraňte soubor kódu Class1 z projektu.  
  
## <a name="configuring-the-project"></a>Konfigurace projektu  
 Než napíšete kód k vytvoření rozšíření projektu, přidejte soubory kódu a odkazy na sestavení na projekt.  
  
#### <a name="to-configure-the-project"></a>Konfigurace projektu  
  
1.  Přidání souboru kódu, který je pojmenován **CustomProperty** do projektu ProjectExtension.  
  
2.  Otevřete místní nabídku pro **ProjectExtension** projektu a potom vyberte **přidat odkaz na**.  
  
3.  V **správce odkazů - CustomProperty** dialogovém okně vyberte **Framework** uzel a potom zaškrtněte políčko vedle System.ComponentModel.Composition a System.Windows.Forms sestavení.  
  
4.  Vyberte **rozšíření** uzlu, zaškrtněte políčko vedle Microsoft.VisualStudio.SharePoint a EnvDTE sestavení a potom zvolte **OK** tlačítko.  
  
5.  V **Průzkumníku řešení**v části **odkazy** složku **ProjectExtension** projektu, zvolte **EnvDTE**.  
  
6.  V **vlastnosti** změňte **vložit zprostředkovatel komunikace s objekty typy** vlastnost **False**.  
  
## <a name="defining-the-new-sharepoint-project-property"></a>Definování vlastnosti nového projektu služby SharePoint  
 Vytvořte třídu, která definuje rozšíření projektu a chování nové vlastnosti projektu. Chcete-li definovat nové rozšíření projektu, třída implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> rozhraní. Toto rozhraní implementujte, kdykoli budete chtít definovat rozšíření projektu služby SharePoint. Také přidat <xref:System.ComponentModel.Composition.ExportAttribute> k třídě. Tento atribut umožňuje [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zjišťovat a načíst vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> implementace. Předat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> typ do konstruktoru atributu.  
  
#### <a name="to-define-the-new-sharepoint-project-property"></a>Chcete-li definovat nové vlastnosti projektu služby SharePoint  
  
1.  Vložte následující kód do souboru CustomProperty.  
  
     [!code-vb[SPExt_ProjectExtension#1](../sharepoint/codesnippet/VisualBasic/projectextension/customproperty.vb#1)]
     [!code-csharp[SPExt_ProjectExtension#1](../sharepoint/codesnippet/CSharp/projectextension/customproperty.cs#1)]  
  
## <a name="building-the-solution"></a>Sestavení řešení  
 V dalším kroku sestavte řešení, abyste měli jistotu, že se zkompiluje bez chyb.  
  
#### <a name="to-build-the-solution"></a>K sestavení řešení  
  
1.  Na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
## <a name="creating-a-vsix-package-to-deploy-the-project-property-extension"></a>Vytvoření balíčku VSIX pro nasazení rozšíření vlastnosti projektu  
 Nasazení rozšíření projektu, použijte k vytvoření balíčku VSIX VSIX projekt ve vašem řešení. Nejprve nakonfigurujte balíčku VSIX úpravou souboru source.extension.vsixmanifest, který je zahrnutý v projektu VSIX. Pak vytvořte balíčku VSIX vytvořením řešení.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Ke konfiguraci a vytvoření balíčku VSIX  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro soubor source.extension.vsixmanifest a potom zvolte **otevřete** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]soubor se otevře v návrháře manifestu. Informace, které se zobrazí v **Metadata** karta se zobrazí také v **rozšíření a aktualizace**. Všechny balíčky VSIX vyžadují soubor extension.vsixmanifest. Další informace o tento soubor najdete v tématu [VSIX rozšíření schématu 1.0 odkaz](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  V **název produktu** zadejte **vlastní vlastnost projektu**.  
  
3.  V **Autor** zadejte **Contoso**.  
  
4.  V **popis** zadejte **vlastní vlastnosti projektu služby SharePoint, která přepíná mapování složky bitových kopií prostředků do projektu**.  
  
5.  Vyberte **prostředky** a pak klikněte na příkaz **nový** tlačítko.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
6.  V **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `MEFComponent` element v souboru extension.vsixmanifest. Tento element určuje název sestavení rozšíření v balíčku VSIX. Další informace najdete v tématu [MEFComponent Element (VSX schéma)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  V **zdroj** seznam, vyberte **na projekt v aktuálním řešení** tlačítko.  
  
8.  V **projektu** vyberte **ProjectExtension**.  
  
     Tato hodnota určuje název sestavení, které umožňuje vytvářet v projektu.  
  
9. Zvolte **OK** zavřete **přidat nový prostředek** dialogové okno.  
  
10. Na řádku nabídek zvolte **soubor**, **Uložit vše** Když dokončíte a pak zavřete editor manifestu.  
  
11. Na řádku nabídek zvolte **sestavení**, **sestavit řešení**a pak se ujistěte, že projekt zkompiluje bez chyb.  
  
12. V **Průzkumníku řešení**, otevřete místní nabídku pro **ProjectExtensionPackage** projektu a zvolte **otevřete složky v Průzkumníku souborů** tlačítko.  
  
13. V **Průzkumníka souborů**, otevřete složku výstupu sestavení pro projekt ProjectExtensionPackage a potom ověřte, že složka obsahuje soubor s názvem ProjectExtensionPackage.vsix.  
  
     Ve výchozím nastavení, je složku výstupu sestavení... \bin\Debug složky pod složkou, která obsahuje soubor projektu.  
  
## <a name="testing-the-project-property"></a>Testování vlastnosti projektu  
 Nyní jste připraveni otestovat vlastní vlastnosti projektu. Je to nejjednodušší provádět ladit a testovat novou vlastnost rozšíření projektu v experimentální instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Tuto instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] se vytvoří při spuštění VSIX nebo jiných rozšiřitelnost projektů. Po ladění projektu, můžete nainstalovat rozšíření ve vašem systému a pak pokračujte ladit a testovat v pravidelných instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
#### <a name="to-debug-and-test-the-extension-in-an-experimental-instance-of-visual-studio"></a>Ladění a testování rozšíření v experimentální instanci sady Visual Studio  
  
1.  Restartujte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] s přihlašovacími údaji správce a pak otevřete řešení ProjectExtensionPackage.  
  
2.  Spuštění ladění sestavení projektu buď tak, že zvolíte **F5** klíč, nebo v nabídce panelu Výběr **ladění**, **spustit ladění**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Custom Project Property\1. 0 a spustí experimentální instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
3.  V experimentální instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvoření projektu služby SharePoint pro řešení farmy a použít výchozí hodnoty pro ostatní hodnoty v průvodci.  
  
    1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
    2.  V horní části **nový projekt** dialogovém okně vyberte **rozhraní .NET Framework 3.5** v seznamu verze rozhraní .NET Framework.  
  
         Rozšíření nástrojů SharePoint vyžaduje funkce v této verzi [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].  
  
    3.  V části **šablony** uzlu, rozbalte **Visual C#** nebo **jazyka Visual Basic** uzlu, vyberte **SharePoint** uzlu a potom vyberte **2010** uzlu.  
  
    4.  Vyberte **projektu služby SharePoint 2010** šablony a potom zadejte **ModuleTest** jako název projektu.  
  
4.  V **Průzkumníku řešení**, vyberte **ModuleTest** uzel projektu.  
  
     Nové vlastní vlastnosti **složky bitových kopií mapy** se zobrazí v **vlastnosti** okno s výchozí hodnotou **False**.  
  
5.  Změna hodnoty této vlastnosti na **True**.  
  
     Složku prostředků obrázků se přidá do projektu služby SharePoint.  
  
6.  Změna hodnoty této vlastnosti zpět do **False**.  
  
     Pokud se rozhodnete **Ano** v tlačítko **odstranit složky bitových kopií?** dialogové okno, bitové kopie se odstraní složku prostředků z projektu služby SharePoint.  
  
7.  Ukončete experimentální instance [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření projektů SharePoint](../sharepoint/extending-sharepoint-projects.md)   
 [Postupy: Přidání vlastnosti do projektů služby SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [Ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [Přidružení vlastních dat k rozšíření nástrojů služby SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  