---
title: 'Návod: Rozšíření Průzkumníka serveru pro zobrazení webové části | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint commands
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b0bbea76c3c63cf562203f9a622acb2a54804bde
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117833"
---
# <a name="walkthrough-extend-server-explorer-to-display-web-parts"></a>Návod: Rozšíření Průzkumníka serveru pro zobrazení webové části
  V sadě Visual Studio, můžete použít **připojení služby SharePoint** uzlu **Průzkumníka serveru** zobrazíte součásti na webech služby SharePoint. Ale **Průzkumníka serveru** nezobrazí některé součásti ve výchozím nastavení. V tomto návodu budete rozšíříte **Průzkumníka serveru** tak, aby zobrazil galerii webových částí na každý z nich připojený web služby SharePoint.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytváření rozšíření pro Visual Studio, který rozšiřuje **Průzkumníka serveru** následujícími způsoby:  
  
    -   Přidá rozšíření **Galerie webových částí** uzel za každý uzel serveru SharePoint v **Průzkumníka serveru**. Tento nový uzel obsahuje podřízené uzly, které představují jednotlivé webové části v galerii webových částí na webu.  
  
    -   Rozšíření definuje nový typ uzlu, který představuje instanci webové části. Tento nový typ uzlu je základem pro podřízené uzly v rámci nové **Galerie webových částí** uzlu. Zobrazí informace v nového typu uzlu webové části **vlastnosti** okno webová část, která reprezentuje. Typ uzlu také zahrnuje vlastní položku nabídky, můžete použít jako východisko pro provedení dalších úloh, které se týkají webové části.  
  
-   Vytvořte dva vlastní příkazy služby SharePoint, které volá sestavení rozšíření. SharePoint – příkazy jsou metody, které je možné volat v sestavení rozšíření pro použití rozhraní API v objektovém modelu serveru pro službu SharePoint. V tomto návodu vytvoříte příkazy, které načíst informace o webové části z místního webu služby SharePoint na vývojovém počítači. Další informace najdete v tématu [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
-   Vytváření rozšíření pro Visual Studio (VSIX) balíčku pro nasazení rozšíření.  
  
-   Ladění a testování rozšíření.  
  
> [!NOTE]  
>  Alternativní verze tohoto průvodce, který používá objektového modelu klienta pro službu SharePoint místo jeho objektový model serveru, najdete v části [návod: volání do modelu klientského objektu služby SharePoint v rozšíření Průzkumníka serveru](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md).  
  
## <a name="prerequisites"></a>Požadavky  
 Následující součásti na vývojovém počítači k dokončení tohoto názorného postupu potřebujete:  
  
-   Podporované edice systému Windows, SharePoint a Visual Studio. Další informace najdete v tématu [požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK. Tento návod používá **projektu VSIX** šablony v sadě SDK k vytvoření balíčku VSIX pro nasazení položka projektu. Další informace najdete v tématu [rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Znalost následující koncepty je užitečné, ale není nutné k dokončení průvodce:  
  
-   Pomocí objektový model serveru pro službu SharePoint. Další informace najdete v tématu [pomocí objektového modelu služby SharePoint Foundation na straně serveru](http://go.microsoft.com/fwlink/?LinkId=177796).  
  
-   Webové části v řešení služby SharePoint. Další informace najdete v tématu [přehled webových částí](http://go.microsoft.com/fwlink/?LinkId=177803).  
  
## <a name="create-the-projects"></a>Vytváření projektů
 Pro dokončení tohoto návodu, musíte vytvořit tří projektů:  
  
-   Projekt VSIX k vytvoření balíčku VSIX pro nasazení rozšíření.  
  
-   Projekt knihovny tříd, který implementuje rozšíření. Tento projekt musí mít jako cíl rozhraní .NET Framework 4.5.  
  
-   Projekt knihovny tříd, která definuje vlastní příkazy služby SharePoint. Tento projekt musí mít jako cíl rozhraní.NET Framework 3.5.  
  
 Spusťte Průvodce vytvořením projektů.  
  
#### <a name="to-create-the-vsix-project"></a>Vytvoření projektu VSIX  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na řádku nabídek zvolte **soubor** > **nový** > **projektu**.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** uzly a potom zvolte **rozšiřitelnost** uzlu.  
  
    > [!NOTE]  
    >  **Rozšiřitelnost** uzel je k dispozici pouze v případě, že nainstalujete Visual Studio SDK. Další informace najdete v části požadavky dříve v tomto tématu.  
  
4.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 4.5** v seznamu verze rozhraní .NET Framework.  
  
5.  Vyberte **projektu VSIX** šablony, název projektu **WebPartNode**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **WebPartNode** projektu do **Průzkumníku řešení**.  
  
#### <a name="to-create-the-extension-project"></a>Vytvoření projektu rozšíření  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** uzlu nebo **jazyka Visual Basic** uzel a potom zvolte **Windows** uzlu.  
  
3.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 4.5** v seznamu verze rozhraní .NET Framework.  
  
4.  V seznamu šablon projektu, zvolte **knihovny tříd**, název projektu **WebPartNodeExtension**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **WebPartNodeExtension** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
5.  Odstraňte soubor kódu Class1 z projektu.  
  
#### <a name="to-create-the-sharepoint-commands-project"></a>Chcete-li vytvořit příkazy projektu služby SharePoint  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení, zvolte **přidat**a potom zvolte **nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** uzlu nebo **jazyka Visual Basic** uzel a potom zvolte **Windows** uzlu.  
  
3.  V horní části dialogových oken, zvolte **rozhraní .NET Framework 3.5** v seznamu verze rozhraní .NET Framework.  
  
4.  V seznamu šablon projektu, zvolte **knihovny tříd**, název projektu **WebPartCommands**a potom zvolte **OK** tlačítko.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **WebPartCommands** projektu a řešení a otevře soubor výchozího kódu Class1.  
  
5.  Odstraňte soubor kódu Class1 z projektu.  
  
## <a name="configure-the-projects"></a>Konfigurace projektů
 Než napíšete kód k vytvoření rozšíření, musíte přidat soubory kódu a odkazy na sestavení a nakonfigurovat nastavení projektu.  
  
#### <a name="to-configure-the-webpartnodeextension-project"></a>Ke konfiguraci projektu WebPartNodeExtension
  
1.  V projektu WebPartNodeExtension přidejte čtyři soubory kódu, které mají tyto názvy:  
  
    -   SiteNodeExtension  
  
    -   WebPartNodeTypeProvider  
  
    -   WebPartNodeInfo  
  
    -   WebPartCommandIds  
  
2.  Otevřete místní nabídku pro **WebPartNodeExtension** projektu a potom vyberte **přidat odkaz na**.  
  
3.  V **správce odkazů - WebPartNodeExtension** dialogovém okně vyberte **Framework** kartě a potom zaškrtněte políčko pro každý z následujících sestavení:  
  
    -   System.ComponentModel.Composition  
  
    -   System.Windows.Forms  
  
4.  Vyberte **rozšíření** kartě, zaškrtněte políčko pro sestavení Microsoft.VisualStudio.SharePoint a potom zvolte **OK** tlačítko.  
  
5.  V **Průzkumníku řešení**, otevřete místní nabídku pro **WebPartNodeExtension** uzel projektu a potom zvolte **vlastnosti**.  
  
     **Návrhář projektu** otevře.  
  
6.  Vyberte **aplikace** kartě.  
  
7.  V **výchozí obor názvů** pole (C#) nebo **kořenový obor názvů** pole ([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]), zadejte **ServerExplorer.SharePointConnections.WebPartNode**.  
  
#### <a name="to-configure-the-webpartcommands-project"></a>Ke konfiguraci projektu webpartcommands
  
1.  V projektu WebPartCommands přidejte kód souboru, který je pojmenován WebPartCommands.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro **WebPartCommands** uzel projektu, zvolte **přidat**a potom zvolte **existující položka**.  
  
3.  V **přidat existující položku** dialogové okno, přejděte do složky, která obsahuje soubory kódu pro projekt WebPartNodeExtension a potom vyberte soubory WebPartNodeInfo a WebPartCommandIds kódu.  
  
4.  Vyberte šipku vedle položky **přidat** tlačítko a potom vyberte **přidat jako odkaz** v nabídce, která se zobrazí.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá soubory kódu do projektu WebPartCommands jako odkazy. V důsledku toho se kód soubory nacházejí v projektu WebPartNodeExtension, ale také kompilované kódu v souborech v projektu WebPartCommands.  
  
5.  Otevřete místní nabídku pro **WebPartCommands** projekt znovu a vyberte **přidat odkaz na**.  
  
6.  V **správce odkazů - WebPartCommands** dialogovém okně vyberte **rozšíření** kartě, zaškrtněte políčko pro každý z následujících sestavení a potom zvolte **OK** tlačítko:  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
7.  V **Průzkumníku řešení**, otevřete místní nabídku pro **WebPartCommands** projekt znovu a potom vyberte **vlastnosti**.  
  
     **Návrhář projektu** otevře.  
  
8.  Vyberte **aplikace** kartě.  
  
9. V **výchozí obor názvů** pole (C#) nebo **kořenový obor názvů** pole ([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]), zadejte **ServerExplorer.SharePointConnections.WebPartNode**.  
  
## <a name="create-icons-for-the-new-nodes"></a>Vytvoření ikony pro nové uzly
 Vytvořte dvě ikony pro **Průzkumníka serveru** rozšíření: ikonu pro nové **Galerie webových částí** uzel a jinou ikonu pro každý uzel podřízené webové části v rámci **Galerie webových částí** uzel. Dále v tomto návodu budete psát kód, který přidruží tyto ikony uzlů.  
  
#### <a name="to-create-icons-for-the-nodes"></a>Vytvoření ikony pro uzly  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **WebPartNodeExtension** projektu a potom vyberte **vlastnosti**.  
  
2.  **Návrhář projektu** otevře.  
  
3.  Vyberte **prostředky** a pak klikněte na příkaz **tohoto projektu neobsahuje výchozí soubor prostředků. Kliknutím sem vytvoříte jeden** odkaz.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Vytvoří soubor prostředků a otevře ji v návrháři.  
  
4.  V horní části návrháře, vyberte na šipku vedle položky **přidat prostředek** nabídky příkaz a potom vyberte **přidat novou ikonu** v nabídce, která se zobrazí.  
  
5.  V **přidat nový prostředek** dialogové okno, název na ikonu Nový **WebPartsNode**a potom zvolte **přidat** tlačítko.  
  
     Nová ikona se otevře v **Editor obrázků**.  
  
6.  Upravte velikosti 16 x 16 verzi ikony tak, aby měl návrh, který lze snadno rozpoznat.  
  
7.  Otevřete místní nabídku pro 32 x 32 verzi ikony a zvolte **odstranit typ obrázku**.  
  
8.  Opakujte kroky 5 až 8 pro přidání druhé ikony do projektu prostředky a pojmenujte tuto ikonu **webové části**.  
  
9. V **Průzkumníku řešení**v části **prostředky** složku **WebPartNodeExtension** projektu, otevřete místní nabídku pro **WebPartsNode.ico**.  
  
10. V **vlastnosti** okně vyberte šipku vedle **akce sestavení**a potom zvolte **vložený prostředek** v zobrazené nabídce.  
  
11. Zopakujte poslední dva kroky pro **WebPart.ico**.  
  
## <a name="add-the-web-part-gallery-node-to-server-explorer"></a>Přidání uzlu Galerie webových částí do Průzkumníka serveru
 Vytvořte třídu, která přidá novou **Galerie webových částí** uzel pro každý uzel serveru SharePoint. Chcete-li přidat nový uzel, třída implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> rozhraní. Toto rozhraní implementovat vždy, když chcete rozšířit chování existujícího uzlu v **Průzkumníka serveru**, jako je například přidávání podřízený uzel do uzlu.  
  
#### <a name="to-add-the-web-part-gallery-node-to-server-explorer"></a>Přidání uzlu Galerie webových částí do Průzkumníka serveru
  
1.  V projektu WebPartNodeExtension otevřete soubor kódu SiteNodeExtension a potom vložte následující kód do ní.  
  
    > [!NOTE]  
    >  Po přidání tohoto kódu, projekt bude mít některé chyby při kompilaci, ale budete ji okamžitě přejděte po přidání kódu v dalších krocích.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#1](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/sitenodeextension.cs#1)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#1](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/sitenodeextension.vb#1)]  
  
## <a name="define-a-node-type-that-represents-a-web-part"></a>Zadejte typ uzlu, který reprezentuje webové části
 Vytvořte třídu, která definuje nový typ uzlu, který představuje webové části. Visual Studio použije tento nový typ uzel k zobrazení podřízených uzlů v rámci **Galerie webových částí** uzlu. Každý podřízený uzel představuje jednu webovou část na webu služby SharePoint.  
  
 K definování nového typu uzlu, třída implementuje <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> rozhraní. Toto rozhraní implementovat, kdykoli budete chtít definovat nový typ uzlu v **Průzkumníka serveru**.  
  
#### <a name="to-define-the-web-part-node-type"></a>Chcete-li definovat typ uzlu webové části
  
1.  V projektu WebPartNodeExtension otevřete soubor WebPartNodeTypeProvder kód a potom vložte následující kód do ní.  
  
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#2](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartnodetypeprovider.vb#2)]
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#2](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartnodetypeprovider.cs#2)]  
  
## <a name="define-the-web-part-data-class"></a>Zadejte webovou část datové třídy
 Definice třídy, která obsahuje data o jednu webovou část na webu služby SharePoint. Dále v tomto návodu vytvoříte vlastního příkazu SharePoint, která získává data o jednotlivé webové části na webu a potom přiřadí data instance této třídy.  
  
#### <a name="to-define-the-web-part-data-class"></a>Chcete-li definovat třídu webovou část dat
  
1.  V projektu WebPartNodeExtension otevřete soubor WebPartNodeInfo kód a potom vložte následující kód do ní.  
  
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#3](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartnodeinfo.vb#3)]
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#3](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartnodeinfo.cs#3)]  
  
## <a name="define-the-ids-for-the-sharepoint-commands"></a>Zadejte ID pro příkazy služby SharePoint
 Definujte několik řetězců, které identifikují vlastní příkazy služby SharePoint. Dále v tomto návodu budete implementovat tyto příkazy.  
  
#### <a name="to-define-the-command-ids"></a>Chcete-li definovat identifikátory příkazů
  
1.  V projektu WebPartNodeExtension otevřete soubor WebPartCommandIds kód a potom vložte následující kód do ní.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#4](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartcommandids.cs#4)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#4](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartcommandids.vb#4)]  
  
## <a name="create-the-custom-sharepoint-commands"></a>Vytvoření vlastních příkazů služby SharePoint
 Vytvořte vlastní příkazy, které volají do objektový model serveru pro službu SharePoint k načtení dat o webové části na webu služby SharePoint. Každý příkaz je metoda, která má <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute> použije na ni.  
  
#### <a name="to-define-the-sharepoint-commands"></a>Chcete-li definovat příkazy služby SharePoint  
  
1.  V projektu WebPartCommands otevřete soubor WebPartCommands kód a potom vložte následující kód do ní.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#6](../sharepoint/codesnippet/CSharp/WebPartNode/WebPartCommands/WebPartCommands.cs#6)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#6](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartcommands/webpartcommands.vb#6)]  
  
## <a name="checkpoint"></a>Kontrolní bod  
 V tomto okamžiku návod, všechny kód **Galerie webových částí** uzlu a příkazy služby SharePoint jsou nyní v projektech. Sestavte řešení, abyste měli jistotu, že oba projekty kompilovat bez chyb.  
  
#### <a name="to-build-the-solution"></a>K sestavení řešení  
  
1.  Na řádku nabídek zvolte **sestavení** > **sestavit řešení**.  
  
    > [!WARNING]  
    >  V tomto okamžiku projektu WebPartNode může mít chyby sestavení, protože soubor manifestu VSIX nemá žádnou hodnotu pro vytváření. Tato chyba zmizí při přidání hodnotu v dalších krocích.  
  
## <a name="create-a-vsix-package-to-deploy-the-extension"></a>Vytvoření balíčku VSIX pro nasazení rozšíření
 K nasazení rozšíření, použijte k vytvoření balíčku VSIX VSIX projekt ve vašem řešení. Nejprve nakonfigurujte balíčku VSIX úpravou souboru source.extension.vsixmanifest v projektu VSIX. Pak vytvořte balíčku VSIX vytvořením řešení.  
  
#### <a name="to-configure-the-vsix-package"></a>Konfigurace balíčku VSIX  
  
1.  V **Průzkumníku řešení**, otevřete v projektu WebPartNode **source.extension.vsixmanifest** souboru v editoru manifestu.  
  
     Soubor source.extension.vsixmanifest je základem pro soubor extension.vsixmanifest, které vyžadují všechny balíčky VSIX. Další informace o tento soubor najdete v tématu [VSIX rozšíření schématu 1.0 odkaz](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  V **název produktu** zadejte **uzel galerie webových částí pro Průzkumníka serveru**.  
  
3.  V **Autor** zadejte **Contoso**.  
  
4.  V **popis** zadejte **přidá vlastní uzel galerie webových částí do uzlu připojení služby SharePoint v Průzkumníku serveru. Toto rozšíření používá vlastní příkazu SharePoint provést volání do objektový model serveru.**  
  
5.  Vyberte **prostředky** karta editoru a potom zvolte **nový** tlačítko.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
6.  V **typ** vyberte **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Tato hodnota odpovídá `MefComponent` element v souboru extension.vsixmanifest. Tento element určuje název sestavení rozšíření v balíčku VSIX. Další informace najdete v tématu [MEFComponent Element (VSX schéma)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  V **zdroj** vyberte **na projekt v aktuálním řešení**.  
  
8.  V **projektu** vyberte **WebPartNodeExtension** a potom zvolte **OK** tlačítko.  
  
9. V editoru manifestu zvolte **nový** tlačítko znovu.  
  
     **Přidat nový prostředek** zobrazí se dialogové okno.  
  
10. V **typ** zadejte **SharePoint.Commands.v4**.  
  
    > [!NOTE]  
    >  Tento element určuje vlastní rozšíření, které chcete zahrnout do rozšíření sady Visual Studio. Další informace najdete v tématu [Element Asset (VSX schéma)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737).  
  
11. V **zdroj** seznam, vyberte **na projekt v aktuálním řešení** položky seznamu.  
  
12. V **projektu** vyberte **WebPartCommands**a potom zvolte **OK** tlačítko.  
  
13. Na řádku nabídek zvolte **sestavení** > **sestavit řešení**a pak se ujistěte, že řešení zkompiluje bez chyb.  
  
14. Ujistěte se, že výstupní složky sestavení pro projekt WebPartNode nyní obsahuje soubor WebPartNode.vsix.  
  
     Ve výchozím nastavení, je složku výstupu sestavení... \bin\Debug složky pod složkou, která obsahuje soubor projektu.  
  
## <a name="test-the-extension"></a>Testování rozšíření
 Nyní jste připraveni otestovat nový **Galerie webových částí** uzlu v **Průzkumníka serveru**. Nejprve spusťte ladění rozšíření v experimentální instanci sady Visual Studio. Potom pomocí nové **webové části** uzlu experimentální instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
#### <a name="to-start-debugging-the-extension"></a>Spustit ladění – rozšíření  
  
1.  Restartujte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] s přihlašovacími údaji správce a pak otevřete řešení WebPartNode.  
  
2.  V projektu WebPartNodeExtension, otevřete soubor kódu SiteNodeExtension a pak přidejte zarážku na první řádek kódu `NodeChildrenRequested` a `CreateWebPartNodes` metody.  
  
3.  Vyberte **F5** klíč spustit ladění.  
  
     Visual Studio nainstaluje rozšíření do %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Web uzel rozšíření Galerie částí pro Server Explorer\1. 0 a spustí experimentální instanci sady Visual Studio. Položka projektu budete testovat v této instanci sady Visual Studio.  
  
#### <a name="to-test-the-extension"></a>K testování rozšíření  
  
1.  V experimentální instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], na řádku nabídek zvolte **zobrazení** > **Průzkumníka serveru**.  
  
2.  Pokud web služby SharePoint, kterou chcete použít pro testování se nezobrazí v části provést následující kroky **připojení služby SharePoint** uzlu v **Průzkumníka serveru**:  
  
    1.  V **Průzkumníka serveru**, otevřete místní nabídku pro **připojení služby SharePoint**a potom zvolte **přidat připojení**.  
  
    2.  V **přidat připojení služby SharePoint** dialogové okno pole, zadejte adresu URL pro web služby SharePoint, ke kterému chcete připojit a potom vyberte **OK** tlačítko.  
  
         Web služby SharePoint ve svém vývojovém počítači, zadejte **http://localhost**.  
  
3.  Rozbalte uzel připojení webu (která zobrazuje adresu URL vašeho webu) a potom rozbalte podřízený uzel serveru (například **týmový web**).  
  
4.  Ověřte, zda kód do jiné instance systému [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zastaví na zarážce, kterou jste nastavili výše v `NodeChildrenRequested` metoda a potom zvolte **F5** pokračujte ladění projektu.  
  
5.  V experimentální instanci sady Visual Studio, ověřte, že nový uzel s názvem **Galerie webových částí** se zobrazí v uzlu lokalita nejvyšší úrovně a potom rozbalte **Galerie webových částí** uzlu.  
  
6.  Ověřte, že kód ve druhé instanci sady Visual Studio zastaví na zarážce, kterou jste nastavili výše v `CreateWebPartNodes` metoda a potom zvolte **F5** klíče a pokračujte ladění projektu.  
  
7.  V experimentální instanci sady Visual Studio, ověřte, že všechny webové části na připojená lokalita zobrazují v části **Galerie webových částí** uzlu v **Průzkumníka serveru**.  
  
8.  V **Průzkumníka serveru**, otevřete místní nabídku pro jednu z webové části a pak zvolte **vlastnosti**.  
  
9. V instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] , kterou ladíte, ověřte, že v zobrazují podrobnosti o webové části **vlastnosti** okno.  
  
## <a name="uninstall-the-extension-from-visual-studio"></a>Odinstalovat rozšíření ze sady Visual Studio
 Po dokončení testování rozšíření, odinstalujte rozšíření ze sady Visual Studio.  
  
#### <a name="to-uninstall-the-extension"></a>Chcete-li odinstalovat rozšíření  
  
1.  V experimentální instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], na řádku nabídek zvolte **nástroje** > **rozšíření a aktualizace**.  
  
     **Rozšíření a aktualizace** otevře se dialogové okno.  
  
2.  V seznamu rozšíření, vyberte **uzel rozšíření Galerie webových částí pro Průzkumníka serveru**a potom zvolte **odinstalovat** tlačítko.  
  
3.  V dialogovém okně, které se zobrazí, vyberte **Ano** tlačítko potvrďte, že chcete odinstalovat rozšíření a potom vyberte **restartovat nyní** tlačítko k dokončení odinstalace.  
  
4.  Zavřete obě instance sady Visual Studio (experimentální instance a instance sady Visual Studio, ve kterém je otevřen řešení WebPartNode).  
  
## <a name="see-also"></a>Viz také:
 [Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Návod: Volání do modelu klientského objektu služby SharePoint v rozšíření Průzkumníka serveru](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)   
 [Editor obrázků pro ikony](/cpp/windows/image-editor-for-icons)   
 [Vytvoření ikony nebo jiného obrázku &#40;Editor obrázků pro ikony&#41;](/cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
