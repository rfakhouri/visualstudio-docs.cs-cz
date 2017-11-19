---
title: "Návod: Zobrazení textu v textovém poli na listu s použitím tlačítka | Microsoft Docs"
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
- text [Office development in Visual Studio], displaying worksheets
- worksheets, displaying text
- text boxes, displaying text in worksheets
- text [Office development in Visual Studio], text boxes
ms.assetid: 59b73159-aab7-4f61-9ace-1723c18d78d6
caps.latest.revision: "56"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1b95eb6eeb5f8615f8f471ad33139afa49d5633f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button"></a>Návod: Zobrazení textu v textovém poli na listu s použitím tlačítka
  Tento návod ukazuje základy používání tlačítka a pole textu v listech aplikace Microsoft Office Excel a postup vytvoření projekty aplikace Excel pomocí nástroje pro vývoj pro Office v sadě Visual Studio. Výsledek jako hotová ukázka najdete v sekci Ukázka ovládací prvky aplikace Excel v [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Během tohoto návodu se dozvíte, jak:  
  
-   Přidání ovládacích prvků na list.  
  
-   V textovém poli naplňte při stisknutí tlačítka.  
  
-   Testování projektu.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
 V tomto kroku vytvoříte projekt sešitu aplikace Excel pomocí sady Visual Studio.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **Moje aplikace Excel tlačítko**. Ujistěte se, že **vytvoříte nový textový dokument** je vybrána. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **Moje aplikace Excel tlačítko** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-controls-to-the-worksheet"></a>Přidání ovládacích prvků na list  
 V tomto návodu budete potřebovat tlačítka a textové pole na prvním listu.  
  
#### <a name="to-add-a-button-and-a-text-box"></a>Přidání tlačítka a textové pole  
  
1.  Ověřte, zda **Moje aplikace Excel Button.xlsx** je sešit otevřít v návrháři Visual Studio s `Sheet1` zobrazí.  
  
2.  Z **běžné ovládací prvky** karty z panelu nástrojů, přetáhněte <xref:Microsoft.Office.Tools.Excel.Controls.TextBox> k `Sheet1`.  
  
3.  Z **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.  
  
4.  Ujistěte **TextBox1** se zobrazí na **vlastnosti** okno rozevíracího seznamu a změňte **název** vlastnosti textového pole **ZobrazenýText**.  
  
5.  Přetáhněte **tlačítko** na ovládací prvek `Sheet1` a změnit následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**insertText**|  
    |**Text**|**Zadejte Text**|  
  
 Nyní psát kód pro spuštění při kliknutí na tlačítko.  
  
## <a name="populating-the-text-box-when-the-button-is-clicked"></a>Při kliknutí na tlačítko naplnění textového pole  
 Pokaždé, když uživatel klikne na tlačítko **Hello, World!** připojí se k textového pole.  
  
#### <a name="to-write-to-the-text-box-when-the-button-is-clicked"></a>Při kliknutí na tlačítko zapsat do textového pole  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Sheet1**a potom klikněte na **kód zobrazení** v místní nabídce.  
  
2.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužné rutiny události tlačítka:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#11](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#11)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#11)]  
  
3.  V jazyce C#, je nutné přidat obslužnou rutinu události a <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> událostí, jak je uvedeno níže. Informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#12)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat váš sešit Ujistěte se, že zpráva **Hello, World!** v textovém poli se zobrazí, když kliknete na tlačítko.  
  
#### <a name="to-test-your-workbook"></a>K testování sešitu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Klikněte na tlačítko.  
  
3.  Potvrďte, že **Hello World!** Zobrazí se v textovém poli.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základy používání tlačítka a textová pole na listech aplikace Excel. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Nasazení projektu. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
-   Chcete-li změnit formátování pomocí zaškrtávacích políček. Další informace najdete v tématu [návod: Změna listu formátování pomocí ovládacích prvků CheckBox](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Přidání ovládacích prvků do dokumentů Office Windows Forms](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Návody pro práci s aplikací Excel](../vsto/walkthroughs-using-excel.md)   
 [Omezení ovládacích prvků Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  