---
title: 'Postupy: Přidání ovládacích prvků do dokumentů Office Windows Forms | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], adding
- controls [Office development in Visual Studio], Windows Forms controls
- documents [Office development in Visual Studio], Windows Forms controls
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ebd26c78e30e522b3d961d42226fc42825eb2a2d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-windows-forms-controls-to-office-documents"></a>Postupy: Přidání ovládacích prvků Windows Forms do dokumentů Office
  Windows Forms – ovládací prvky můžete přidat do aplikace Microsoft Office Excel a Microsoft Office Word dokumentů v době návrhu v projekty na úrovni dokumentu. V době běhu můžete přidat ovládací prvky v přizpůsobeních na úrovni dokumentu a v doplňcích VSTO. Například můžete přidat <xref:Microsoft.Office.Tools.Excel.Controls.ComboBox> řízení do listu, aby uživatelé můžete vybrat ze seznamu možností.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 Toto téma popisuje následující úlohy:  
  
-   [Přidání ovládacích prvků v době návrhu](#designtime)  
  
-   [Přidání ovládacích prvků za běhu v projekty na úrovni dokumentu](#runtimedoclevel)  
  
-   [Přidání ovládacích prvků za běhu v doplňcích VSTO](#runtimeaddin)  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: Přidání ovládacích prvků na plochu dokumentu za běhu?](http://go.microsoft.com/fwlink/?LinkId=132782).  
  
##  <a name="designtime"></a> Přidání ovládacích prvků v době návrhu  
 Existuje několik způsobů k přidávání ovládacích prvků Windows Forms v dokumentu v projektech na úrovni dokumentu v době návrhu.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-drag-a-windows-forms-control-to-the-document"></a>Přetáhněte ovládacího prvku Windows Forms v dokumentu  
  
1.  Vytvořit nebo otevřít projektu sešitu aplikace Excel nebo produktu project dokument aplikace Word v sadě Visual Studio tak, aby dokument v návrháři. Informace o vytváření projektů najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  V **běžné ovládací prvky** kartě **sada nástrojů**, klikněte na ovládací prvek, který chcete přidat a přetáhněte jej do dokumentu.  
  
    > [!NOTE]  
    >  Když vyberete ovládacího prvku v aplikaci Excel, uvidíte **=EMBED("WinForms.Control.Host","")** v **řádek vzorců**. Tento text je nezbytné a nesmí být odstraněna.  
  
#### <a name="to-draw-a-windows-forms-control-on-the-document"></a>K vykreslení ovládacího prvku Windows Forms v dokumentu  
  
1.  Vytvořit nebo otevřít projektu sešitu aplikace Excel nebo produktu project dokument aplikace Word v sadě Visual Studio tak, aby dokument v návrháři. Informace o vytváření projektů najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  V **běžné ovládací prvky** kartě **sada nástrojů**, klikněte na ovládací prvek, který chcete přidat.  
  
3.  V dokumentu klikněte na levý horní roh ovládacího prvku na nalezen a přetáhněte ji na místo, kde pravém dolním rohu ovládacího prvku na nalezen.  
  
     Ovládací prvek se přidá do dokumentu pomocí zadané umístění a velikost.  
  
    > [!NOTE]  
    >  Když vyberete ovládacího prvku v aplikaci Excel, uvidíte **=EMBED("WinForms.Control.Host","")** v **řádek vzorců**. Tento text je nezbytné a nesmí být odstraněna.  
  
#### <a name="to-add-a-windows-forms-control-to-the-document-by-single-clicking-the-control"></a>Přidání ovládacího prvku Windows Forms v dokumentu jedním kliknutím ovládacího prvku  
  
1.  Vytvořit nebo otevřít projektu sešitu aplikace Excel nebo produktu project dokument aplikace Word v sadě Visual Studio tak, aby dokument v návrháři. Informace o vytváření projektů najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  V **běžné ovládací prvky** kartě **sada nástrojů**, klikněte na ovládací prvek, který chcete přidat  
  
3.  Jeden dokument, klikněte na tlačítko, které chcete přidat ovládací prvek.  
  
     Ovládací prvek se přidá do dokumentu s výchozí velikostí.  
  
    > [!NOTE]  
    >  Když vyberete ovládacího prvku v aplikaci Excel, uvidíte **=EMBED("WinForms.Control.Host","")** v **řádek vzorců**. Tento text je nezbytné a nesmí být odstraněna.  
  
#### <a name="to-add-a-windows-forms-control-to-the-document-by-double-clicking-the-control"></a>Přidání ovládacího prvku Windows Forms v dokumentu poklepáním na ovládací prvek  
  
1.  Vytvořit nebo otevřít projektu sešitu aplikace Excel nebo produktu project dokument aplikace Word v sadě Visual Studio tak, aby dokument v návrháři. Informace o vytváření projektů najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  V **běžné ovládací prvky** kartě **sada nástrojů**, dvakrát klikněte na ovládací prvek, který chcete přidat.  
  
     Ovládací prvek se přidá do dokumentu v centru dokumentu nebo aktivního podokna.  
  
    > [!NOTE]  
    >  Když vyberete ovládacího prvku v aplikaci Excel, uvidíte **=EMBED("WinForms.Control.Host","")** v **řádek vzorců**. Tento text je nezbytné a nesmí být odstraněna.  
  
#### <a name="to-add-a-windows-forms-control-to-the-document-by-pressing-the-enter-key"></a>Přidání ovládacího prvku Windows Forms v dokumentu po stisknutí klávesy ENTER  
  
1.  Vytvořit nebo otevřít projektu sešitu aplikace Excel nebo produktu project dokument aplikace Word v sadě Visual Studio tak, aby dokument v návrháři. Informace o vytváření projektů najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  V **běžné ovládací prvky** kartě **sada nástrojů**, klikněte na ovládací prvek, který chcete přidat a stiskněte klávesu ENTER.  
  
     Ovládací prvek se přidá do dokumentu v centru dokumentu nebo aktivního podokna.  
  
    > [!NOTE]  
    >  Když vyberete ovládacího prvku v aplikaci Excel, uvidíte **=EMBED("WinForms.Control.Host","")** v **řádek vzorců**. Tento text je nezbytné a nesmí být odstraněna.  
  
##  <a name="runtimedoclevel"></a> Přidání ovládacích prvků za běhu v projekty na úrovni dokumentu  
 Ovládací prvky Windows Forms můžete prostřednictvím kódu programu přidat do dokumentu za běhu. V aplikaci Word, použít metody <xref:Microsoft.Office.Tools.Word.DocumentBase.Controls%2A> vlastnost `ThisDocument` třídy. V aplikaci Excel pomocí metody <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Controls%2A> vlastnost `Sheet` *n* třídy. Každá metoda má několik přetížení, které vám umožní zadat umístění ovládacího prvku různými způsoby.  
  
 Když přidáte ovládacího prvku Windows Forms do dokumentu za běhu, ovládacího prvku neuchovává jako trvalý v dokumentu při zavření v dokumentu. Ovládací prvek můžete znovu při příštím otevření dokumentu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-windows-forms-control-at-run-time"></a>Přidání ovládacího prvku Windows Forms v době běhu  
  
1.  Použít metodu, která má název přidat\<*třídu ovládacího prvku*> (kde *třídu ovládacího prvku* je název třídy ovládacího prvku Windows Forms, který chcete přidat, jako například <xref:Microsoft.Office.Tools.Word.ControlExtensions.AddButton%2A>).  
  
     Následující příklad kódu ukazuje, jak přidat <xref:Microsoft.Office.Tools.Excel.Controls.Button> do buňky **C5** z `Sheet1` v projektech na úrovni dokumentu pro Excel.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#4](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#4)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#4)]  
  
##  <a name="runtimeaddin"></a> Přidání ovládacích prvků za běhu v doplňcích VSTO  
 Windows Forms – ovládací prvky můžete přidat prostřednictvím kódu programu otevřete dokumentu za běhu. Generovat položku hostitele, který je založen na Otevřít dokument nebo listu. Potom v aplikaci Word, použít metody <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> vlastnost novou položku hostitele. V aplikaci Excel pomocí metody <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> vlastnost novou položku hostitele. Každá metoda má několik přetížení, které vám umožní zadat umístění ovládacího prvku různými způsoby.  
  
 Když přidáte ovládacího prvku Windows Forms do dokumentu za běhu, ovládacího prvku neuchovává jako trvalý v dokumentu při zavření v dokumentu. Ovládací prvek můžete znovu při příštím otevření dokumentu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Další informace o generování hostitelských položkách v projekty doplňku VSTO v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
#### <a name="to-add-a-windows-forms-control-at-run-time"></a>Přidání ovládacího prvku Windows Forms v době běhu  
  
1.  Použít metodu, která má název přidat\<*třídu ovládacího prvku*> (kde *třídu ovládacího prvku* je název třídy ovládacího prvku Windows Forms, který chcete přidat, jako například <xref:Microsoft.Office.Tools.Word.ControlExtensions.AddButton%2A>).  
  
    > [!NOTE]  
    >  V doplňku VSTO projektů cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte přidat odkaz na sestavení Microsoft.Office.Tools.Excel.v4.0.Utilities.dll nebo Microsoft.Office.Tools.Word.v4.0.Utilities.dll, než budete moct přidat\< *třídu ovládacího prvku*> metody.  
  
     Následující příklad kódu ukazuje, jak přidat <xref:Microsoft.Office.Tools.Word.Controls.Button> na prvním odstavci aktivního dokumentu pomocí doplňku VSTO pro Word.  
  
     [!code-vb[Trin_WordAddInDynamicControls#7](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#7)]
     [!code-csharp[Trin_WordAddInDynamicControls#7](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#7)]  
  
## <a name="see-also"></a>Viz také  
 [Windows Forms – ovládací prvky na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Postupy: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  