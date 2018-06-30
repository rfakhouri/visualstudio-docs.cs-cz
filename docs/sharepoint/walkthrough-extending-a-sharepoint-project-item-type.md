---
title: 'Návod: Rozšiřování typu položky projektu služby SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b7d0604e0e80fcb0fa14c65bd57669f60e68fd11
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118262"
---
# <a name="walkthrough-extend-a-sharepoint-project-item-type"></a>Návod: Rozšíření typu položky projektu SharePoint
  Můžete použít **modelu připojení obchodních dat** položka projektu pro vytvoření modelu pro službu Business Data Connectivity (BDC) ve službě SharePoint. Ve výchozím nastavení když vytvoříte model pomocí této položky projektu data v modelu se uživatelům nezobrazí. Musíte taky vytvořit externího seznamu ve službě SharePoint umožňuje uživatelům zobrazit data.  
  
 V tomto návodu vytvoříte rozšíření pro **modelu připojení obchodních dat** položka projektu. Vývojáři použít k vytvoření externího seznamu v jejich projekt, který zobrazí data v modelu služby BDC rozšíření. Tento návod ukazuje následující úlohy:  
  
-   Vytváření rozšíření pro Visual Studio, který provádí dvě hlavní úlohy:  
  
    -   Generuje externí seznam, který se zobrazuje data v modelu služby BDC. Rozšíření používá objektový model pro systému projektu služby SharePoint k vygenerování *Elements.xml* soubor, který definuje seznamu. Také přidá soubor do projektu tak, aby nasazení společně s modelu služby BDC.  
  
    -   Přidá položky místní nabídky k **modelu připojení obchodních dat** položky v projektu **Průzkumníku řešení**. Vývojáři mohou kliknutím na tuto položku pro vytvoření externího seznamu pro modelu služby BDC.  
  
-   Vytváření rozšíření pro Visual Studio (VSIX) balíčku pro nasazení sestavení rozšíření.  
  
-   Testování rozšíření.  
  
## <a name="prerequisites"></a>Požadavky  
 Následující součásti na vývojovém počítači k dokončení tohoto názorného postupu potřebujete:  
  
-   Podporované edice systému Microsoft Windows, SharePoint a Visual Studio. Další informace najdete v tématu [požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!include[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Tento návod používá **projektu VSIX** šablony v sadě SDK k vytvoření balíčku VSIX pro nasazení položka projektu. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Znalost následující koncepty je užitečné, ale není nutné k dokončení průvodce:  
  
-   Služby BDC [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]. Další informace najdete v tématu [BDC architektura](http://go.microsoft.com/fwlink/?LinkId=177798).  
  
-   Schéma XML pro modelů služby BDC. Další informace najdete v tématu [Infrastruktura modelu služby BDC](http://go.microsoft.com/fwlink/?LinkId=177799).  
  
## <a name="create-the-projects"></a>Vytváření projektů
 K dokončení tohoto postupu potřebujete vytvořit dva projekty:  
  
-   Projekt VSIX k vytvoření balíčku VSIX pro rozšíření položky projektu nasazení.  
  
-   Projekt knihovny tříd, který implementuje rozšíření položky projektu.  
  
 Spusťte Průvodce vytvořením projektů.  
  
#### <a name="to-create-the-vsix-project"></a>Vytvoření projektu VSIX  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na řádku nabídek zvolte **soubor** > **nový** > **projektu**.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **rozšiřitelnost** uzlu.  
  
    > [!NOTE]  
    >  **Rozšiřitelnost** uzel je k dispozici pouze v případě, že nainstalujete Visual Studio SDK. Další informace najdete v části požadavky dříve v tomto tématu.  
  
4.  V seznamu v horní části **nový projekt** dialogovém okně vyberte **rozhraní .NET Framework 4.5**.  
  
     Rozšíření nástrojů SharePoint vyžaduje funkce v této verzi rozhraní .NET Framework.  
  
5.  Vyberte **projektu VSIX** šablony.  
  
6.  V **název** zadejte **GenerateExternalDataLists**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **GenerateExternalDataLists** projektu do **Průzkumníku řešení**.  
  
7.  Pokud soubor source.extension.vsixmanifest automaticky neotevře, otevřete jeho místní nabídky v projektu GenerateExternalDataLists a potom zvolte **otevřete**  
  
8.  Ověřte, zda má soubor source.extension.vsixmanifest položku neprázdné (zadejte Contoso) pro pole Author soubor uložte a zavřete ji.  
  
#### <a name="to-create-the-extension-project"></a>Vytvoření projektu rozšíření  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **GenerateExternalDataLists** uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V **přidat nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **Windows** uzlu.  
  
3.  V seznamu nahoře v dialogovém okně vyberte **rozhraní .NET Framework 4.5**.  
  
4.  V seznamu šablon projektu, zvolte **knihovny tříd**.  
  
5.  V **název** zadejte **BdcProjectItemExtension**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **BdcProjectItemExtension** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
6.  Odstraňte soubor kódu Class1 z projektu.  
  
## <a name="configure-the-extension-project"></a>Konfigurace projektu rozšíření
 Než napíšete kód k vytvoření rozšíření položky projektu, přidejte soubory kódu a odkazy na sestavení na projekt.  
  
#### <a name="to-configure-the-project"></a>Konfigurace projektu  
  
1.  V projektu BdcProjectItemExtension přidejte dva soubory kódu, které mají tyto názvy:  
  
    -   ProjectItemExtension  
  
    -   GenerateExternalDataLists  
  
2.  Zvolte projekt BdcProjectItemExtension a potom na panelu nabídek **projektu** > **přidat odkaz na**.  
  
3.  V části **sestavení** uzlu, vyberte **Framework** uzel a vyberte možnost zaškrtnutí políčka pro každou z následujících sestavení:  
  
    -   System.ComponentModel.Composition  
  
    -   WindowsBase  
  
4.  V části **sestavení** uzlu, vyberte **rozšíření** uzel a potom vyberte zaškrtávací pole pro následující sestavení:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  Vyberte **OK** tlačítko.  
  
## <a name="define-the-project-item-extension"></a>Definování rozšíření položky projektu
 Vytvořte třídu, která definuje rozšíření pro **modelu připojení obchodních dat** položka projektu. Můžete definovat rozšíření, třída implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> rozhraní. Toto rozhraní implementujte, kdykoli budete chtít rozšířit existující typ položky projektu.  
  
#### <a name="to-define-the-project-item-extension"></a>Můžete definovat rozšíření položky projektu  
  
1.  Vložte následující kód do kódem ProjectItemExtension.  
  
    > [!NOTE]  
    >  Po přidání tohoto kódu, projekt bude mít několik chyb kompilace. Tyto chyby zmizí při přidání kódu v dalších krocích.  
  
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../sharepoint/codesnippet/CSharp/generateexternaldatalists/bdcprojectitemextension/projectitemextension.cs#1)]
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../sharepoint/codesnippet/VisualBasic/generateexternaldatalists/bdcprojectitemextension/projectitemextension.vb#1)]  
  
## <a name="create-the-external-data-lists"></a>Vytváření seznamů externích dat
 Přidejte částečnou definici `GenerateExternalDataListsExtension` třídu, která vytvoří seznam externích dat pro každé entity v modelu služby BDC. Chcete-li vytvořit seznam externích dat, tento kód nejprve čte data entity v modelu služby BDC analýzou dat XML v souboru modelu služby BDC. Potom vytvoří instanci seznamu, která je založená na modelu služby BDC a přidá do projektu tuto instanci seznamu.  
  
#### <a name="to-create-the-external-data-lists"></a>Chcete-li vytvořit seznamy externích dat  
  
1.  Vložte následující kód do souboru kódu GenerateExternalDataLists.  
  
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../sharepoint/codesnippet/VisualBasic/generateexternaldatalists/bdcprojectitemextension/generateexternaldatalists.vb#2)]
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../sharepoint/codesnippet/CSharp/generateexternaldatalists/bdcprojectitemextension/generateexternaldatalists.cs#2)]  
  
## <a name="checkpoint"></a>Kontrolní bod  
 V tomto okamžiku návodu, je celý kód pro rozšíření položky projektu v projektu. Sestavte řešení, abyste měli jistotu, že projekt zkompiluje bez chyb.  
  
#### <a name="to-build-the-solution"></a>K sestavení řešení  
  
1.  Na řádku nabídek zvolte **sestavení** > **sestavit řešení**.  
  
## <a name="create-a-vsix-package-to-deploy-the-project-item-extension"></a>Vytvoření balíčku VSIX pro nasazení rozšíření položky projektu
 K nasazení rozšíření, použijte k vytvoření balíčku VSIX VSIX projekt ve vašem řešení. Nejprve nakonfigurujte balíčku VSIX úpravou souboru source.extension.vsixmanifest, který je zahrnutý v projektu VSIX. Pak vytvořte balíčku VSIX vytvořením řešení.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Ke konfiguraci a vytvoření balíčku VSIX  
  
1.  V **Průzkumníku řešení**, otevřete v projektu GenerateExternalDataLists místní nabídku pro soubor source.extension.vsixmanifest a potom zvolte **otevřete**.  
  
     Visual Studio otevře soubor v editoru manifestu. Soubor source.extension.vsixmanifest je základem pro soubor extension.vsixmanifest je vyžadováno pro všechny balíčky VSIX. Další informace o tento soubor najdete v tématu [VSIX rozšíření schématu 1.0 odkaz](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  V **název produktu** zadejte **Generátor seznamu externích dat**.  
  
3.  V **Autor** zadejte **Contoso**.  
  
4.  V **popis** zadejte **rozšíření pro položky projektu modelu připojení obchodních dat, které lze použít pro vygenerování externích dat**.  
  
5.  Na **prostředky** karta editoru, vyberte **nový** tlačítko.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
6.  V **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `MefComponent` element v souboru extension.vsixmanifest. Tento element určuje název sestavení rozšíření v balíčku VSIX. Další informace najdete v tématu [MEFComponent Element (VSX schéma)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
8.  V **projektu** vyberte **BdcProjectItemExtension**a potom zvolte **OK** tlačítko.  
  
9. Na řádku nabídek zvolte **sestavení** > **sestavit řešení**.  
  
10. Ujistěte se, že projekt zkompiluje a vytvoří bez chyb.  
  
11. Ujistěte se, že složku výstupu sestavení pro projekt GenerateExternalDataLists nyní obsahuje soubor GenerateExternalDataLists.vsix.  
  
     Ve výchozím nastavení, je složku výstupu sestavení... \bin\Debug složky pod složkou, která obsahuje soubor projektu.  
  
## <a name="test-the-project-item-extension"></a>Testování rozšíření položky projektu
 Nyní jste připraveni k testování rozšíření položky projektu. Nejprve spusťte ladění rozšíření projektu v experimentální instanci sady Visual Studio. Potom pomocí rozšíření v experimentální instanci sady Visual Studio k vytvoření externího seznamu pro modelu služby BDC. Nakonec otevřete externí seznam na webu služby SharePoint k ověření, že funguje podle očekávání.  
  
#### <a name="to-start-debugging-the-extension"></a>Spustit ladění – rozšíření  
  
1.  V případě potřeby restartujte Visual Studio s přihlašovacími údaji správce a pak otevřete řešení GenerateExternalDataLists.  
  
2.  V projektu BdcProjectItemExtension otevřete kódem ProjectItemExtension a pak přidejte zarážku řádek kódu `Initialize` metoda.  
  
3.  Otevřete soubor s kódem GenerateExternalDataLists a poté přidejte zarážku na první řádek kódu `GenerateExternalDataLists_Execute` metoda.  
  
4.  Spuštění ladění výběrem **F5** klíč, nebo v nabídce panelu Výběr **ladění** > **spustit ladění**.  
  
     Visual Studio nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\External Data List Generator\1. 0 a spustí experimentální instanci sady Visual Studio. Položka projektu budete testovat v této instanci sady Visual Studio.  
  
#### <a name="to-test-the-extension"></a>K testování rozšíření  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **soubor** > **nový** > **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **šablony** uzlu, rozbalte **Visual C#** uzlu, rozbalte položku **SharePoint** uzlu a potom Zvolte **2010**.  
  
3.  V seznamu v horní části dialogových oken, ujistěte se, že **rozhraní .NET Framework 3.5** je vybrána. Projekty pro [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] vyžadovat tuto verzi rozhraní .NET Framework.  
  
4.  V seznamu šablon projektu, zvolte **projektu služby SharePoint 2010**.  
  
5.  V **název** zadejte **SharePointProjectTestBDC**a potom zvolte **OK** tlačítko.  
  
6.  Průvodce nastavením služby SharePoint, zadejte adresu URL webu, který chcete použít pro ladění, zvolte **nasadit jako řešení farmy**a potom zvolte **Dokončit**tlačítko.  
  
7.  Otevřete místní nabídky projektu SharePointProjectTestBDC, zvolte **přidat**a potom zvolte **novou položku**.  
  
8.  V **přidat NewItem - SharePointProjectTestBDC** dialogové okno pole, rozbalte uzel nainstalovaný jazyk, rozbalte **SharePoint** uzlu.  
  
9. Vyberte **2010** uzel a potom zvolte **modelu připojení obchodních dat (pouze řešení farmy)** šablony.  
  
10. V **název** zadejte **TestBDCModel**a potom zvolte **přidat** tlačítko.  
  
11. Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou nastavíte v `Initialize` metoda kódem ProjectItemExtension.  
  
12. V zastaveném instanci sady Visual Studio, vyberte **F5** klíče, nebo v řádku nabídek zvolte **ladění** > **pokračovat** pokračujte ladění projektu.  
  
13. V experimentální instanci sady Visual Studio, vyberte **F5** klíče, nebo na řádku nabídek zvolte **ladění** > **spustit ladění** k vytvoření, nasazení a spuštění **TestBDCModel** projektu.  
  
     Otevře se webový prohlížeč na stránku výchozího webu služby SharePoint, která je určená pro ladění.  
  
14. Ověřte, zda **uvádí** část v oblasti Snadné spuštění ještě neobsahuje seznam, který je založen na výchozím modelu služby BDC do projektu. Seznam externích dat, musíte nejprve vytvořit buď přes uživatelské rozhraní služby SharePoint, nebo pomocí rozšíření položky projektu.  
  
15. Zavřete webový prohlížeč.  
  
16. V instanci sady Visual Studio, který má otevřete projekt TestBDCModel otevřete místní nabídku pro **TestBDCModel** uzlu v **Průzkumníku řešení**a potom zvolte **generovat externích dat Seznam**.  
  
17. Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou nastavíte v `GenerateExternalDataLists_Execute` metoda. Vyberte **F5** klíče, nebo na řádku nabídek zvolte **ladění** > **pokračovat** pokračujte ladění projektu.  
  
18. Experimentální instanci sady Visual Studio přidá instanci seznamu s názvem **Entity1DataList** k TestBDCModel projektu a instance také vytváří funkci s názvem **Feature2** seznam instance.  
  
19. Vyberte **F5** klíče, nebo na řádku nabídek zvolte **ladění** > **spustit ladění** k vytvoření, nasazení a spuštění projektu TestBDCModel.  
  
     Otevře se webový prohlížeč na stránku výchozího webu služby SharePoint, který se používá pro ladění.  
  
20. V **uvádí** části oblasti Snadné spuštění, vyberte **Entity1DataList** seznamu.  
  
21. Ověřte, jestli seznam obsahuje sloupce, které jsou pojmenované Identifier1 a zprávy, kromě jednu položku, který má hodnotu Identifier1 0 a hodnotu zprávy Hello World.  
  
     **Modelu připojení obchodních dat** generuje poskytující všech těchto dat modelu služby BDC výchozí šablona projektu.  
  
22. Zavřete webový prohlížeč.  
  
## <a name="clean-up-the-development-computer"></a>Vyčištění vývojovém počítači
 Po dokončení testování rozšíření položky projektu, odeberte externí seznam a modelu služby BDC z webu služby SharePoint a odeberte rozšíření položky projektu ze sady Visual Studio.  
  
#### <a name="to-remove-the-external-data-list-from-the-sharepoint-site"></a>Chcete-li odebrat seznamu externí data z webu služby SharePoint  
  
1.  V oblasti Snadné spuštění webu služby SharePoint, zvolte **Entity1DataList** seznamu.  
  
2.  Na pásu karet na webu služby SharePoint, vyberte **seznamu** kartě.  
  
3.  Na **seznamu** ve **nastavení** skupiny, vyberte **nastavení seznamu**.  
  
4.  V části **oprávnění a správa**, zvolte **odstranit tento seznam**a potom zvolte **OK** potvrďte chcete odeslat do koše seznamu.  
  
5.  Zavřete webový prohlížeč.  
  
#### <a name="to-remove-the-bdc-model-from-the-sharepoint-site"></a>Chcete-li odebrat modelu služby BDC z webu služby SharePoint  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **sestavení** > **odvolat**.  
  
     Visual Studio odebere modelu služby BDC z webu služby SharePoint.  
  
#### <a name="to-remove-the-project-item-extension-from-visual-studio"></a>Chcete-li odebrat rozšíření položky projektu ze sady Visual Studio  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **nástroje** > **rozšíření a aktualizace**.  
  
     **Rozšíření a aktualizace** otevře se dialogové okno.  
  
2.  V seznamu rozšíření, vyberte **Generátor seznamu externích dat**a potom zvolte **odinstalovat** tlačítko.  
  
3.  V zobrazeném dialogu vyberte **Ano** potvrďte, že chcete odinstalovat rozšíření.  
  
4.  Zvolte **restartovat nyní** k dokončení odinstalace.  
  
5.  Zavřete obě instance sady Visual Studio (experimentální instanci a instance, ve kterém je otevřen řešení GenerateExternalDataLists).  
  
## <a name="see-also"></a>Viz také:
 [Rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  
