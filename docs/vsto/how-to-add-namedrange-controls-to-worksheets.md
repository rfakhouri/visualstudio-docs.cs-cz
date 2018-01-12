---
title: "Postupy: Přidání ovládacích prvků NamedRange do listů | Microsoft Docs"
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
- ranges, adding to worksheets
- NamedRange control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: ef0ec1846a4ef75200fa6d37f137ca1ab1d70f48
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-namedrange-controls-to-worksheets"></a>Postupy: Přidání ovládacích prvků NamedRange do listů
  Můžete přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacích prvků na list aplikace Microsoft Office Excel v době návrhu a za běhu v projekty na úrovni dokumentu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Můžete také přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacích prvků za běhu v projekty doplňku VSTO.  
  
 Toto téma popisuje následující úlohy:  
  
-   [Přidání ovládacích prvků NamedRange v době návrhu](#designtime)  
  
-   [Přidání ovládacích prvků NamedRange za běhu v projektech na úrovni dokumentu](#runtimedoclevel)  
  
-   [Přidání ovládacích prvků NamedRange za běhu v projektu doplňku VSTO](#runtimeaddin)  
  
 Další informace o <xref:Microsoft.Office.Tools.Excel.NamedRange> najdete v části ovládací prvky, [NamedRange – ovládací prvek](../vsto/namedrange-control.md).  
  
##  <a name="designtime"></a>Přidání ovládacích prvků NamedRange v době návrhu  
 Existuje několik způsobů, jak přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacích prvků na list v projektech na úrovni dokumentu v době návrhu: z aplikace Excel v sadě Visual Studio **sada nástrojů**a z **zdroje dat** okno.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-name-box-in-excel"></a>Přidání ovládacího prvku NamedRange do listu pomocí pole název v aplikaci Excel  
  
1.  Vyberte buňku nebo buňky, které chcete zahrnout do pojmenované oblasti.  
  
2.  V **pole název**, zadejte název pro rozsah a stiskněte klávesu ENTER.  
  
     **Pole název** nachází vedle řádku vzorců, nad sloupec **A** listu.  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-toolbox"></a>Přidání ovládacího prvku NamedRange do listu pomocí sady nástrojů  
  
1.  Otevřete **sada nástrojů** a klikněte na tlačítko **ovládací prvky aplikace Excel** kartě.  
  
2.  Klikněte na tlačítko <xref:Microsoft.Office.Tools.Excel.NamedRange> a přetáhněte ji do listu.  
  
     **Přidat pojmenovaný rozsah** zobrazí se dialogové okno.  
  
3.  Vyberte buňku nebo buňky, které chcete zahrnout do pojmenované oblasti.  
  
4.  Click **OK**.  
  
     Pokud nechcete, aby výchozí název, který je přiřazen k ovládacímu prvku, můžete změnit název v **vlastnosti** okno.  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-data-sources-window"></a>Přidání ovládacího prvku NamedRange do listu pomocí okna zdroje dat  
  
1.  Otevřete **zdroje dat** okno a vytvořte zdroj dat pro váš projekt. Další informace najdete v tématu [přidat nová připojení](../data-tools/add-new-connections.md).  
  
2.  Přetáhněte jediné pole z **zdroje dat** okna do listu.  
  
     Vázané na data <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek je přidán do listu. Další informace najdete v tématu [datové vazby a rozhraní Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
##  <a name="runtimedoclevel"></a>Přidání ovládacích prvků NamedRange za běhu v projektech na úrovni dokumentu  
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení prostřednictvím kódu programu na list za běhu. To umožňuje vytvářet hostitelské ovládací prvky v reakci na události. Dynamicky vytvořený pojmenované oblasti nejsou trvalé do listu jako umisťování ovládacích prvků při uzavření listu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-programmatically"></a>Přidání ovládacího prvku NamedRange do listu prostřednictvím kódu programu  
  
1.  V <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> obslužné rutiny události z `Sheet1`, vložte následující kód k přidání <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do buňky **A1** a nastavit jeho <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnosti`Hello world!`  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreHostControlsExcel#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#3)]  
  
##  <a name="runtimeaddin"></a>Přidání ovládacích prvků NamedRange za běhu v projektu doplňku VSTO  
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení prostřednictvím kódu programu k žádné otevřete sešit v projektu doplňku VSTO. Dynamicky vytvořený pojmenované oblasti nejsou trvalé do listu jako umisťování ovládacích prvků při uzavření listu. Další informace najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-programmatically"></a>Přidání ovládacího prvku NamedRange do listu prostřednictvím kódu programu  
  
1.  Hostitelská položka worksheet, která je založena na otevřete list a potom přidá generuje následující kód <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do buňky **A1** a nastaví její <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost `Hello world`.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#7](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#7)]
     [!code-vb[Trin_Excel_Dynamic_Controls#7](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  