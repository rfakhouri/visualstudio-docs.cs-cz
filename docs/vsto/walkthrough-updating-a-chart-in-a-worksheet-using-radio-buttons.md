---
title: 'Návod: Aktualizace grafu na listu s použitím přepínačů | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, updating using managed controls
- controls [Office development in Visual Studio], updating worksheets
- worksheets, using radio buttons
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fbdbcc8ae12e1b0f317b53a4f0ffd7e9b2885aec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons"></a>Návod: Aktualizace grafu na listu s použitím přepínačů
  Tento návod ukazuje základy používání rádiová tlačítka na tabulku aplikace Microsoft Office Excel poskytuje způsob, jak rychle přepínat mezi možnostmi uživateli. V takovém případě možnosti změnit styl grafu.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Výsledek jako hotová ukázka najdete v sekci Ukázka ovládací prvky aplikace Excel v [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Přidání skupiny přepínačů do listu.  
  
-   Změna stylu grafu, pokud je vybrána možnost.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="adding-a-chart-to-a-worksheet"></a>Přidáním grafu do listu  
 Můžete vytvořit projekt sešitu aplikace Excel, který upravuje existující sešit. V tomto návodu k sešitu přidáte graf a pak použít tento sešit nové řešení aplikace Excel. Zdroj dat v tomto návodu je to list s názvem **Data grafu**.  
  
#### <a name="to-add-the-data"></a>Chcete-li přidat data  
  
1.  Otevřete aplikaci Microsoft Excel.  
  
2.  Klikněte pravým tlačítkem myši **Sheet3** a pak klikněte **přejmenovat** v místní nabídce.  
  
3.  Přejmenování seznamu můžete **Data grafu**.  
  
4.  Přidejte následující data, která mají **Data grafu** s buňky A4 se levý horní roh a E8 pravého dolního rohu.  
  
    ||OTÁZKA Č. 1|DOTAZ Č. 2|3. ČTVRTLETÍ|OTÁZKA Č. 4|  
    |-|--------|--------|--------|--------|  
    |– Západ|500|550|550|600|  
    |– Východ|600|625|675|700|  
    |– sever|450|470|490|510|  
    |– Jih|800|750|775|790|  
  
 Dále přidáte první listu pro zobrazení dat grafu.  
  
#### <a name="to-add-a-chart-in-excel"></a>Chcete-li přidat graf v aplikaci Excel  
  
1.  Na **vložit** ve **grafy** klikněte na možnost **sloupec**a potom klikněte na **všechny typy grafů**.  
  
2.  V **vložit graf** dialogové okno, klikněte na tlačítko **OK**.  
  
3.  Na **návrhu** ve **Data** klikněte na možnost **vyberte Data**.  
  
4.  V **vybrat zdroj dat** dialogové okno, klikněte v **Chartdata rozsah** a zrušte všechny výchozí výběr.  
  
5.  V **Data grafu** list, vyberte blok buněk, který obsahuje čísla, která zahrnuje A4 v levém horním rohu na E8 v pravém dolním rohu.  
  
6.  V **vybrat zdroj dat** dialogové okno, klikněte na tlačítko **OK**.  
  
7.  Změna umístění grafu tak, aby pravého horního rohu zarovnaná s buňky **E2**.  
  
8.  Uložte soubor na jednotce C a pojmenujte ji **ExcelChart.xlsx**.  
  
9. Ukončete aplikaci Excel.  
  
## <a name="creating-a-new-project"></a>Vytvoření nového projektu  
 V tomto kroku vytvoříte projekt sešitu aplikace Excel na základě **ExcelGraf** sešitu.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **Moje aplikace Excel graf**. V průvodci vyberte **zkopírovat stávající dokument**.  
  
     Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Klikněte **Procházet** buttonand procházení k sešitu, který jste vytvořili dříve v tomto návodu.  
  
3.  Click **OK**.  
  
     Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **Moje aplikace Excel graf** projektu do **Průzkumníku řešení**.  
  
## <a name="setting-properties-of-the-chart"></a>Nastavení vlastností grafu  
 Když vytvoříte nový projekt sešitu aplikace Excel, která používá existující sešit, hostitelské ovládací prvky se vytvářejí automaticky pro všechny pojmenované oblasti, seznamy a grafy v sešitu. Můžete změnit název <xref:Microsoft.Office.Tools.Excel.Chart> ovládacího prvku pomocí **vlastnosti** okno.  
  
#### <a name="to-change-the-name-of-the-chart-control"></a>Chcete-li změnit název ovládacího prvku grafu  
  
1.  Vyberte <xref:Microsoft.Office.Tools.Excel.Chart> řízení v návrháři a změnit následující vlastnosti v **vlastnosti** okno.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**dataChart**|  
    |**HasLegend**|**false**|  
  
## <a name="adding-controls"></a>Přidání ovládacích prvků  
 Tento list používá přepínače uživatelům způsob, jak rychle změnit styl grafu. Přepínací tlačítka však musí být výhradní – Pokud je vybraný jeden tlačítko, lze vybrat žádné jiné tlačítko ve skupině ve stejnou dobu. Toto chování se neodehrává ve výchozím nastavení, pokud přidáte několik přepínačů do listu.  
  
 Jeden způsob, jak přidat toto chování je k seskupení přepínačů v uživatelského ovládacího prvku zadejte kód za uživatelského ovládacího prvku a pak přidejte uživatelského ovládacího prvku do listu.  
  
#### <a name="to-add-a-user-control"></a>Chcete-li přidat uživatelský ovládací prvek  
  
1.  Vyberte **Moje aplikace Excel graf** projektu v **Průzkumníku řešení**.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogové okno, klikněte na tlačítko **uživatelský ovládací prvek**, název ovládacího prvku **ChartOptions,** a klikněte na tlačítko **přidat**.  
  
#### <a name="to-add-radio-buttons-to-the-user-control"></a>Přidání přepínače do uživatelského ovládacího prvku  
  
1.  Pokud není zobrazená v Návrháři uživatelského ovládacího prvku, klikněte dvakrát na **ChartOptions** v **Průzkumníku řešení**.  
  
2.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte ji **přepínač** řízení do uživatelského ovládacího prvku a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**columnChart**|  
    |**Text**|**Sloupcový graf**|  
  
3.  Přidejte druhý přepínače do uživatelského ovládacího prvku a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**barChart**|  
    |**Text**|**Pruhový graf**|  
  
4.  Přidejte třetí přepínače do uživatelského ovládacího prvku a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**lineChart**|  
    |**Text**|**Spojnicový graf**|  
  
5.  Přidejte čtvrtý přepínače do uživatelského ovládacího prvku a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**areaBlockChart**|  
    |**Text**|**Plošný graf bloku**|  
  
 Dále napište kód aktualizovat graf při kliknutí na přepínače.  
  
## <a name="changing-the-chart-style-when-a-radio-button-is-selected"></a>Změna grafu stylu při přepínač je vybrána.  
 Teď můžete přidat kód změnit styl grafu. Vytvořit veřejnou událost na uživatelského ovládacího prvku, přidání vlastnosti do nastavení výběru typu a vytvoření obslužné rutiny události pro `CheckedChanged` události jednotlivých přepínačů.  
  
#### <a name="to-create-an-event-and-property-on-a-user-control"></a>Vytvoření událostí a vlastnost na uživatelský ovládací prvek  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uživatelský ovládací prvek a potom klikněte na **kód zobrazení**.  
  
2.  Přidejte kód, který `ChartOptions` třídy za účelem vytvoření `SelectionChanged` událostí a `Selection` vlastnost.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#13](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#13)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#13)]  
  
#### <a name="to-handle-the-checkedchanged-event-of-the-radio-buttons"></a>Zpracování události CheckedChanged přepínacích tlačítek  
  
1.  Nastavte typ grafu v `CheckedChanged` obslužnou rutinu události `areaBlockChart` přepínač a poté vyvolat událost.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#14](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#14)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#14)]  
  
2.  Nastavte typ grafu v `CheckedChanged` obslužnou rutinu události `barChart` přepínač.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#15](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#15)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#15](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#15)]  
  
3.  Nastavte typ grafu v `CheckedChanged` obslužnou rutinu události `columnChart` přepínač.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#16](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#16)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#16)]  
  
4.  Nastavte typ grafu v `CheckedChanged` obslužnou rutinu události `lineChart` přepínač.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#17](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#17)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#17)]  
  
5.  V jazyce C# je nutné přidat obslužných rutin událostí pro přepínací tlačítka. Můžete přidat kód, který `ChartOptions` konstruktor pod volání `InitializeComponent`. Informace o tom, jak vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#18)]  
  
## <a name="adding-the-user-control-to-the-worksheet"></a>Přidání uživatelského ovládacího prvku do listu  
 Při sestavování řešení, se automaticky přidá do nového uživatelského ovládacího prvku **sada nástrojů**. Potom můžete přetáhnout z ovládacího prvku **sada nástrojů** do listu.  
  
#### <a name="to-add-the-user-control-your-worksheet"></a>Chcete-li přidat uživatelský ovládací prvek listu  
  
1.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
     **ChartOptions** uživatelský ovládací prvek je přidán do **sada nástrojů**.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Sheet1.vb** nebo **Sheet1.cs**a potom klikněte na **Návrhář zobrazení**.  
  
3.  Přetáhněte **ChartOptions** řídit z **sada nástrojů** do listu.  
  
     Nový ovládací prvek s názvem `my_Excel_Chart_ChartOptions1` se přidá do projektu.  
  
4.  Změňte název ovládacího prvku na **ChartOptions1**.  
  
## <a name="changing-the-chart-type"></a>Změnit typ grafu.  
 Chcete-li změnit typ grafu, vytvořte obslužnou rutinu události, která nastavuje styl podle možnosti vybrané v uživatelského ovládacího prvku.  
  
#### <a name="to-change-the-type-of-chart-that-is-displayed-in-the-worksheet"></a>Chcete-li změnit typ grafu, který se zobrazí v listu  
  
1.  Přidejte následující obslužné rutiny události pro `Sheet1` třídy.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#19](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#19)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#19)]  
  
2.  V jazyce C#, je nutné přidat obslužné rutiny události pro ovládací prvek uživatele k <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> událostí, jak je uvedeno níže. Informace o tom, jak vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#20)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat vašeho sešitu, chcete-li ověřit, že graf je navržen tak správně, když vyberete přepínače.  
  
#### <a name="to-test-your-workbook"></a>K testování sešitu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Vyberte různé přepínače.  
  
3.  Potvrďte, že styl grafu se změní tak, aby odpovídaly výběr.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základy používání přepínačů a styly grafu na listech. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Nasazení projektu. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
-   Pomocí tlačítka k naplnění textové pole. Další informace najdete v tématu [návod: zobrazení textu v textovém poli v listu pomocí tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md).  
  
-   Formátování v listu pomocí zaškrtávacích políček změnit. Další informace najdete v tématu [návod: Změna listu formátování pomocí ovládacích prvků CheckBox](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Viz také  
 [Návody pro práci s aplikací Excel](../vsto/walkthroughs-using-excel.md)  
  
  