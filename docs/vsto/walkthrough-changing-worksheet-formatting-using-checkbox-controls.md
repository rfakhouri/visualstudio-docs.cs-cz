---
title: 'Návod: Změna formátování listů s použitím ovládacích prvků CheckBox | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, changing formatting using managed controls
- worksheets, check box controls
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 35394b5f45e3c1e456dfcfae8f4b6db50af12147
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-changing-worksheet-formatting-using-checkbox-controls"></a>Návod: Změna formátování listů s použitím ovládacích prvků CheckBox
  Tento návod ukazuje základy používání zaškrtávací políčka na tabulku aplikace Microsoft Office Excel Změna formátování. Nástroje pro vývoj pro Office v sadě Visual Studio použije k vytvoření a přidání kódu do projektu. Výsledek jako hotová ukázka najdete v sekci Ukázka ovládací prvky aplikace Excel v [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Během tohoto návodu se dozvíte, jak:  
  
-   Přidejte text a ovládacích prvků na list.  
  
-   Pokud je vybrána možnost formátování textu.  
  
-   Testování projektu.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
 V tomto kroku vytvoříte projekt sešitu aplikace Excel pomocí sady Visual Studio.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **Moje aplikace Excel formátování**. Ujistěte se, že **vytvoříte nový textový dokument** je vybrána. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **Moje aplikace Excel formátování** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-text-and-controls-to-the-worksheet"></a>Přidávání textu a ovládacích prvků do listu  
 V tomto návodu budete potřebovat tři <xref:Microsoft.Office.Tools.Excel.Controls.CheckBox> ovládací prvky a text v <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku.  
  
#### <a name="to-add-three-check-boxes"></a>Chcete-li přidat tři políčka  
  
1.  Ověřte, zda je sešit otevřít v návrháři Visual Studio a že `Sheet1` je otevřený.  
  
2.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte <xref:Microsoft.Office.Tools.Excel.Controls.CheckBox> ovládacího prvku na nebo téměř buňky **B2** v **Sheet1**.  
  
3.  Z **zobrazení** nabídce vyberte možnost **vlastnosti** okno.  
  
4.  Zkontrolujte **Checkbox1** je viditelný v objektu název seznamu poli **vlastnosti** okně a změnit následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**applyBoldFont**|  
    |**Text**|**Bold**|  
  
5.  Přetáhněte druhý zaškrtávací políčko nebo v těsné blízkosti buňky **B4** a změnit následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**applyItalicFont**|  
    |**Text**|**Kurzíva**|  
  
6.  Přetáhněte třetí zaškrtávací políčko nebo v těsné blízkosti buňky **B6** a změnit následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**applyUnderlineFont**|  
    |**Text**|**Podtržení**|  
  
7.  Vyberte všechny ovládací prvky políčko tři podržíte klávesu CTRL.  
  
8.  Ve skupině uspořádat na kartě formátu v aplikaci Excel, klikněte na tlačítko **Align**a potom klikněte na **Zarovnat doleva**.  
  
     Ovládací prvky tři zaškrtávací políčko je zarovnán na levé straně, na pozici prvního ovládacího prvku, které jste vybrali.  
  
     V dalším kroku bude přetažení <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do listu.  
  
    > [!NOTE]  
    >  Můžete také přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení zadáním **textFont** do **název** pole.  
  
#### <a name="to-add-text-to-a-namedrange-control"></a>Chcete-li přidat text do ovládacího prvku NamedRange  
  
1.  Z **ovládací prvky aplikace Excel** karty z panelu nástrojů, přetáhněte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do buňky **B9**.  
  
2.  Ověřte, že **$B$ 9** se zobrazí v upravitelné textového pole a dané buňky **B9** je vybrána. Pokud není, klikněte na buňku **B9** ji vyberte.  
  
3.  Click **OK**.  
  
4.  Buňky **B9** stane oblast s názvem `NamedRange1`.  
  
     Není nijak viditelně naznačeno na listu, ale `NamedRange1` se zobrazí v **pole název** (nad listu na levé straně) Pokud buňka **B9** je vybrána.  
  
5.  Zkontrolujte **NamedRange1** je viditelný v objektu název seznamu poli **vlastnosti** okně a změnit následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**textFont**|  
    |**Value2**|**Klikněte na zaškrtávací políčko, chcete-li změnit formátování tento text.**|  
  
 Dále napište kód k formátování textu, pokud je vybrána možnost.  
  
## <a name="formatting-the-text-when-an-option-is-selected"></a>Formátování textu při možnost je vybrána.  
 V této části napíšete kód tak, aby v případě, že uživatel vybere možnost formátování, se změní formát textu v listu.  
  
#### <a name="to-change-formatting-when-a-check-box-is-selected"></a>Chcete-li změnit formátování při zaškrtávací políčko je zaškrtnuto  
  
1.  Klikněte pravým tlačítkem na **Sheet1**a potom klikněte na **kód zobrazení** v místní nabídce.  
  
2.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužnou rutinu události `applyBoldFont` políčko:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#7](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#7)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#7)]  
  
3.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužnou rutinu události `applyItalicFont` políčko:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#8](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#8)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#8)]  
  
4.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužnou rutinu události `applyUnderlineFont` políčko:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#9](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#9)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#9)]  
  
5.  V jazyce C#, je nutné přidat obslužné rutiny události pro pole a <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> událostí, jak je uvedeno níže. Informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#10)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat vašeho sešitu, abyste měli jistotu, že text správně naformátován při vyberte nebo zrušte zaškrtnutí políčka.  
  
#### <a name="to-test-your-workbook"></a>K testování sešitu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Vyberte nebo zrušte zaškrtnutí políčka.  
  
3.  Potvrďte, že text správně naformátován.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základní informace o použití zaškrtávacího políčka a formátování textu v listech aplikace Excel. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Nasazení projektu. Další informace najdete v tématu [nasazení řešení Office aplikací ClickOnce pomocí](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
-   Pomocí tlačítka k naplnění textové pole. Další informace najdete v tématu [návod: zobrazení textu v textovém poli v listu pomocí tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md).  
  
## <a name="see-also"></a>Viz také  
 [Návody pro práci s aplikací Excel](../vsto/walkthroughs-using-excel.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Omezení ovládacích prvků modelu Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  