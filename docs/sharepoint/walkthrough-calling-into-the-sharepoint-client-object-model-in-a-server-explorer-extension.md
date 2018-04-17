---
title: 'Návod: Volání do objektového modelu klienta pro SharePoint v rozšíření Průzkumníka serveru | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, client object model
- SharePoint commands [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4951d9960a3027e8d72bb0fbc72d551f123993ce
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension"></a>Návod: Volání do modelu klientského objektu služby SharePoint v rozšíření průzkumníka serveru
  Tento návod ukazuje, jak volat objektového modelu klienta služby SharePoint z rozšíření pro **připojení služby SharePoint** uzlu v **Průzkumníka serveru**. Další informace o tom, jak pomocí objektového modelu klienta služby SharePoint, naleznete v části [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytváření [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] rozšíření, která rozšiřuje **připojení služby SharePoint** uzlu **Průzkumníka serveru** následujícími způsoby:  
  
    -   Přidá rozšíření **Galerie webových částí** uzel za každý uzel serveru SharePoint v **Průzkumníka serveru**. Tento nový uzel obsahuje podřízené uzly, které představují jednotlivé webové části v galerii webových částí na webu.  
  
    -   Rozšíření definuje nový typ uzlu, který představuje instanci webové části. Tento nový typ uzlu je základem pro podřízené uzly v rámci nové **Galerie webových částí** uzlu. Zobrazí informace v nového typu uzlu webovou část **vlastnosti** okno webová část, která představuje uzel.  
  
-   Vytváření rozšíření pro Visual Studio (VSIX) balíčku pro nasazení rozšíření.  
  
-   Ladění a testování rozšíření.  
  
> [!NOTE]  
>  Rozšíření, které vytvoříte v tomto návodu podobné rozšíření, které vytvoříte v [návod: rozšíření Průzkumníka serveru pro zobrazení webové části](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md). Tento návod používá objektový model serveru SharePoint, ale tento návod provede stejné úlohy pomocí objektového modelu klienta.  
  
## <a name="prerequisites"></a>Požadavky  
 Následující součásti na vývojovém počítači k dokončení tohoto názorného postupu potřebujete:  
  
-   Podporované edice systému Windows, SharePoint a Visual Studio. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK. Tento návod používá **projektu VSIX** šablony v sadě SDK k vytvoření balíčku VSIX pro nasazení rozšíření. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
Znalost následující koncepty je užitečné, ale není nutné k dokončení průvodce:  
  
-   Pomocí objektového modelu klienta služby SharePoint. Další informace najdete v tématu [spravovaný objektový Model klienta](http://go.microsoft.com/fwlink/?LinkId=177797).  
  
-   Webové části služby SharePoint. Další informace najdete v tématu [přehled webových částí](http://go.microsoft.com/fwlink/?LinkId=177803).  
  
## <a name="creating-the-projects"></a>Vytváření projektů  
 K dokončení tohoto postupu je nutné vytvořit dva projekty:  
  
-   Projekt VSIX k vytvoření balíčku VSIX pro nasazení **Průzkumníka serveru** rozšíření.  
  
-   Projektu knihovny tříd, který implementuje **Průzkumníka serveru** rozšíření.  
  
 Spusťte Průvodce vytvořením projektů.  
  
#### <a name="to-create-the-vsix-project"></a>Vytvoření projektu VSIX  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **rozšiřitelnost**.  
  
    > [!NOTE]  
    >  **Rozšiřitelnost** uzel je k dispozici pouze v případě, že nainstalujete Visual Studio SDK. Další informace najdete v části požadavky dříve v tomto tématu.  
  
4.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 4.5** v seznamu verze rozhraní .NET Framework.  
  
     Rozšíření nástrojů SharePoint vyžaduje funkce v této verzi rozhraní .NET Framework.  
  
5.  Vyberte **projektu VSIX** šablony.  
  
6.  V **název** zadejte **WebPartNode**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **WebPartNode** projektu do **Průzkumníku řešení**.  
  
#### <a name="to-create-the-extension-project"></a>Vytvoření projektu rozšíření  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **Windows**.  
  
3.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 4.5** v seznamu verze rozhraní .NET Framework.  
  
4.  V seznamu šablon projektu, zvolte **knihovny tříd**.  
  
5.  V **název** zadejte **WebPartNodeExtension**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **WebPartNodeExtension** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
6.  Odstraňte soubor kódu Class1 z projektu.  
  
## <a name="configuring-the-extension-project"></a>Konfigurace projektu rozšíření  
 Než napíšete kód k vytvoření rozšíření, musíte přidat soubory kódu a odkazy na sestavení do projektu a je nutné aktualizovat výchozí obor názvů.  
  
#### <a name="to-configure-the-project"></a>Konfigurace projektu  
  
1.  V **WebPartNodeExtension** projekt, přidejte dva soubory kódu, které jsou s názvem SiteNodeExtension a WebPartNodeTypeProvider.  
  
2.  Otevřete místní nabídku pro projekt WebPartNodeExtension a zvolte **přidat odkaz na**.  
  
3.  V **správce odkazů - WebPartNodeExtension** dialogovém okně vyberte **Framework** uzel a potom vyberte zaškrtávací políčka pro System.ComponentModel.Composition a System.Windows.Forms sestavení.  
  
4.  Vyberte **rozšíření** uzlu, zaškrtněte políčko pro každý z následujících sestavení a potom zvolte **OK** tlačítko:  
  
    -   Microsoft.SharePoint.Client  
  
    -   Microsoft.SharePoint.Client.Runtime  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  Otevřete místní nabídku pro **WebPartNodeExtension** projektu a potom vyberte **vlastnosti**.  
  
     **Návrhář projektu** otevře.  
  
6.  Vyberte **aplikace** kartě.  
  
7.  V **výchozí obor názvů** pole (C#) nebo **kořenový obor názvů** pole (Visual Basic), zadejte **ServerExplorer.SharePointConnections.WebPartNode**.  
  
## <a name="creating-icons-for-the-new-nodes"></a>Vytváření ikon pro nové uzly  
 Vytvořte dvě ikony pro **Průzkumníka serveru** rozšíření: ikonu pro nové **Galerie webových částí** uzel a jinou ikonu pro každý uzel podřízené webové části v rámci **Galerie webových částí** uzel. Dále v tomto návodu budete psát kód, který přidruží tyto ikony uzlů.  
  
#### <a name="to-create-icons-for-the-nodes"></a>Vytvoření ikony pro uzly  
  
1.  V **Návrhář projektu** pro projekt WebPartNodeExtension, vyberte **prostředky** kartě.  
  
2.  Vyberte odkaz **tohoto projektu neobsahuje výchozí soubor prostředků. Chcete-li vytvořit, klikněte sem.**  
  
     Visual Studio vytvoří soubor prostředků a otevře ji v návrháři.  
  
3.  V horní části návrháře, vyberte na šipku **přidat prostředek** nabídky příkaz a potom vyberte **přidat novou ikonu**.  
  
4.  Zadejte **WebPartsNode** pro na ikonu nový název a potom vyberte **přidat** tlačítko.  
  
     Nová ikona se otevře v **Editor obrázků**.  
  
5.  Upravte velikosti 16 x 16 verzi ikony tak, aby měl návrh, který lze snadno rozpoznat.  
  
6.  Otevřete místní nabídku pro 32 x 32 verzi ikony a zvolte **odstranit typ obrázku**.  
  
7.  Opakujte kroky 3 až 7 pro přidání druhé ikony do projektu prostředky a pojmenujte tuto ikonu **webové části**.  
  
8.  V **Průzkumníku řešení**v **prostředky** složku **WebPartNodeExtension** projektu, zvolte **WebPartsNode.ico**.  
  
9. V **vlastnosti** okno, otevřete **akce sestavení** seznamu a potom vyberte **vložený prostředek**.  
  
10. Zopakujte poslední dva kroky pro **WebPart.ico**.  
  
## <a name="adding-the-web-part-gallery-node-to-server-explorer"></a>Přidání uzlu Galerie webových částí do Průzkumníka serveru  
 Vytvořte třídu, která přidá novou **Galerie webových částí** uzel pro každý uzel serveru SharePoint. Chcete-li přidat nový uzel, třída implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> rozhraní. Toto rozhraní implementovat vždy, když chcete rozšířit chování existujícího uzlu v **Průzkumníka serveru**, jako je například přidávání nového podřízeného uzlu do uzlu.  
  
#### <a name="to-add-the-web-part-gallery-node-to-server-explorer"></a>Přidání uzlu Galerie webových částí do Průzkumníka serveru  
  
1.  Vložte následující kód do **SiteNodeExtension** souboru kódu **WebPartNodeExtension** projektu.  
  
    > [!NOTE]  
    >  Po přidání tohoto kódu, projekt bude mít několik chyb kompilace. Tyto chyby zmizí při přidání kódu v dalších krocích.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNode#1](../sharepoint/codesnippet/CSharp/webpartnode/webpartnodeextension/sitenodeextension.cs#1)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNode#1](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnode.webpartnode/webpartnodeextension/sitenodeextension.vb#1)]  
  
## <a name="defining-a-node-type-that-represents-a-web-part"></a>Definování typu uzlu, který představuje webové části  
 Vytvořte třídu, která definuje nový typ uzlu, který představuje webové části. Visual Studio použije tento nový typ uzel k zobrazení podřízených uzlů v rámci **Galerie webových částí** uzlu. Každý z těchto podřízených uzlů představuje jednu webovou část na webu služby SharePoint.  
  
 K definování nového typu uzlu, třída implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> rozhraní. Toto rozhraní implementovat, kdykoli budete chtít definovat nový typ uzlu v **Průzkumníka serveru**.  
  
#### <a name="to-define-the-web-part-node-type"></a>K definování typu uzlu webové části  
  
1.  Vložte následující kód do **WebPartNodeTypeProvider** souboru kódu **WebPartNodeExtension** projektu.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNode#2](../sharepoint/codesnippet/CSharp/webpartnode/webpartnodeextension/webpartnodetypeprovider.cs#2)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNode#2](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnode.webpartnode/webpartnodeextension/webpartnodetypeprovider.vb#2)]  
  
## <a name="checkpoint"></a>Kontrolní bod  
 V tomto okamžiku návod, všechny kód **Galerie webových částí** uzel je nyní v projektu. Sestavení **WebPartNodeExtension** projektu se ujistěte, že se zkompiluje bez chyb.  
  
#### <a name="to-build-the-project"></a>Pro sestavení projektu  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **WebPartNodeExtension** projektu a potom vyberte **sestavení**.  
  
## <a name="creating-a-vsix-package-to-deploy-the-extension"></a>Vytvoření balíčku VSIX pro nasazení rozšíření  
 K nasazení rozšíření, použijte k vytvoření balíčku VSIX VSIX projekt ve vašem řešení. Nejprve nakonfigurujte balíčku VSIX úpravou souboru source.extension.vsixmanifest, který je zahrnutý v projektu. Pak vytvořte balíček VSIX sestavení řešení.  
  
#### <a name="to-configure-the-vsix-package"></a>Konfigurace balíčku VSIX  
  
1.  V **Průzkumníku řešení**v **WebPartNode** projekt, otevřete **source.extension.vsixmanifest** souboru v editoru manifestu.  
  
     Soubor source.extension.vsixmanifest je základem pro soubor extension.vsixmanifest, které vyžadují všechny balíčky VSIX. Další informace o tento soubor najdete v tématu [VSIX rozšíření schématu 1.0 odkaz](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  V **název produktu** zadejte **uzel galerie webových částí pro Průzkumníka serveru**.  
  
3.  V **Autor** zadejte **Contoso**.  
  
4.  V **popis** zadejte **přidá vlastní uzel galerie webových částí do uzlu připojení služby SharePoint v Průzkumníku serveru**.  
  
5.  Na **prostředky** karta editoru, vyberte **nový** tlačítko.  
  
6.  V **přidat nový prostředek** dialogu **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `MefComponent` element v souboru extension.vsixmanifest. Tento element určuje název sestavení rozšíření v balíčku VSIX. Další informace najdete v tématu [MEFComponent Element (VSX schéma)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
8.  V **projektu** vyberte **WebPartNodeExtension**a potom zvolte **OK** tlačítko.  
  
9. Na řádku nabídek zvolte **sestavení**, **sestavit řešení**a pak se ujistěte, že řešení zkompiluje bez chyb.  
  
10. Ujistěte se, že výstupní složky sestavení pro projekt WebPartNode nyní obsahuje soubor WebPartNode.vsix.  
  
     Ve výchozím nastavení, je složku výstupu sestavení... \bin\Debug složky pod složkou, která obsahuje soubor projektu.  
  
## <a name="testing-the-extension"></a>Testování rozšíření  
 Nyní jste připraveni k testování nové **Galerie webových částí** uzlu v **Průzkumníka serveru**. Nejprve spusťte ladění rozšíření projektu v experimentální instanci sady Visual Studio. Použít novou **webové části** uzlu v experimentální instanci sady Visual Studio.  
  
#### <a name="to-start-debugging-the-extension"></a>Spustit ladění – rozšíření  
  
1.  Restartujte Visual Studio s přihlašovacími údaji správce a pak otevřete **WebPartNode** řešení.  
  
2.  Otevřete v projektu WebPartNodeExtension **SiteNodeExtension** kód soubor a pak přidejte zarážku první řádky kódu v `NodeChildrenRequested` a `CreateWebPartNodes` metody.  
  
3.  Zvolte klávesy F5 spusťte ladění.  
  
     Visual Studio nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Web uzel rozšíření Galerie částí pro Server Explorer\1. 0 a spustí experimentální instanci sady Visual Studio. Položka projektu budete testovat v této instanci sady Visual Studio.  
  
#### <a name="to-test-the-extension"></a>K testování rozšíření  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **zobrazení**, **Průzkumníka serveru**.  
  
2.  Ověřte, zda web služby SharePoint, kterou chcete použít pro testování zobrazí v části **připojení služby SharePoint** uzlu v **Průzkumníka serveru**. Pokud není v seznamu uvedena, postupujte takto:  
  
    1.  Otevřete místní nabídku pro **připojení služby SharePoint**a potom zvolte **přidat připojení**.  
  
    2.  V **přidat připojení služby SharePoint** dialogové okno pole, zadejte adresu URL pro web služby SharePoint, ke kterému chcete připojit a potom vyberte **OK** tlačítko.  
  
         Chcete-li zadat web služby SharePoint ve svém vývojovém počítači, zadejte **http://localhost**.  
  
3.  Rozbalte uzel připojení webu (která zobrazuje adresu URL vašeho webu) a potom rozbalte podřízený uzel serveru (například **týmový web**).  
  
4.  Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou jste nastavili výše v `NodeChildrenRequested` metoda a potom vyberte klávesy F5 pokračujte ladění projektu.  
  
5.  V experimentální instanci sady Visual Studio, rozbalte **Galerie webových částí** uzlu, který se zobrazí v uzlu lokalita nejvyšší úrovně.  
  
6.  Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou jste nastavili výše v `CreateWebPartNodes` metoda a potom vyberte klávesy F5 pokračujte ladění projektu.  
  
7.  V experimentální instanci sady Visual Studio, ověřte, že všechny webové části na připojená lokalita zobrazují v části **Galerie webových částí** uzlu v **Průzkumníka serveru**.  
  
8.  Otevřete místní nabídku pro webovou část a potom zvolte **vlastnosti**.  
  
9. V **vlastnosti** okno, ověřte, že se zobrazují podrobnosti o webové části.  
  
10. V **Průzkumníka serveru**, otevřete místní nabídku pro stejné webové části a pak zvolte **zobrazená zpráva**.  
  
     V dialogovém okně se zobrazí, vyberte **OK** tlačítko.  
  
## <a name="uninstalling-the-extension-from-visual-studio"></a>Odinstalovat rozšíření ze sady Visual Studio  
 Po dokončení testování rozšíření, odinstalujte ji ze sady Visual Studio.  
  
#### <a name="to-uninstall-the-extension"></a>Chcete-li odinstalovat rozšíření  
  
1.  V experimentální instanci sady Visual Studio na řádku nabídek zvolte **nástroje**, **rozšíření a aktualizace**.  
  
     **Rozšíření a aktualizace** otevře se dialogové okno.  
  
2.  V seznamu rozšíření, vyberte **uzel galerie webových částí pro Průzkumníka serveru**a potom zvolte **odinstalovat** tlačítko.  
  
3.  V dialogovém okně, které se zobrazí, vyberte **Ano** tlačítko.  
  
4.  Vyberte **restartovat nyní** tlačítko k dokončení odinstalace.  
  
     Položka projektu je také odinstalovat.  
  
5.  Zavřete obě instance sady Visual Studio (experimentální instance a instance sady Visual Studio, ve kterém je otevřen řešení WebPartNode).  
  
## <a name="see-also"></a>Viz také  
 [Volání do služby SharePoint objektové modely](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Návod: Rozšíření Průzkumníka serveru pro zobrazení webové části](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [Editor obrázků pro ikony](/cpp/windows/image-editor-for-icons)   
 [Vytvoření ikony nebo jiného obrázku &#40;Editor obrázků pro ikony&#41;](/cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  