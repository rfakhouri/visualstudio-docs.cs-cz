---
title: "Návod: Vytvoření vašeho prvního doplňku VSTO pro Excel | Microsoft Docs"
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
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- add-ins [Office development in Visual Studio], creating your first project
- Excel [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: de2b241cd44adebecd91ee097ebf8f8875915937
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-your-first-vsto-add-in-for-excel"></a>Postup: Vytvoření prvního doplňku VSTO pro Excel
  Tento úvodní návod ukazuje, jak vytvořit úrovni aplikace Add-in pro aplikaci Microsoft Office Excel. Funkce, které vytvoříte v tento druh řešení jsou k dispozici pro vlastní, bez ohledu na to, které jsou otevřené sešity aplikace.  
  
 [!INCLUDE[appliesto_xlallapp](../vsto/includes/appliesto-xlallapp-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu doplňku VSTO v Excelu pro aplikaci Excel.  
  
-   Psaní kódu, který používá objektový model aplikace Excel k přidání textu do sešitu při jeho uložení.  
  
-   Sestavení a spuštění projektu to vyzkoušíte.  
  
-   Čistí dokončený projekt tak, aby doplňku VSTO již nebude automaticky spustí na svém vývojovém počítači.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
  
#### <a name="to-create-a-new-excel-vsto-add-in-project-in-visual-studio"></a>K vytvoření nového projektu doplňku VSTO pro Excel v sadě Visual Studio  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
4.  V části sada rozšířeného **Office/SharePoint** uzlu, vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu, vyberte **doplněk aplikace Excel 2010** nebo **doplněk Excelu 2013**.  
  
6.  V **název** zadejte **FirstExcelAddIn**.  
  
7.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]vytvoří **FirstExcelAddIn** projektu a otevře soubor ThisAddIn kódu v editoru.  
  
## <a name="writing-code-to-add-text-to-the-saved-workbook"></a>Psaní kódu přidat Text do uloženého sešitu  
 Dál přidejte kód do souboru kódu ThisAddIn. Nový kód používá objektový model aplikace Excel k vložení často používaný text v prvním řádku aktivního listu. Aktivního listu je listu, která je otevřená, když uživatel uloží do sešitu. Ve výchozím nastavení soubor ThisAddIn kód obsahuje následující generovaný kód:  
  
-   Částečné definice `ThisAddIn` třídy. Tato třída představuje vstupní bod pro kód a poskytuje přístup k modelu objektů aplikace Excel. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md). Zbývající část `ThisAddIn` třída definovaná v souboru skrytá kódu, který byste neměli upravovat.  
  
-   `ThisAddIn_Startup` a `ThisAddIn_Shutdown` obslužné rutiny událostí. Tyto obslužné rutiny událostí jsou volány při Excel načte a uvolní vaší doplňku VSTO. Pomocí těchto obslužných rutin událostí k chybě při inicializaci doplňku VSTO, když je načten a vyčistit prostředky využívané třídou vaší Add-in, když je odpojen. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-a-line-of-text-to-the-saved-workbook"></a>Přidání řádku textu uložené sešitu  
  
1.  V souboru kódu ThisAddIn, přidejte následující kód, který `ThisAddIn` třídy. Nový kód definuje obslužnou rutinu události pro <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> událost, která se vyvolá, když je sešit uložit.  
  
     Když uživatel uloží sešitu, obslužné rutiny události přidá nový text na začátku aktivního listu.  
  
     [!code-vb[Trin_ExcelAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ExcelAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_ExcelAddInTutorial/ThisAddIn.cs#1)]  
  
2.  Pokud používáte C#, přidat následující požadované kód, který `ThisAddIn_Startup` obslužné rutiny události. Tento kód se používá k připojení `Application_WorkbookBeforeSave` obslužné rutiny události s <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> událostí.  
  
     [!code-csharp[Trin_ExcelAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_ExcelAddInTutorial/ThisAddIn.cs#2)]  
  
 Chcete-li upravit sešit při jeho uložení, předchozí příklady kódu použijte následující objekty:  
  
-   `Application` Pole z `ThisAddIn` třídy. `Application` Pole vrátí <xref:Microsoft.Office.Interop.Excel.Application> objekt, který představuje aktuální instanci aplikace Excel.  
  
-   `Wb` Parametr obslužné rutiny události pro <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> událostí. `Wb` Parametr <xref:Microsoft.Office.Interop.Excel.Workbook> objekt, který reprezentuje uložené sešitu. Další informace najdete v tématu [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).  
  
## <a name="testing-the-project"></a>Testování projektu  
  
#### <a name="to-test-the-project"></a>Otestování projektu  
  
1.  Stiskněte klávesu **F5** sestavení a spuštění projektu.  
  
     Při sestavování projektu se zkompilovat kód do sestavení, které je součástí složku výstupu sestavení pro projekt. Visual Studio také vytvoří sadu položky registru, které umožňují Excel zjišťovat a načíst doplňku VSTO a nakonfiguruje nastavení zabezpečení na vývojovém počítači povolit doplňku VSTO ke spuštění. Další informace najdete v tématu [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
2.  V aplikaci Excel uložte sešit.  
  
3.  Ověřte, zda je přidána následující text k sešitu.  
  
     **Tento text byl přidán pomocí kódu.**  
  
4.  Zavření Excelu.  
  
## <a name="cleaning-up-the-project"></a>Čištění projektu  
 Po dokončení vývoj projektu, odeberte z vývojovém počítači doplňku VSTO sestavení, položky registru a nastavení zabezpečení. V opačném doplňku VSTO bude nadále spouštět pokaždé, když ve svém vývojovém počítači otevřete aplikaci Excel.  
  
#### <a name="to-clean-up-the-completed-project-on-your-development-computer"></a>Vyčistěte dokončený projekt na vývojovém počítači  
  
1.  V sadě Visual Studio na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**.  
  
## <a name="next-steps"></a>Další kroky  
 Teď, když jste vytvořili základní Add-in VSTO pro Excel, můžete další informace o tom, jak vyvíjet doplňků VSTO z těchto témat:  
  
-   Obecné programování úlohy, které můžete provádět v doplňcích VSTO: [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
-   Úlohy programování, které jsou specifické pro doplňky VSTO aplikace Excel: [řešení pro aplikaci Excel](../vsto/excel-solutions.md).  
  
-   Pomocí modelu objektů aplikace Excel: [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).  
  
-   Přizpůsobení uživatelského rozhraní (UI) aplikace Excel, například pomocí vytvoření vlastní karty na pásu karet nebo vytváření vlastních vlastního podokna úloh: [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
-   Sestavování a ladění doplňků VSTO pro Excel: [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
-   Nasazení doplňků VSTO pro Excel: [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled vývoje řešení pro systém Office &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Řešení pro aplikaci Excel](../vsto/excel-solutions.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Přehled šablon projektů Microsoft Office Project](../vsto/office-project-templates-overview.md)  
  
  