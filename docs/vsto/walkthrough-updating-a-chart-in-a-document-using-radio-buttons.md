---
title: "Návod: Aktualizace grafu v dokumentu s použitím přepínačů | Microsoft Docs"
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
- documents [Office development in Visual Studio], updating using controls
- controls [Office development in Visual Studio], updating documents
ms.assetid: 56e6d1f2-65a4-41f0-aff5-f0cfd96d7185
caps.latest.revision: "60"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2d6fa02174a8b334b404a0a4ea84ee0e8089c584
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-updating-a-chart-in-a-document-using-radio-buttons"></a>Návod: Aktualizace grafu v dokumentu s použitím přepínačů
  Tento návod ukazuje, jak používat přepínací tlačítka v přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Word uživatelům možnost zvolit styly grafu v dokumentu.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Přidáním grafu do dokumentu v projektech na úrovni dokumentu v době návrhu.  
  
-   Seskupování přepínačů jejich přidáním do uživatelského ovládacího prvku.  
  
-   Změna stylu grafu, pokud je vybrána možnost.  
  
 Výsledek jako hotová ukázka najdete v sekci Ukázka ovládací prvky aplikace Word v [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
 Prvním krokem je vytvoření projektu dokument aplikace Word.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu dokument aplikace Word s názvem **Moje možnosti grafu**. V průvodci vyberte **vytvoříte nový textový dokument**. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nový dokument aplikace Word v návrháři a přidá **Moje možnosti grafu** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-a-chart-to-the-document"></a>Přidáním grafu do dokumentu  
  
#### <a name="to-add-a-chart"></a>Chcete-li přidat graf  
  
1.  Do Wordového dokumentu, který je hostován v návrháři Visual Studio na pásu karet, klikněte **vložit** kartě.  
  
2.  V **Text** klikněte na možnost **vložit objekt** tlačítko rozevíracího seznamu a klikněte na tlačítko **objekt**.  
  
     **Objekt** otevře se dialogové okno.  
  
3.  V **typ objektu** seznam na **vytvořit nový** vyberte **graf aplikace Microsoft Graph** a pak klikněte na **OK**.  
  
     Graf se přidá do dokumentu na pozici kurzoru a **zobrazení datového** se zobrazí okno s některé výchozí data.  
  
4.  Zavřít **zobrazení datového** okno přijměte výchozí hodnoty v grafu a klikněte na tlačítko uvnitř dokumentu, který má přesunout fokus od grafu.  
  
5.  Klikněte pravým tlačítkem na graf a pak klikněte na **formát objektu**.  
  
6.  Na **rozložení** kartě **formát objektu** dialogové okno, vyberte **hranaté** a klikněte na tlačítko **OK**.  
  
## <a name="adding-a-user-control-to-the-project"></a>Přidání uživatelského ovládacího prvku do projektu  
 Přepínací tlačítka v dokumentu nejsou vzájemně se vylučuje ve výchozím nastavení. Je fungovat správně je pomocí přidání do ovládacího prvku uživatele a pak psaní kódu pro řízení výběr můžete provést.  
  
#### <a name="to-add-a-user-control"></a>Chcete-li přidat uživatelský ovládací prvek  
  
1.  Vyberte **Moje možnosti grafu** projektu v **Průzkumníku řešení**.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogové okno, klikněte na tlačítko **uživatelský ovládací prvek**, název ovládacího prvku **ChartOptions,** a klikněte na tlačítko **přidat**.  
  
#### <a name="to-add-windows-form-controls-to-the-user-control"></a>Přidání ovládacích prvků ve formuláři Windows do uživatelského ovládacího prvku  
  
1.  Pokud není zobrazená v Návrháři uživatelského ovládacího prvku, klikněte dvakrát na **ChartOptions** v **Průzkumníku řešení**.  
  
2.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte první **přepínač** řízení do uživatelského ovládacího prvku a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**columnChart**|  
    |**Text**|**Sloupcový graf**|  
  
3.  Přidejte druhý **přepínač** uživateli řídit a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**barChart**|  
    |**Text**|**Pruhový graf**|  
  
4.  Přidat třetí **přepínač** uživateli řídit a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**lineChart**|  
    |**Text**|**Spojnicový graf**|  
  
5.  Přidat čtvrtý **přepínač** uživateli řídit a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**areaBlockChart**|  
    |**Text**|**Plošný graf bloku**|  
  
## <a name="adding-references"></a>Přidávání odkazů  
 K grafu z uživatelského ovládacího prvku v dokumentu musíte mít odkaz na sestavení Microsoft.Office.Interop.Graph ve vašem projektu.  
  
#### <a name="to-add-a-reference-to-the-microsoftofficeinteropgraph-assembly"></a>Chcete-li přidat odkaz na sestavení Microsoft.Office.Interop.Graph  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat odkaz na**.  
  
     **Přidat odkaz na** zobrazí se dialogové okno.  
  
2.  Na **rozhraní .NET** vyberte **Microsoft.Office.Interop.Graph** a klikněte na tlačítko **OK**. Vyberte 14.0.0.0 verzi sestavení.  
  
## <a name="changing-the-chart-style-when-a-radio-button-is-selected"></a>Změna stylu grafu, pokud je vybrána přepínače  
 Chcete-li tlačítka fungovat správně, vytvořte veřejnou událost na uživatelského ovládacího prvku, přidání vlastnosti do nastavení výběru typu a vytvořit proceduru k `CheckedChanged` události jednotlivých přepínačů.  
  
#### <a name="to-create-an-event-and-property-on-a-user-control"></a>Vytvoření událostí a vlastnost na uživatelský ovládací prvek  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uživatelský ovládací prvek a potom klikněte na **kód zobrazení**.  
  
2.  Přidejte kód k vytvoření `SelectionChanged` událostí a `Selection` vlastnost, která má `ChartOptions` třídy.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#9](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#9)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#9](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#9)]  
  
#### <a name="to-handle-the-checkedchange-event-of-the-radio-buttons"></a>Zpracování události CheckedChange přepínacích tlačítek  
  
1.  Nastavte typ grafu v `CheckedChanged` obslužnou rutinu události `areaBlockChart` přepínač a poté vyvolat událost.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#10](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#10)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#10](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#10)]  
  
2.  Nastavte typ grafu v `CheckedChanged` obslužnou rutinu události `barChart` přepínač.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#11](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#11)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#11](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#11)]  
  
3.  Nastavte typ grafu v `CheckedChanged` obslužnou rutinu události `columnChart` přepínač.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#12](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#12)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#12](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#12)]  
  
4.  Nastavte typ grafu v `CheckedChanged` obslužnou rutinu události `lineChart` přepínač.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#13](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#13)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#13](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#13)]  
  
5.  V jazyce C# je nutné přidat obslužných rutin událostí pro přepínací tlačítka. Můžete přidat kód, který `ChartOptions` konstruktor pod volání `InitializeComponent`. Informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#14](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#14)]  
  
## <a name="adding-the-user-control-to-the-document"></a>Přidání uživatelského ovládacího prvku do dokumentu  
 Při sestavování řešení, se automaticky přidá do nového uživatelského ovládacího prvku **sada nástrojů**. Potom můžete přetáhnout z ovládacího prvku **sada nástrojů** do dokumentu.  
  
#### <a name="to-add-the-user-control-your-document"></a>Chcete-li přidat uživatelského ovládacího prvku dokument  
  
1.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
     **ChartOptions** uživatelský ovládací prvek je přidán do **sada nástrojů**.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **ThisDocument.vb** nebo **ThisDocument.cs**a potom klikněte na **Návrhář zobrazení**.  
  
3.  Přetáhněte `ChartOptions` řídit z **sada nástrojů** k dokumentu.  
  
     V **vlastnosti** období, název ovládací prvek, který jste právě přidali v dokumentu `ChartOptions1`.  
  
## <a name="changing-the-chart-type"></a>Změnit typ grafu.  
 Vytvoření obslužné rutiny události chcete-li změnit typ grafu podle možnosti vybrané v uživatelského ovládacího prvku.  
  
#### <a name="to-change-the-type-of-chart-that-is-displayed-in-the-document"></a>Chcete-li změnit typ grafu, který se zobrazí v dokumentu  
  
1.  Přidejte následující obslužné rutiny události pro `ThisDocument` třídy.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#15](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#15)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#15](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#15)]  
  
2.  V jazyce C#, je nutné přidat obslužné rutiny události pro ovládací prvek na <xref:Microsoft.Office.Tools.Word.Document.Startup> událostí.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#16](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#16)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat dokument a ujistěte se, že styl grafu je správně aktualizován, když vyberete přepínače.  
  
#### <a name="to-test-your-document"></a>K testování dokumentu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Vyberte různé přepínače.  
  
3.  Potvrďte, že styl grafu se změní tak, aby odpovídaly výběr.  
  
## <a name="next-steps"></a>Další kroky  
 Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Pomocí tlačítka k naplnění textové pole. Další informace najdete v tématu [návod: zobrazení textu v textovém poli v dokumentu pomocí tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md).  
  
-   Změna formátování výběrem styl z pole se seznamem. Další informace najdete v tématu [návod: Změna dokumentu formátování pomocí ovládacích prvků CheckBox](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Viz také  
 [Návody pro práci s aplikací Word](../vsto/walkthroughs-using-word.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Omezení ovládacích prvků Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  