---
title: 'Návod: Import opakovaně použitelného pracovního postupu návrháře služby SharePoint do sady Visual Studio | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.WSPImport.ImportWF
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing reusable workflows
- reusable workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2269beef06f7ca43556c2c00493ac8d7cb1c4ad5
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120203"
---
# <a name="walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio"></a>Návod: Importujte opakovaně použitelného pracovního postupu návrháře služby SharePoint do sady Visual Studio
  Tento návod ukazuje, jak importovat znovu použitelné pracovní postup vytvořený v SharePoint Designer 2010 do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu pracovního postupu služby SharePoint.  
  
 Pracovní postupy vytvořené v aplikaci SharePoint Designer nebo *deklarativní pracovních*, obsahovat [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] příkazy místo kódu. Zavádí SharePoint Designer 2010 *znovu použitelné pracovní postupy*, které jsou přenosné, deklarativní pracovní postupy, které můžete používat různé seznamy na webech služby SharePoint.  
  
 Pracovní postupy vytvořené v [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)], jako je například počítač sekvenční a stavu pracovních postupů, se nazývají *code pracovních*. Pracovní postupy kódu obsahovat soubory XML a kódové moduly, které mohou uživatelé přizpůsobit chování pracovního postupu.  
  
 Visual Studio můžete importovat znovu použitelné pracovní postupy vytvořené v Návrháři SharePoint 2010 a je převést na kód pracovní postupy pro použití v webů služby SharePoint.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytvoření pracovního postupu jednoduchý, opakovaně použitelný v návrháře služby SharePoint.  
  
-   Export opakovaně použitelného pracovního postupu návrháře služby SharePoint k *WSP* souboru a do služby SharePoint.  
  
-   Import *WSP* soubor do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] pomocí projektu Import opakovaně použitelného pracovního postupu.  
  
-   Změna pracovního postupu tak, že přidáte kód.  
  
-   Pomocí importovaných pracovního postupu na webu služby SharePoint.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] a služby SharePoint. Další informace najdete v tématu [požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
-   Microsoft [!INCLUDE[TLA2#tla_office](../sharepoint/includes/tla2sharptla-office-md.md)] SharePoint Designer 2010.  
  
## <a name="create-target-sharepoint-subsites"></a>Vytváření podřízených webů služby SharePoint cíl
 Nejprve vytvořte dva nové podřízené weby služby SharePoint: jeden pro hostování znovu použitelné pracovní postupy z Návrháře služby SharePoint, jiné k hostování převedený pracovních postupů.  
  
#### <a name="to-create-sharepoint-subsites"></a>Vytvoření podřízených webů služby SharePoint  
  
1.  V SharePoint Designer 2010 na řádku nabídek zvolte **soubor** > **nový prázdný web**.  
  
2.  V **nový prázdný web** dialogové okno, přejděte na web služby SharePoint, kde chcete vytvořit pracovní postup, nebo použijte hodnotu http://*SystemName*/ a potom zvolte **OK** tlačítko.  
  
     Zobrazí se na domovskou stránku.  
  
3.  V **podřízené lokality** zvolte **nový** tlačítko.  
  
4.  V **nový** dialogovém okně vyberte **šablony služby SharePoint** ze seznamu v levém podokně a zvolte **týmový web** ze seznamu v pravém podokně.  
  
5.  V **zadejte umístění na webu** pole, nahraďte slovo **podřízeného webu** v adrese URL s **SPD1**a potom zvolte **OK** tlačítko.  
  
     Otevře se nové podřízené lokality do seznamu služby SharePoint. Zavřete tuto instanci služby SharePoint Designer a přejděte zpět na první instance (lokalitě nejvyšší úrovně).  
  
6.  Opakujte kroky 3 až 5 vytvořte druhý podřízený web, tentokrát nahrazení slovo **podřízeného webu** v [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] s **SPD2**.  
  
## <a name="create-a-sharepoint-designer-reusable-workflow"></a>Vytvořit opakovaně použitelného pracovního postupu návrháře služby SharePoint
 Protože SharePoint nezahrnuje znovu použitelné pracovní postupy, které můžete použít v tomto příkladu, vytvoříte jeden. V tomto jednoduché pracovním postupu když uživatel zadá novou úlohu v seznamu úloh, která má konkrétní softwarový produkt, úloha je přiřazená tomuto uživateli.  
  
#### <a name="to-create-a-sharepoint-designer-reusable-workflow"></a>Vytvoření opakovaně použitelného pracovního postupu aplikace SharePoint Designer
  
1.  V **podřízené lokality** zvolte **SPD1** lokality jej upravit.  
  
2.  Na pásu karet, vyberte **opakovaně použitelného pracovního postupu** tlačítko.  
  
     Zobrazí se Průvodce vytvořením opakovaně použitelného pracovního postupu.  
  
3.  V **název** zadejte **postupu úlohy SPD**.  
  
4.  V **typ obsahu** vyberte **úloh**a potom zvolte **OK** tlačítko.  
  
     Pracovní postup se otevře v Návrháři pracovních postupů služby SharePoint Designer.  
  
5.  V Návrháři pracovních postupů, zvolte krok 1 a pak na pásu karet **podmínku** tlačítko.  
  
6.  V seznamu podmínek, vyberte **Pokud se hodnota rovná aktuální položky pole**.  
  
     Tento krok přidává podmínku, která je s názvem **Pokud pole rovná hodnotě**.  
  
7.  V **Pokud pole rovná hodnotě** podmínek, vyberte **pole** odkaz.  
  
8.  V seznamu hodnot, zvolte **název**.  
  
9. V **Pokud pole rovná hodnotě** podmínek, vyberte **hodnotu** odkaz.  
  
10. V dialogovém okně zadejte **nová úloha**.  
  
     Načte příkaz podmínky **Pokud aktuální položka: název rovná nová úloha**.  
  
11. Zvolte řádku pod příkaz podmínky a pak na pásu karet **akce** tlačítko.  
  
12. V seznamu akcí, vyberte **sadu pole v aktuální položky**.  
  
13. V **pole nastavit na hodnotu** akce, vyberte **pole** propojit a potom v seznamu zvolte **přiřazené**.  
  
14. V **pole nastavit na hodnotu** akce, vyberte **hodnotu** propojit a potom v seznamu existující uživatelů a skupin, zvolte **uživatele, který vytvořil položku**.  
  
15. Vyberte **přidat** tlačítko a potom vyberte **OK** tlačítko.  
  
     Načte příkaz akce **nastavit přiřazeno uživateli pro aktuální položku: vytvořená**.  
  
## <a name="save-and-deploy-the-reusable-workflow"></a>Uložte a nasaďte opakovaně použitelného pracovního postupu
 Protože [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] můžete importovat pouze *WSP* soubory, je nutné uložit opakovaně použitelného pracovního postupu jako *WSP* a nasadíte ho do služby SharePoint před importem do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
> [!IMPORTANT]  
>  Pokud se zobrazí chyba v běhu provedením tohoto postupu, budete muset proveďte postup v systému, který má přístup k webu služby SharePoint.  
  
#### <a name="to-save-and-deploy-the-reusable-workflow"></a>Uložení a nasazení opakovaně použitelného pracovního postupu  
  
1.  V horní části seznamu služby SharePoint, vyberte **Uložit** tlačítko pro rozdělanou práci uložit a potom vyberte **publikovat** tlačítko nasazení pracovního postupu **SPD1** web služby SharePoint .  
  
2.  V navigačním podokně, vyberte **pracovních** objektu.  
  
3.  V části **opakovaně použitelného pracovního postupu**, zvolte **postupu úlohy SPD**.  
  
4.  Na pásu karet, vyberte **uložit jako šablonu** tlačítko pro uložení postupu jako *WSP* souboru.  
  
5.  Otevřete **SPD1** web služby SharePoint v prohlížeči zobrazit *WSP* souboru ve službě SharePoint.  
  
6.  Na panel Rychlé spuštění, zvolte **knihovny** odkaz.  
  
7.  V **knihovny dokumentů** zvolte **prostředky lokality** odkaz.  
  
     **Postupu úlohy SPD** souboru je uveden s prostředky jiné lokality.  
  
8.  V seznamu souborů zvolte název tohoto souboru  
  
9. V **stažení souboru** dialogovém okně vyberte **Uložit** tlačítko Uložit *WSP* souboru v místním systému.  
  
## <a name="import-the-wsp-file-into-visual-studio"></a>Import souborů WSP do sady Visual Studio
 Import *WSP* soubor do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] pomocí projektu Import opakovaně použitelného pracovního postupu. Tento projekt převede do pracovního postupu kód pracovního postupu z opakovaně použitelný deklarativní pracovní postup. Po převodu pracovního postupu použijete kód změnit její chování.  
  
#### <a name="to-import-a-workflow-from-a-wsp-file-and-modify-it"></a>Import pracovního postupu ze souboru WSP a jeho úpravy  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], na řádku nabídek zvolte **soubor** > **nový** > **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom vyberte **2010** uzlu.  
  
3.  V **šablony** podokně, vyberte **pracovního postupu Import opakovaně použitelného služby SharePoint 2010** šablony, ponechejte pole název projektu jako **WorkflowImportProject1**a potom vyberte **OK** tlačítko.  
  
     Zobrazí se Průvodce nastavením služby SharePoint.  
  
4.  Na **zadejte úroveň lokality a zabezpečení pro ladění** stránky, zadejte [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] pro druhý podřízeného webu služby SharePoint, kterou jste vytvořili dříve: http://*systémový název*/SPD2.  
  
5.  V **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint?** zvolte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Další** tlačítko.  
  
     Další informace o v izolovaném prostoru a řešení ve farmách, najdete v části [aspekty řešení v izolovaném prostoru](../sharepoint/sandboxed-solution-considerations.md).  
  
6.  V **zadejte nový zdroj projektu** stránky, přejděte do umístění na serveru, kam jste dříve uložili *WSP* souboru, otevřete soubor a potom zvolte **Další** tlačítko.  
  
    > [!NOTE]  
    >  Vyberte **Dokončit** tlačítko naimportovány všechny položky k dispozici v *WSP* souboru.  
  
     Zobrazí se seznam dostupných pro import znovu použitelné pracovní postupy.  
  
7.  V **vybrat položky k importu** , vyberte **postupu úlohy SPD** pracovního postupu a potom vyberte **Dokončit** tlačítko.  
  
     Po dokončení operace importu projektu s názvem **WorkflowImportProject1** je vytvořen obsahující pracovního postupu s názvem **SPD_Workflow_TestFT**. V této složce je soubor definice pracovního postupu *Elements.xml* a soubor návrháře pracovního postupu (*XOML*). Návrhář obsahuje dva soubory: soubor pravidla (.rules) a soubor kódu (buď *.cs* nebo *VB*, v závislosti na programovací jazyk vašeho projektu).  
  
8.  V **Průzkumníku řešení**, odstraňte **ostatní soubory importovat** složky.  
  
9. V *Elements.xml* souboru, odstraňte `InstantiationURL="_layouts/IniErkflIP.sspx"`.  
  
10. V **Průzkumníku řešení**, zvolte **WorkflowImportProject1**a potom na řádku nabídek zvolte **projektu** > **nastavit jako spouštěný projekt**  nastavit **WorkflowImportProject1** jako položku při spuštění.  
  
     Při ladění projektu okamžitě zobrazí v seznamu.  
  
11. Protože **Import opakovaně použitelného 2010 pracovního postupu služby SharePoint** šablony neimportuje přidružení hodnoty vlastností pro importované pracovní postup, je nutné je zadat. Provedete to následujícím způsobem:  
  
    1.  V **Průzkumníku řešení**, vyberte **SPD_Workflow_TestFT** uzlu.  
  
    2.  Zvolte se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "elipsy ASP.NET – Návrhář mobilních řešení")) tlačítko vedle jeden seznam vlastností, jako **cílového seznamu** vlastnost.  
  
    3.  Vyplňte chybějící hodnoty v průvodce nastavením služby SharePoint a potom vyberte **Dokončit** tlačítko.  
  
12. Zvolte soubor XOML a potom na panelu nabídek **zobrazení** > **Návrhář** zobrazíte importovaných pracovních postupů v Návrháři pracovních postupů.  
  
13. V **Windows Workflow v3.0** uzlu **sada nástrojů**, proveďte jednu z následujících kroků:  
  
    -   Otevřete místní nabídku pro **kód** aktivitu a potom zvolte **kopie**. V Návrháři pracovních postupů otevřete místní nabídku pro řádek v části **SequenceActivity1** aktivitu a potom zvolte **vložení**.  
  
    -   Přetáhněte **kód** aktivity z **sada nástrojů** pro návrháře pracovních postupů a připojte ho k řádku pod **SequenceActivity1** aktivity.  
  
     Tento postup přidá aktivitu do pracovního postupu návrháře s názvem **CodeActivity1**. V rámci této aktivity přidáte kód akci, která vytvoří oznámení v seznamu oznámení, když uživatel spustí pracovní postup.  
  
14. Proveďte jednu z následujících sad kroků:  
  
    -   Klikněte dvakrát na **CodeActivity1** Generovat obslužné rutiny události a zobrazení kódu.  
  
    -   V **vlastnosti** okna pro **CodeActivity1**, nastavte hodnotu **ExecuteCode** vlastnost **codeActivity_ExecuteCode**.  
  
15. Přidejte následující pod existující **pomocí** nebo **importy** příkazy:  
  
     [!code-csharp[SP_SPDWFImport#1](../sharepoint/codesnippet/CSharp/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.cs#1)]
     [!code-vb[SP_SPDWFImport#1](../sharepoint/codesnippet/VisualBasic/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.vb#1)]  
  
16. Nahraďte `codeActivity1_ExecuteCode` následujícím kódem:  
  
     [!code-csharp[SP_SPDWFImport#2](../sharepoint/codesnippet/CSharp/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.cs#2)]
     [!code-vb[SP_SPDWFImport#2](../sharepoint/codesnippet/VisualBasic/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.vb#2)]  
  
## <a name="deploy-the-project-and-associate-the-workflow"></a>Nasazení projektu a přidružení pracovního postupu
 Potom spusťte WorkflowImportProject1 k nasazení na web služby SharePoint a pak přidružit pracovního postupu k seznamu úloh pro zobrazení a testování upravené, převést pracovního postupu.  
  
#### <a name="to-deploy-the-project-and-associate-the-workflow"></a>Nasazení projektu a přidružení pracovního postupu  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vyberte **F5** klíče ke spuštění a nasazení projektu převedený pracovního postupu.  
  
2.  Na panel Rychlé spuštění, zvolte **úlohy** odkaz k zobrazení seznamu úloh.  
  
3.  Na **nástroje seznamu** , zvolte **položky** tlačítko a potom vyberte **nová položka** tlačítko.  
  
     **Úlohy – nová položka** otevře se dialogové okno.  
  
4.  V **název** zadejte **nová úloha**a potom zvolte **Uložit** tlačítko.  
  
5.  Na **nástroje seznamu** , zvolte **seznamu** tlačítko a potom vyberte **nastavení seznamu** tlačítko.  
  
     **Nastavení seznamu** se zobrazí stránka.  
  
6.  V **oprávnění a správa** zvolte **nastavení pracovních postupů** odkaz.  
  
     **Nastavení pracovních postupů** se zobrazí stránka.  
  
7.  Vyberte **přidat pracovní postup** odkaz.  
  
8.  V **pracovního postupu** vyberte **WorkflowImportProject1 - SPD pracovní postup Test**.  
  
9. V **název** zadejte **SPD pracovní postup Test**a potom zvolte **OK** tlačítko.  
  
10. V panel Rychlé spuštění, vyberte **úlohy** seznamu.  
  
11. Vyberte šipku vedle **nová úloha**a potom v seznamu, vyberte **pracovních**.  
  
12. V **spustit nový pracovní postup** zvolte odkaz pro **SPD pracovní postup Test**a potom zvolte **spustit** tlačítko zahájíte pracovního postupu.  
  
    > [!NOTE]  
    >  Alternativně můžete můžete automaticky přidružení pracovního postupu se seznamem spuštěním Průvodce nastavením pracovního postupu a nastavení pracovní postup automaticky přidružení.  
  
     Všimněte si, že dvě akce provádí pracovního postupu: vaše jméno se zobrazí v úkolu **přiřazeno** sloupce a oznámení se zobrazí v **oznámení** seznamu.  
  
## <a name="see-also"></a>Viz také:
 [Import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
