---
title: 'Postupy: Změna velikosti ovládacích prvků ListObject'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- ListObject control, resizing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 98b37c91ff2d36832345f3c0ee93a98de0372060
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54869577"
---
# <a name="how-to-resize-listobject-controls"></a>Postupy: Změna velikosti ovládacích prvků ListObject
  Nastavte velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, když ho přidáte do sešitu aplikace Microsoft Office Excel; však můžete chtít změnit jeho velikost později. Například můžete chtít změnit seznam dvěma sloupci na tři sloupce.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacích prvků v době návrhu nebo za běhu v projektech na úrovni dokumentu. Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacích prvků za běhu v projektu doplňku VSTO.  
  
 Toto téma popisuje následující úkoly:  
  
- [Změna velikosti ovládacích prvků ListObject v době návrhu](#designtime)  
  
- [Změna velikosti ovládacích prvků ListObject za běhu v projektu úrovni dokumentu](#runtimedoclevel)  
  
- [Změna velikosti ovládacích prvků ListObject za běhu v projektu doplňku VSTO](#runtimeaddin)  
  
  Další informace o <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacích prvků, naleznete v tématu [ListObject – ovládací prvek](../vsto/listobject-control.md).  
  
  ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související video ukázku naleznete v tématu [postup: Přidání sloupců do seznamu objektů vázané na data za běhu? ](http://go.microsoft.com/fwlink/?LinkID=130318).  
  
##  <a name="designtime"></a> Změna velikosti ovládacího prvku ListObject v době návrhu  
 Pokud chcete změnit velikost seznamu, můžete kliknout a přetáhněte jeden z úchytů pro změnu velikosti, nebo můžete změnit jeho velikost v **změnit velikost seznamu** dialogové okno.  
  
### <a name="to-resize-a-list-by-using-the-resize-list-dialog-box"></a>Změnit velikost seznamu pomocí dialogu změnit velikost seznamu  
  
  
1.  Klikněte kamkoli do <xref:Microsoft.Office.Tools.Excel.ListObject> tabulky. **Nástroje tabulky** > **návrhu** zobrazuje kartu na pásu karet.  
  
2.  V části Vlastnosti klikněte na **změnit velikost tabulky**.  

    ![VSTO_ResizeTable](../vsto/media/vsto-resizetable.png)
  
3.  Vyberte nový rozsah dat pro tabulku.  
  
4.  Klikněte na **OK**.  
  
##  <a name="runtimedoclevel"></a> Změna velikosti ovládacího prvku ListObject za běhu v projektu úrovni dokumentu  
 Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku za běhu pomocí <xref:Microsoft.Office.Tools.Excel.ListObject.Resize%2A> metody. Tuto metodu nelze použít pro přesun <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek na nové umístění na listu. Záhlaví musí zůstat ve stejném řádku a změněnou velikostí <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek musí překrývat na původní objekt seznamu. Změněnou velikostí <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek musí obsahovat řádek záhlaví a alespoň jeden řádek data.  
  
### <a name="to-resize-a-list-object-programmatically"></a>Změnit velikost seznamu objektů prostřednictvím kódu programu  
  
1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který zahrnuje buňky **A1** prostřednictvím **B3** na `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#6)]  
  
2.  Změnit velikost, aby obsahoval buňky **A1** prostřednictvím **C5**.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#7)]  
  
##  <a name="runtimeaddin"></a> Změna velikosti objektu ListObject za běhu v projektu doplňku VSTO  
 Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek na jakékoli otevřete list za běhu. Další informace o tom, jak přidat <xref:Microsoft.Office.Tools.Excel.ListObject> řídit do listu pomocí doplňku VSTO, přečtěte si téma [jak: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
### <a name="to-resize-a-list-object-programmatically"></a>Změnit velikost seznamu objektů prostřednictvím kódu programu  
  
1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který zahrnuje buňky **A1** prostřednictvím **B3** na `Sheet1`.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#12)]
     [!code-vb[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#12)]  
  
2.  Změnit velikost, aby obsahoval buňky **A1** prostřednictvím **C5**.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#13)]
     [!code-vb[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Viz také:  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject – ovládací prvek](../vsto/listobject-control.md)   
 [Postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Postupy: Změna velikosti ovládacích prvků záložek](../vsto/how-to-resize-bookmark-controls.md)   
 [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)  
