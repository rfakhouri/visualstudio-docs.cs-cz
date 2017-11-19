---
title: "Návod: Shromažďování dat pomocí formuláře Windows | Microsoft Docs"
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
- data [Office development in Visual Studio], Windows Forms
- Windows Forms [Office development in Visual Studio], collecting data
- forms [Office development in Visual Studio], walkthroughs
- worksheets [Office development in Visual Studio], collecting data
ms.assetid: 40e87f7f-cfbb-4761-bf1b-d042f45f4f09
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 32156e4d2c9e8e5f809a4de64478667e7133aeb1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-collecting-data-using-a-windows-form"></a>Návod: Shromažďování dat pomocí formuláře Windows
  Tento návod ukazuje, jak otevřít formuláře Windows z přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Excel, shromažďovat informace od uživatele a zapíše tyto informace do buňky listu.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 I když tento návod používá konkrétně projektu úrovni dokumentu pro Excel, se použijí pro další projekty Office koncepty znázorněno pomocí průvodce.  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="creating-a-new-project"></a>Vytvoření nového projektu  
 Prvním krokem je vytvoření projektu sešitu aplikace Excel.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **WinFormInput**a vyberte **vytvoříte nový textový dokument** v průvodci. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **WinFormInput** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-a-namedrange-control-to-the-worksheet"></a>Přidání ovládacího prvku NamedRange do listu  
  
#### <a name="to-add-a-named-range-to-sheet1"></a>Přidání do Sheet1 pojmenované oblasti  
  
1.  Vyberte buňku **A1** na `Sheet1`.  
  
2.  V **název** zadejte **formInput**.  
  
     **Název** pole se nachází vlevo od řádku vzorců, nad sloupec **A** listu.  
  
3.  Stiskněte klávesu ENTER.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek přidán do buňky **A1**. Není nijak viditelně naznačeno na listu, ale **formInput** se zobrazí v **název** pole (nad listu na levé straně) a v **vlastnosti** okno při buňky **A1** je vybrána.  
  
## <a name="adding-a-windows-form-to-the-project"></a>Přidávání formuláře Windows k projektu  
 Vytvoření formuláře Windows k požádat uživatele o informace.  
  
#### <a name="to-add-a-windows-form"></a>Chcete-li přidat formuláře Windows  
  
1.  Vyberte projekt **WinFormInput** v **Průzkumníku řešení**.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat formuláře Windows**.  
  
3.  Název formátu **GetInputString.vb** nebo **GetInputString.cs**a potom klikněte na **přidat**.  
  
     Nový formulář se zobrazí v návrháři.  
  
4.  Přidat <xref:System.Windows.Forms.TextBox> a <xref:System.Windows.Forms.Button> do formuláře.  
  
5.  Kliknutím na tlačítko, najít vlastnost **Text** v **vlastnosti** okně a změňte text, který se **OK**.  
  
 V dalším kroku přidejte kód, který `ThisWorkbook.vb` nebo `ThisWorkbook.cs` ke shromažďování informací o uživateli.  
  
## <a name="displaying-the-windows-form-and-collecting-information"></a>Zobrazení formuláře Windows a shromažďování informací o  
 Vytvoření instance `GetInputString` formuláře Windows a zobrazit ji a pak zapsat informace uživatele do buňky v listu.  
  
#### <a name="to-display-the-form-and-collect-information"></a>Zobrazit formulář a shromažďovat informace  
  
1.  Klikněte pravým tlačítkem na **ThisWorkbook.vb** nebo **ThisWorkbook.cs** v **Průzkumníku řešení**a potom klikněte na **kód zobrazení**.  
  
2.  V <xref:Microsoft.Office.Tools.Excel.Workbook.Open> obslužné rutiny události z `ThisWorkbook`, přidejte následující kód, který deklarovat proměnnou pro daný formulář `GetInputString` a pak zobrazit formulář.  
  
    > [!NOTE]  
    >  V jazyce C#, musíte přidat obslužné rutiny události, jak je znázorněno v <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> následující událost. Informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingCollectingData#1](../vsto/codesnippet/CSharp/WinFormInputCS/ThisWorkbook.cs#1)]
     [!code-vb[Trin_VstcoreProgrammingCollectingData#1](../vsto/codesnippet/VisualBasic/WinFormInput/ThisWorkbook.vb#1)]  
  
3.  Vytvořit metodu s názvem `WriteStringToCell` , zapíše text do pojmenované oblasti. Tato metoda je volána z formuláře a uživatelský vstup je předána <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení, `formInput`, v buňce **A1**.  
  
     [!code-csharp[Trin_VstcoreProgrammingCollectingData#2](../vsto/codesnippet/CSharp/WinFormInputCS/ThisWorkbook.cs#2)]
     [!code-vb[Trin_VstcoreProgrammingCollectingData#2](../vsto/codesnippet/VisualBasic/WinFormInput/ThisWorkbook.vb#2)]  
  
 Dál přidejte kód pro formulář pro zpracování kliknutím na tlačítko událostí.  
  
## <a name="sending-information-to-the-worksheet"></a>Odesílání informace do listu  
  
#### <a name="to-send-information-to-the-worksheet"></a>K odeslání informací do listu  
  
1.  Klikněte pravým tlačítkem na **GetInputString** v **Průzkumníku řešení**a potom klikněte na **Návrhář zobrazení**.  
  
2.  Dvakrát klikněte na tlačítko pro otevření souboru kódu pomocí tlačítka <xref:System.Windows.Forms.Control.Click> přidání obslužné rutiny události.  
  
3.  Přidání kódu do obslužné rutiny události trvat vstup z textového pole, odešle funkce `WriteStringToCell`a pak zavřete formulář.  
  
     [!code-csharp[Trin_VstcoreProgrammingCollectingData#3](../vsto/codesnippet/CSharp/WinFormInputCS/GetInputString.cs#3)]
     [!code-vb[Trin_VstcoreProgrammingCollectingData#3](../vsto/codesnippet/VisualBasic/WinFormInput/GetInputString.vb#3)]  
  
## <a name="testing"></a>Testování  
 Teď můžete spustit projekt. Formuláře Windows se zobrazí, a váš vstup v listu.  
  
#### <a name="to-test-your-workbook"></a>K testování sešitu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Potvrďte, že se zobrazí formuláře Windows.  
  
3.  Typ **Hello, World** textového pole a pak klikněte na **OK**.  
  
4.  Potvrďte, že **Hello, World** se zobrazí v buňce **A1** listu.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základní informace o zobrazení formuláře Windows a předávání dat do listu. Jiné úlohy, které můžete chtít provést patří:  
  
-   Pomocí ovládacích prvků Windows Forms v sešitu aplikace Excel nebo dokument aplikace Word. Další informace najdete v tématu [ovládacích prvků Windows Forms na přehled dokumenty Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
-   Upravte uživatelské rozhraní aplikace Microsoft Office z přizpůsobení na úrovni dokumentu nebo doplňku VSTO. Další informace najdete v tématu [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Návody pro práci s aplikací Word](../vsto/walkthroughs-using-word.md)   
 [Návody pro práci s aplikací Excel](../vsto/walkthroughs-using-excel.md)  
  
  