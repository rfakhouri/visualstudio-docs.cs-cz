---
title: 'Návod: Změna formátování dokumentů s použitím ovládacích prvků CheckBox'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word documents, changing formatting using controls
- documents [Office development in Visual Studio], formatting
- check boxes, Word documents
- documents [Office development in Visual Studio], check box controls
- controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 459253c6a84add4fcca68565d5bf082dc0931f22
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34263861"
---
# <a name="walkthrough-change-document-formatting-using-checkbox-controls"></a>Návod: Změna formátování dokumentů s použitím ovládacích prvků CheckBox
  Tento návod ukazuje, jak používat ovládací prvky Windows Forms v přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Word Změna formátování textu.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Přidávání textu a ovládacího prvku v dokumentu v projektech na úrovni dokumentu v době návrhu.  
  
-   Formátování textu, pokud je vybrána možnost.  
  
 Výsledek jako hotová ukázka najdete v sekci Ukázka ovládací prvky aplikace Word v [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="create-the-project"></a>Vytvoření projektu  
 Prvním krokem je vytvoření projektu dokument aplikace Word.  
  
### <a name="create-a-new-project"></a>Vytvoření nového projektu  
  
1.  Vytvoření projektu dokument aplikace Word s názvem **Moje aplikace Word formátování**. V průvodci vyberte **vytvoříte nový textový dokument**.  
  
     Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nový dokument aplikace Word v návrháři a přidá **Moje aplikace Word formátování** projektu do **Průzkumníku řešení**.  
  
## <a name="add-text-and-controls-to-the-word-document"></a>Přidávání textu a ovládacích prvků do dokumentů aplikace Word  
 Pro účely tohoto postupu přidat tři políčka a text v <xref:Microsoft.Office.Tools.Word.Bookmark> řízení dokument aplikace Word. Zaškrtněte políčka nabídne možnosti pro uživatele pro formátování textu.  
  
### <a name="add-three-check-boxes"></a>Přidejte tři políčka  
  
1.  Ověřte, že dokument otevřít v návrháři Visual Studio.  
  
2.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte první <xref:Microsoft.Office.Tools.Word.Controls.CheckBox> ovládací prvek v dokumentu.  
  
3.  V **vlastnosti** okně změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**applyBoldFont**|  
    |**Text**|**Bold**|  
  
4.  Stiskněte klávesu **Enter** přesuňte kurzor pod zaškrtávacím políčkem první.  
  
5.  Přidání druhého zaškrtávacího políčka v dokumentu níže `ApplyBoldFont` zaškrtněte políčko a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**applyItalicFont**|  
    |**Text**|**Kurzíva**|  
  
6.  Stiskněte klávesu **Enter** přesuňte kurzor pod zaškrtávacím políčkem druhý.  
  
7.  Přidat třetí zaškrtávací políčko k dokumentu níže `ApplyItalicFont` zaškrtněte políčko a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**applyUnderlineFont**|  
    |**Text**|**Podtržení**|  
  
### <a name="add-text-and-a-bookmark-control"></a>Přidávání textu a ovládacího prvku záložek  
  
1.  Přesuňte kurzor na následující ovládací prvky zaškrtávacích políček a zadejte následující text:  
  
     **Klikněte na zaškrtávací políčko, chcete-li změnit formátování tento text.**  
  
2.  Z **ovládací prvky aplikace Word** kartě **sada nástrojů**, přetáhněte ji <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek v dokumentu.  
  
     **Přidání ovládacího prvku záložek** zobrazí se dialogové okno.  
  
3.  Vyberte text, který jste přidali do dokumentu a klikněte na tlačítko **OK**.  
  
     A <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek s názvem **Bookmark1** je přidat do vybraného textu v dokumentu.  
  
4.  V **vlastnosti** okno, změňte hodnotu **(název)** vlastnost **fontText.**  
  
 Dále napište kód k formátování textu, když je zaškrtávací políčko zaškrtnuto, nezaškrtnuto.  
  
## <a name="format-the-text-when-a-check-box-is-checked-or-cleared"></a>Pokud zaškrtávací políčko je zaškrtnuto nebo Vymazat formátování textu  
 Když uživatel vybere možnost formátování, změňte formát text v dokumentu.  
  
### <a name="change-formatting-when-a-check-box-is-selected"></a>Změna formátování, pokud je zaškrtnuto zaškrtávací políčko  
  
1.  Klikněte pravým tlačítkem na `ThisDocument` v **Průzkumníku řešení**a potom klikněte na **kód zobrazení** v místní nabídce.  
  
2.  Pro jazyk C# pouze, přidejte následující konstanty, na **ThisDocument** třídy.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#2)]  
  
3.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužnou rutinu události `applyBoldFont` zaškrtávací políčko.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#3](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#3)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#3](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#3)]  
  
4.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužnou rutinu události `applyItalicFont` zaškrtávací políčko.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#4](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#4)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#4](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#4)]  
  
5.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužnou rutinu události `applyUnderlineFont` zaškrtávací políčko.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#5](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#5)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#5](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#5)]  
  
6.  V jazyce C#, je nutné přidat obslužné rutiny události pro do textových polí na <xref:Microsoft.Office.Tools.Word.Document.Startup> událostí. Informace o tom, jak vytváření obslužných rutin událostí najdete v tématu [postupy: vytváření obslužných rutin událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#6)]  
  
## <a name="test-the-application"></a>Testování aplikace  
 Nyní můžete otestovat dokument k ověření, že text správně naformátován při vyberte nebo zrušte zaškrtnutí políčka.  
  
### <a name="test-your-document"></a>Testování dokumentu  
  
1.  Stiskněte klávesu **F5** ke spuštění projektu.  
  
2.  Vyberte nebo zrušte zaškrtnutí políčka.  
  
3.  Potvrďte, že text správně naformátován.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základní informace o použití zaškrtávacího políčka a formátování textu na dokumenty aplikace Word prostřednictvím kódu programu změna. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Tlačítko se používá k naplnění textové pole. Další informace najdete v tématu [návod: zobrazení textu v textovém poli v dokumentu s použitím tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md).  
  
-   Pomocí přepínačů vyberte styly grafu. Další informace najdete v tématu [návod: aktualizace grafu v dokumentu s použitím přepínačů](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md).  
  

## <a name="see-also"></a>Viz také  
 [Návody pro aplikaci Word](../vsto/walkthroughs-using-word.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Omezení ovládacích prvků Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  