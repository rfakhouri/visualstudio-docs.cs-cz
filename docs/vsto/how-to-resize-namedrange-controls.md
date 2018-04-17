---
title: 'Postupy: Změna velikosti ovládacích prvků NamedRange | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- NamedRange control, resizing
- ranges, resizing in Excel
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6d475f9140607ba0ae7415a60a9589aef11a44a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-resize-namedrange-controls"></a>Postupy: Změna velikosti ovládacích prvků NamedRange
  Můžete nastavit velikost <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení, pokud ho přidáte do dokumentu aplikace Microsoft Office Excel; však můžete chtít jeho velikost na později.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 V době návrhu nebo za běhu v projekty na úrovni dokumentu, můžete změnit velikost pojmenované oblasti. Můžete taky změnit velikost pojmenované oblasti za běhu v úrovni aplikace VSTO doplňků.  
  
 Toto téma popisuje následující úlohy:  
  
-   [Změna velikosti ovládacích prvků NamedRange v době návrhu](#designtime)  
  
-   [Změna velikosti ovládacích prvků NamedRange za běhu v projektech na úrovni dokumentu](#runtimedoclevel)  
  
-   [Změna velikosti ovládacích prvků NamedRange za běhu v projektu doplňku VSTO](#runtimeaddin)  
  
##  <a name="designtime"></a> Změna velikosti ovládacích prvků NamedRange v době návrhu  
 Pojmenované oblasti můžete změnit velikost, opětovná definice v jeho velikost **definovat název** dialogové okno.  
  
#### <a name="to-resize-a-named-range-by-using-the-define-name-dialog-box"></a>Ke změně velikosti pojmenované oblasti pomocí dialogového okna zadejte název  
  
1.  Klikněte pravým tlačítkem myši <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku.  
  
2.  Klikněte na tlačítko **spravovat pojmenované rozsahy** v místní nabídce.  
  
     **Definovat název** zobrazí se dialogové okno.  
  
3.  Vyberte pojmenované oblasti, kterou chcete změnit.  
  
4.  Vymazat **odkazuje na** pole.  
  
5.  Vyberte buňky, které chcete použít k definování velikost pojmenované oblasti.  
  
6.  Click **OK**.  
  
##  <a name="runtimedoclevel"></a> Změna velikosti ovládacích prvků NamedRange za běhu v projektech na úrovni dokumentu  
 Můžete změnit velikost pojmenované oblasti programově pomocí <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> vlastnost.  
  
> [!NOTE]  
>  V **vlastnosti** okně <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> vlastnost označena jako jen pro čtení.  
  
#### <a name="to-resize-a-named-range-programmatically"></a>Ke změně velikosti pojmenované oblasti prostřednictvím kódu programu  
  
1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek v buňce **A1** z `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#4)]  
  
2.  Změnit velikost pojmenované oblasti zahrnout buňky **B1**.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#5)]  
  
##  <a name="runtimeaddin"></a> Změna velikosti ovládacích prvků NamedRange za běhu v projektu doplňku VSTO  
 Můžete změnit velikost <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek v jakékoli otevřete list za běhu. Další informace o tom, jak přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> řídit do listu pomocí doplňku VSTO najdete v tématu [postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
#### <a name="to-resize-a-named-range-programmatically"></a>Ke změně velikosti pojmenované oblasti prostřednictvím kódu programu  
  
1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek v buňce **A1** z `Sheet1`.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#10)]
     [!code-vb[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#10)]  
  
2.  Změnit velikost pojmenované oblasti zahrnout buňky **B1**.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#11)]
     [!code-vb[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#11)]  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Postupy: Změna velikosti ovládacích prvků záložek](../vsto/how-to-resize-bookmark-controls.md)   
 [Postupy: Změna velikosti ovládacích prvků ListObject](../vsto/how-to-resize-listobject-controls.md)  
  
  