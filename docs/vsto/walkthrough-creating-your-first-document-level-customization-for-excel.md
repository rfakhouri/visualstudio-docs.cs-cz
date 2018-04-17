---
title: 'Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, creating your first project
- Excel [Office development in Visual Studio], creating your first project
- document-level customizations [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f1a8335c301d8eba2ec170c9b1b462d09364904f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-your-first-document-level-customization-for-excel"></a>Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel
  Tento úvodní návod ukazuje, jak vytvořit přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Excel. Funkce, které vytvoříte v tento druh řešení jsou k dispozici pouze v případě, že konkrétní sešitu je otevřený. Nelze použít přizpůsobení na úrovni dokumentu celou aplikaci změnit, například zobrazení novou kartu pásu karet v otevřeném žádné sešitu.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu sešitu aplikace Excel.  
  
-   Přidávání textu do listu, který je hostován v návrháři Visual Studio.  
  
-   Psaní kódu, který používá objektový model aplikace Excel k přidání textu do přizpůsobené listu při otevření.  
  
-   Sestavení a spuštění projektu to vyzkoušíte.  
  
-   Čistí dokončený projekt k odebrání vývojovém počítači sestavení nepotřebných souborů a nastavení zabezpečení.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
  
#### <a name="to-create-a-new-excel-workbook-project-in-visual-studio"></a>Chcete-li vytvořit nový projekt sešitu aplikace Excel v sadě Visual Studio  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
4.  V části sada rozšířeného **Office/SharePoint** uzlu, vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu zvolte projektu doplňku VSTO v Excelu.  
  
6.  V **název** zadejte **FirstWorkbookCustomization**.  
  
7.  Click **OK**.  
  
     **Visual Studio Tools for Office – Průvodce projektem** otevře.  
  
8.  Vyberte **vytvoříte nový textový dokument**a klikněte na tlačítko **OK**.  
  
    -   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] vytvoří **FirstWorkbookCustomization** projektu a přidá následující soubory do projektu.  
  
    -   *FirstWorkbookCustomization*XLSX - představuje sešitu aplikace Excel v projektu. Obsahuje všechny listy a grafy.  
  
    -   Sheet1 (VB soubor pro soubor .cs pro Visual C# nebo Visual Basic) - listu, která poskytuje návrhová plocha a kód pro první listu v sešitu. Další informace najdete v tématu [hostitelská položka Worksheet](../vsto/worksheet-host-item.md).  
  
    -   Sheet2 (VB soubor pro soubor .cs pro Visual C# nebo Visual Basic) - listu, která poskytuje návrhová plocha a kód pro druhý listu v sešitu.  
  
    -   Sheet3 (VB soubor pro soubor .cs pro Visual C# nebo Visual Basic) - listu, která poskytuje návrhová plocha a kód pro třetí listu v sešitu.  
  
    -   ThisWorkbook (VB jazyka Visual Basic) nebo .cs souboru v jazyce Visual C# – obsahuje návrhová plocha a kód pro přizpůsobení na úrovni sešitu. Další informace najdete v tématu [hostitelská položka Workbook](../vsto/workbook-host-item.md).  
  
     K souboru kódu Sheet1 je automaticky otevřít v návrháři.  
  
## <a name="closing-and-reopening-worksheets-in-the-designer"></a>Zavřete a znovu otevřete listů v Návrháři  
 Pokud jste úmyslně nebo neúmyslně zavřít sešitu nebo listu v Návrháři při vývoji projektu, můžete ho znovu otevřít.  
  
#### <a name="to-close-and-reopen-a-worksheet-in-the-designer"></a>Zavřete a znovu otevřete sešit v Návrháři  
  
1.  Sešit zavřete kliknutím **Zavřít** tlačítko (X) pro návrháře okno.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **Sheet1** kód soubor a klikněte na tlačítko **Návrhář zobrazení**.  
  
     \- nebo –  
  
     V **Průzkumníku řešení**, dvakrát klikněte **Sheet1** souboru kódu.  
  
## <a name="adding-text-to-a-worksheet-in-the-designer"></a>Přidávání textu na list v Návrháři  
 Uživatelské rozhraní (UI) můžete navrhnout vaše přizpůsobení úpravou listu, která je otevřený v návrháři. Můžete například přidat text do buněk, použít ve vzorcích nebo přidat ovládací prvky aplikace Excel. Další informace o tom, jak použít Návrháře dotazů najdete v tématu [projektech pro systém Office v prostředí sady Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
#### <a name="to-add-text-to-a-worksheet-by-using-the-designer"></a>Chcete-li přidat text do listu pomocí návrháře  
  
1.  V listu, která je otevřený v návrháři, vyberte buňku **A1**a potom zadejte následující text.  
  
     **Tento text byl přidán pomocí návrháře.**  
  
> [!WARNING]  
>  Když přidáte tento řádek textu buňky **A2**, budou přepsány jiný kód v tomto příkladu.  
  
## <a name="adding-text-to-a-worksheet-programmatically"></a>Přidávání textu do listu prostřednictvím kódu programu  
 Dál přidejte kód do souboru kódu Sheet1. Nový kód používá objektový model aplikace Excel k přidání druhého řádku textu do sešitu. Ve výchozím nastavení soubor Sheet1 kód obsahuje následující generovaný kód:  
  
-   Částečné definice `Sheet1` třída, která představuje programovací model listu a poskytuje přístup k modelu objektů aplikace Excel. Další informace najdete [hostitelská položka Worksheet](../vsto/worksheet-host-item.md) a [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md). Zbývající část `Sheet1` třída definovaná v souboru skrytá kódu, který byste neměli upravovat.  
  
-   `Sheet1_Startup` a `Sheet1_Shutdown` obslužné rutiny událostí. Tyto obslužné rutiny událostí jsou volány při Excel načte a uvolní vlastní. Použití těchto obslužných rutin událostí k chybě při inicializaci vlastní, když je načten a vyčištění prostředků, které používají vlastní při je odpojen. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-a-second-line-of-text-to-the-worksheet-by-using-code"></a>Přidání druhého řádku textu do listu s použitím kódu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Sheet1**a potom klikněte na **kód zobrazení**.  
  
     Otevření souboru kódu v sadě Visual Studio.  
  
2.  Nahraďte `Sheet1_Startup` obslužné rutiny události s následujícím kódem. Po otevření Sheet1 tento kód přidá druhý řádek textu do listu.  
  
     [!code-csharp[Trin_ExcelWorkbookTutorial#1](../vsto/codesnippet/CSharp/Trin_ExcelWorkbookTutorial/Sheet1.cs#1)]
     [!code-vb[Trin_ExcelWorkbookTutorial#1](../vsto/codesnippet/VisualBasic/Trin_ExcelWorkbookTutorial/Sheet1.vb#1)]  
  
## <a name="testing-the-project"></a>Testování projektu  
  
#### <a name="to-test-your-workbook"></a>K testování sešitu  
  
1.  Stiskněte klávesu **F5** sestavení a spuštění projektu.  
  
     Při sestavování projektu se zkompilovat kód do sestavení, které je přidružený sešit. Visual Studio převádí kopii sešitu a sestavení v zadané výstupní složce sestavení projektu a nakonfiguruje nastavení zabezpečení na vývojovém počítači za účelem přizpůsobení ke spuštění. Další informace najdete v tématu [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
2.  V sešitu ověřte, že vidíte následující text.  
  
     **Tento text byl přidán pomocí návrháře.**  
  
     **Tento text byl přidán pomocí kódu.**  
  
3.  Zavřete.  
  
## <a name="cleaning-up-the-project"></a>Čištění projektu  
 Po dokončení vývoj projektu, byste měli odebrat soubory v zadané výstupní složce sestavení a nastavení zabezpečení vytvořené procesu sestavení.  
  
#### <a name="to-clean-up-the-completed-project-on-your-development-computer"></a>Vyčistěte dokončený projekt na vývojovém počítači  
  
1.  V sadě Visual Studio na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**.  
  
## <a name="next-steps"></a>Další kroky  
 Teď, když jste vytvořili základní přizpůsobení na úrovni dokumentu pro Excel, můžete další informace o tom, jak vyvíjet přizpůsobení z těchto témat:  
  
-   Obecné programování úlohy, které můžete provádět v přizpůsobeních na úrovni dokumentu: [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).  
  
-   Úlohy programování, které jsou specifické pro přizpůsobení na úrovni dokumentu pro Excel: [řešení pro aplikaci Excel](../vsto/excel-solutions.md).  
  
-   Pomocí modelu objektů aplikace Excel: [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).  
  
-   Přizpůsobení uživatelského rozhraní aplikace Excel, například pomocí vytvoření vlastní karty na pásu karet nebo vytvoření vlastního podokna akce: [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
-   Pomocí rozšířených objektů aplikace Excel poskytuje nástroje pro vývoj pro Office v sadě Visual Studio k provádění úloh, které nejsou možné pomocí model objektů aplikace Excel (například hostování spravovaných ovládacích prvků v dokumentech a vazba ovládací prvky aplikace Excel k datům s použitím Windows Forms datové vazby modelu): [automatizace aplikace Excel pomocí rozšířených objekty](../vsto/automating-excel-by-using-extended-objects.md).  
  
-   Sestavování a ladění přizpůsobení na úrovni dokumentu pro Excel: [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
-   Nasazení přizpůsobení na úrovni dokumentu pro Excel: [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Řešení pro aplikaci Excel](../vsto/excel-solutions.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Přehled šablon projektů Microsoft Office Project](../vsto/office-project-templates-overview.md)  
  
  