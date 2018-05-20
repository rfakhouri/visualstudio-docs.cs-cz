---
title: 'Postupy: Přidání ovládacích prvků ListObject do listů'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ListObject control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3ab95f3929b556f6ece0d3b44ee12bad6f21a361
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-add-listobject-controls-to-worksheets"></a>Postupy: Přidání ovládacích prvků ListObject do listů
  Můžete přidat <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacích prvků na list aplikace Microsoft Office Excel v době návrhu a v době běhu projekty na úrovni dokumentu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Můžete také přidat <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvky v době běhu projekty doplňku VSTO.  
  
 Toto téma popisuje následující úlohy:  
  
-   [Přidání ovládacích prvků ListObject v době návrhu](#designtime)  
  
-   [Přidání ovládacích prvků ListObject za běhu v projektech na úrovni dokumentu](#runtimedoclevel)  
  
-   [Přidání ovládacích prvků ListObject za běhu v projektu doplňku VSTO](#runtimeaddin)  
  
 Další informace o <xref:Microsoft.Office.Tools.Excel.ListObject> najdete v části ovládací prvky, [ListObject – ovládací prvek](../vsto/listobject-control.md).  
  
##  <a name="designtime"></a> Přidání ovládacích prvků ListObject v době návrhu  
 Existuje několik způsobů, jak přidat <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacích prvků na list v projektech na úrovni dokumentu v době návrhu: Z aplikace Excel v sadě Visual Studio **sada nástrojů**a z **zdroje dat** okno.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-use-the-ribbon-in-excel"></a>Používání pásu karet v aplikaci Excel  
  
1.  Na **vložit** ve **tabulky** klikněte na možnost **tabulky**.  
  
2.  Vybrat buňku nebo buňky, které chcete zahrnout do seznamu a klikněte na tlačítko **OK**.  
  
#### <a name="to-use-the-toolbox"></a>Použití panelu  
  
1.  Z **ovládací prvky aplikace Excel** kartě **sada nástrojů**, přetáhněte ji <xref:Microsoft.Office.Tools.Excel.ListObject> do listu.  
  
     **Přidat ovládací prvek ListObject** zobrazí se dialogové okno.  
  
2.  Vybrat buňku nebo buňky, které chcete zahrnout do seznamu a klikněte na tlačítko **OK**.  
  
     Pokud nechcete, aby výchozí název, můžete změnit název v **vlastnosti** okno.  
  
#### <a name="to-use-the-data-sources-window"></a>Použití okna zdroje dat  
  
1.  Otevřete **zdroje dat** okno a vytvořte zdroj dat pro váš projekt. Další informace najdete v tématu [přidat nová připojení](../data-tools/add-new-connections.md).  
  
2.  Přetáhněte tabulku ze **zdroje dat** okna do listu.  
  
     Vázané na data <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek je přidán do listu. Další informace najdete v tématu [datová vazba a systém Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
##  <a name="runtimedoclevel"></a> Přidání ovládacích prvků ListObject za běhu v projektech na úrovni dokumentu  
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.ListObject> řízení dynamicky za běhu. To umožňuje vytvářet hostitelské ovládací prvky v reakci na události. Dynamicky vytvořený list – objekty nejsou trvalé do listu jako umisťování ovládacích prvků při uzavření listu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-listobject-control-to-a-worksheet-programmatically"></a>Přidání ovládacího prvku ListObject do listu prostřednictvím kódu programu  
  
1.  V <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> obslužné rutiny události z `Sheet1`, vložte následující kód k přidání <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku do buněk **A1** prostřednictvím **A4**.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreHostControlsExcel#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#2)]  
  
##  <a name="runtimeaddin"></a> Přidání ovládacích prvků ListObject za běhu v projektu doplňku VSTO  
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.ListObject> řízení prostřednictvím kódu programu k žádné otevřete sešit v projektu doplňku VSTO. Dynamicky vytvořený list – objekty nejsou trvalé do listu jako umisťování ovládacích prvků, když je na listu uloženy a zavřeny. Další informace najdete v tématu [dokumentů rozšířit aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
#### <a name="to-add-a-listobject-control-to-a-worksheet-programmatically"></a>Přidání ovládacího prvku ListObject do listu prostřednictvím kódu programu  
  
1.  Následující kód vytvoří hostitelská položka worksheet, která je založena na otevřete list a pak přidá <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku do buněk **A1** prostřednictvím **A4**.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#8](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#8)]
     [!code-vb[Trin_Excel_Dynamic_Controls#8](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#8)]  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [ListObject – ovládací prvek](../vsto/listobject-control.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Postupy: Změna velikosti ovládacích prvků ListObject](../vsto/how-to-resize-listobject-controls.md)   
 [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  