---
title: 'Návod: Změna formátování dokumentů s použitím ovládacích prvků CheckBox'
ms.date: 02/02/2017
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f1b4137a6f024a9a4f752af7c9e19fd946a1c282
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59653889"
---
# <a name="walkthrough-change-document-formatting-using-checkbox-controls"></a>Návod: Změna formátování dokumentů s použitím ovládacích prvků CheckBox
  Tento návod ukazuje, jak změnit formátování textu pomocí ovládacích prvků Windows Forms v přizpůsobení úrovni dokumentu pro aplikaci Microsoft Office Word.

 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]

 Tento návod znázorňuje následující úlohy:

- Přidání textu a ovládací prvek v dokumentu v projektu úrovni dokumentu v době návrhu.

- Formátování textu, pokud je vybrána možnost.

  Výsledek jako úplnou vzorovou najdete v ukázce ovládací prvky aplikace Word v [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Požadavky
 K dokončení tohoto návodu budete potřebovat následující komponenty:

-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].

## <a name="create-the-project"></a>Vytvoření projektu
 Prvním krokem je vytvoření projektu dokumentu aplikace Word.

### <a name="create-a-new-project"></a>Vytvoření nového projektu

1.  Vytvoření projektu Wordového dokumentu s názvem **Moje formátování aplikace Word**. V průvodci vyberte **vytvoříte nový textový dokument**.

     Další informace najdete v tématu [jak: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).

     Visual Studio otevře nový Wordový dokument v návrháři a přidá **Moje formátování aplikace Word** projektu **Průzkumníka řešení**.

## <a name="add-text-and-controls-to-the-word-document"></a>Přidání textu a ovládacích prvků do dokumentu aplikace Word
 V tomto návodu, přidejte tři políčka a text v <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku na dokument aplikace Word. Zaškrtávací políčka zobrazíte možnosti pro uživatele pro formátování textu.

### <a name="add-three-check-boxes"></a>Přidejte tři políčka

1.  Ověřte, že dokument je otevřen v návrháři aplikace Visual Studio.

2.  Z **běžné ovládací prvky** karty **nástrojů**, přetáhněte první <xref:Microsoft.Office.Tools.Word.Controls.CheckBox> ovládací prvek v dokumentu.

3.  V **vlastnosti** okně změnit následující vlastnosti.

    |Vlastnost|Hodnota|
    |--------------|-----------|
    |**Název**|**applyBoldFont**|
    |**Text**|**Tučné**|

4.  Stisknutím klávesy **Enter** přesuňte kurzor pod první zaškrtávací políčko.

5.  Přidejte druhý zaškrtávací políčko níže dokumentu `ApplyBoldFont` zaškrtněte políčko a změnit následující vlastnosti.

    |Vlastnost|Value|
    |--------------|-----------|
    |**Název**|**applyItalicFont**|
    |**Text**|**Kurzíva**|

6.  Stisknutím klávesy **Enter** přesuňte kurzor pod zaškrtávacím políčkem druhý.

7.  Přidat třetí zaškrtávací políčko níže dokumentu `ApplyItalicFont` zaškrtněte políčko a změnit následující vlastnosti.

    |Vlastnost|Value|
    |--------------|-----------|
    |**Název**|**applyUnderlineFont**|
    |**Text**|**Podtržení**|

### <a name="add-text-and-a-bookmark-control"></a>Přidání textu a ovládací prvek Bookmark

1. Přesuňte kurzor pod ovládací prvky zaškrtávacích políček a zadejte následující text:

    **Klikněte na zaškrtávací políčko, chcete-li změnit formátování tento text.**

2. Z **ovládací prvky aplikace Word** karty **nástrojů**, přetáhněte <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek v dokumentu.

    **Přidejte ovládací prvek Bookmark** zobrazí se dialogové okno.

3. Vyberte text, který jste přidali do dokumentu a klikněte na tlačítko **OK**.

    A <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek s názvem **Bookmark1** se přidá do vybraného textu v dokumentu.

4. V **vlastnosti** okna, změňte hodnotu **(název)** vlastnost **fontText.**

   Dále napište kód k formátování textu, když je zaškrtávací políčko zaškrtnuto nebo vymazat.

## <a name="format-the-text-when-a-check-box-is-checked-or-cleared"></a>Pokud zaškrtávací políčko je zaškrtnuté políčko nebo Vymazat formátování textu
 Když uživatel vybere možnost formátování, změny formátu textu v dokumentu.

### <a name="change-formatting-when-a-check-box-is-selected"></a>Změna formátování, pokud je zaškrtnuto zaškrtávací políčko

1.  Klikněte pravým tlačítkem na `ThisDocument` v **Průzkumníka řešení**a potom klikněte na tlačítko **zobrazit kód** v místní nabídce.

2.  Pro C# pouze, přidejte následující konstanty **ThisDocument** třídy.

     [!code-csharp[Trin_VstcoreProgrammingControlsWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#2)]

3.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužná rutina události `applyBoldFont` zaškrtávací políčko.

     [!code-vb[Trin_VstcoreProgrammingControlsWord#3](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#3)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#3](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#3)]

4.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužná rutina události `applyItalicFont` zaškrtávací políčko.

     [!code-vb[Trin_VstcoreProgrammingControlsWord#4](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#4)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#4](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#4)]

5.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužná rutina události `applyUnderlineFont` zaškrtávací políčko.

     [!code-vb[Trin_VstcoreProgrammingControlsWord#5](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#5)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#5](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#5)]

6.  V C#, je nutné přidat obslužné rutiny událostí pro textová pole <xref:Microsoft.Office.Tools.Word.Document.Startup> událostí. Informace o tom, jak vytváření obslužných rutin událostí, naleznete v tématu [jak: Vytváření obslužných rutin událostí v projektech pro systém Office](../vsto/how-to-create-event-handlers-in-office-projects.md).

     [!code-csharp[Trin_VstcoreProgrammingControlsWord#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#6)]

## <a name="test-the-application"></a>Testování aplikace
 Teď můžete otestovat váš dokument k ověření, že text je správný při zaškrtněte nebo zrušte zaškrtnutí políčka.

### <a name="test-your-document"></a>Testovat váš dokument

1.  Stisknutím klávesy **F5** ke spuštění projektu.

2.  Vyberte nebo zrušte zaškrtnutí políčka.

3.  Potvrďte, že je správně formátovaný text.

## <a name="next-steps"></a>Další kroky
 Tento návod ukazuje základy používání zaškrtávacích políček a formátování textu na dokumenty aplikace Word prostřednictvím kódu programu změna. Tady jsou některé úlohy, které by mohl pocházet Další:

-   Tlačítko se používá k naplnění textové pole. Další informace najdete v tématu [názorný postup: Zobrazení textu v textovém poli v dokumentu s použitím tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md).

-   Pomocí přepínačů vyberte styly grafu. Další informace najdete v tématu [názorný postup: Aktualizace grafu v dokumentu s použitím přepínačů](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md).

## <a name="see-also"></a>Viz také:
- [Návody pro aplikaci Word](../vsto/walkthroughs-using-word.md)
- [Ukázky vývoje pro Office a názorné postupy](../vsto/office-development-samples-and-walkthroughs.md)
- [Namedrange – ovládací prvek](../vsto/namedrange-control.md)
- [Omezení ovládacích prvků Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)
