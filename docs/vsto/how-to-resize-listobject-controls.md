---
title: "Postupy: Změna velikosti ovládacích prvků ListObject | Microsoft Docs"
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
- controls [Office development in Visual Studio], resizing
- ListObject control, resizing
ms.assetid: a4c7dceb-7b55-447e-9b88-c3596a2fc361
caps.latest.revision: "50"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 96616338d0fd26e31ac0cc67e66d4dc35d03fdda
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-listobject-controls"></a>Postupy: Změna velikosti ovládacích prvků ListObject
  Nastavení velikosti <xref:Microsoft.Office.Tools.Excel.ListObject> řízení, pokud ho přidáte do sešitu aplikace Microsoft Office Excel; však můžete chtít jeho velikost na později. Můžete například změnit seznam dvou sloupců na tři sloupce.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvky v době návrhu nebo za běhu v projekty na úrovni dokumentu. Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacích prvků za běhu v projektu doplňku VSTO.  
  
 Toto téma popisuje následující úlohy:  
  
-   [Změna velikosti ovládacích prvků ListObject v době návrhu](#designtime)  
  
-   [Změna velikosti ovládacích prvků ListObject za běhu v projektech na úrovni dokumentu](#runtimedoclevel)  
  
-   [Změna velikosti ovládacích prvků ListObject za běhu v projektu doplňku VSTO](#runtimeaddin)  
  
 Další informace o <xref:Microsoft.Office.Tools.Excel.ListObject> najdete v části ovládací prvky, [ListObject – ovládací prvek](../vsto/listobject-control.md).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: Přidat sloupce do seznamu objekt vázané na Data v době běhu?](http://go.microsoft.com/fwlink/?LinkID=130318).  
  
##  <a name="designtime"></a>Změna velikosti ovládacího prvku ListObject v době návrhu  
 Ke změně velikosti seznamu, můžete klikněte na tlačítko a přetáhněte jeden úchyt, nebo můžete změnit její velikost v definici **změnit velikost seznamu** dialogové okno.  
  
#### <a name="to-resize-a-list-by-using-the-resize-list-dialog-box"></a>Ke změně velikosti seznamu pomocí dialogu změnit velikost seznamu  
  
  
1.  Klikněte kamkoli do <xref:Microsoft.Office.Tools.Excel.ListObject> tabulky. **Nástroje tabulky, návrh** se zobrazí karta na pásu karet.  
  
2.  V části vlastnosti, klikněte na **změnit velikost tabulky**.  

    ![VSTO_ResizeTable](../vsto/media/vsto-resizetable.png)
  
3.  Vyberte nový rozsah dat pro tabulku.  
  
4.  Click **OK**.  
  
##  <a name="runtimedoclevel"></a>Změna velikosti ovládacího prvku ListObject za běhu v projektech na úrovni dokumentu  
 Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku za běhu pomocí <xref:Microsoft.Office.Tools.Excel.ListObject.Resize%2A> metoda. Pomocí této metody nelze přesunout <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku do nového umístění v listu. Záhlaví musí zůstat ve stejném řádku a změněnou velikostí <xref:Microsoft.Office.Tools.Excel.ListObject> řízení musí překrývat původní objekt seznamu. Změněnou <xref:Microsoft.Office.Tools.Excel.ListObject> řízení musí obsahovat řádek záhlaví a alespoň jeden řádek dat.  
  
#### <a name="to-resize-a-list-object-programmatically"></a>Ke změně velikosti objekt seznamu prostřednictvím kódu programu  
  
1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který zahrnuje buňky **A1** prostřednictvím **B3** na `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#6)]  
  
2.  Změnit velikost, aby obsahoval buněk **A1** prostřednictvím **C5**.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#7)]  
  
##  <a name="runtimeaddin"></a>Změna velikosti ListObject za běhu v projektu doplňku VSTO  
 Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek v jakékoli otevřete list za běhu. Další informace o tom, jak přidat <xref:Microsoft.Office.Tools.Excel.ListObject> řídit do listu pomocí doplňku VSTO najdete v tématu [postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
#### <a name="to-resize-a-list-object-programmatically"></a>Ke změně velikosti objekt seznamu prostřednictvím kódu programu  
  
1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který zahrnuje buňky **A1** prostřednictvím **B3** na `Sheet1`.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#12)]
     [!code-vb[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#12)]  
  
2.  Změnit velikost, aby obsahoval buněk **A1** prostřednictvím **C5**.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#13)]
     [!code-vb[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject – ovládací prvek](../vsto/listobject-control.md)   
 [Postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Postupy: Změna velikosti ovládacích prvků záložek](../vsto/how-to-resize-bookmark-controls.md)   
 [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)  
  
  