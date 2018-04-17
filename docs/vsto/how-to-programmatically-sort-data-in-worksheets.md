---
title: 'Postupy: řazení dat na listech prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data sorting, worksheets
- data [Office development in Visual Studio], sorting in worksheets
- worksheets, sorting data
- sorting data, in worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4d53baac81bc3a2e583743a61635560b1486a76e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-sort-data-in-worksheets"></a>Postupy: Řazení dat na listech prostřednictvím kódu programu
  Můžete řadit data, která se nachází v oblasti v listech a seznamy za běhu. Následující kód seřadí vícesloupcového oblast s názvem `Fruits` podle data z prvního sloupce a poté podle data v druhém sloupci.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="sorting-data-in-a-document-level-customization"></a>Řazení dat v přizpůsobení na úrovni dokumentu  
  
#### <a name="to-sort-data-in-a-namedrange-control"></a>Řazení dat v ovládacím prvku NamedRange  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.NamedRange.Sort%2A> metodu <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku. Následující příklad vyžaduje <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `Fruits` na listu. Tento kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#78)]
     [!code-vb[Trin_VstcoreExcelAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#78)]  
  
 Vložte následující kód v Sheet1.vb nebo Sheet1.cs řazení dat v <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku. Kód předpokládá, že máte <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek s názvem `fruitList` na listu s názvem `Sheet1`.  
  
#### <a name="to-sort-data-in-a-listobject-control"></a>Řazení dat v ovládacím prvku ListObject  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> metodu <xref:Microsoft.Office.Tools.Excel.ListObject.Range%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.ListObject> hostování ovládacího prvku.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#79)]
     [!code-vb[Trin_VstcoreExcelAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#79)]  
  
## <a name="sorting-data-in-a-vsto-add-in"></a>Řazení dat v doplňku VSTO  
  
#### <a name="to-sort-data-in-a-native-range"></a>Řazení dat v nativní rozsahu  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> metoda nativní aplikace Excel <xref:Microsoft.Office.Interop.Excel.Range> ovládacího prvku. Následující příklad vyžaduje ovládací prvek nativní aplikace Excel s názvem `Fruits` na listu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#23](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#23](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#23)]  
  
#### <a name="to-sort-data-in-a-listobject-control"></a>Řazení dat v ovládacím prvku ListObject  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> metodu <xref:Microsoft.Office.Tools.Excel.ListObject.Range%2A> vlastnost nativní aplikace Excel <xref:Microsoft.Office.Interop.Excel.ListObject> ovládacího prvku. V následujícím příkladu se předpokládá, že máte nativní aplikace Excel <xref:Microsoft.Office.Interop.Excel.ListObject> ovládací prvek s názvem `fruitList` v aktivním listu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#24](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#24](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#24)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: programové automatické naplňování oblastí s přírůstkově se měnícími daty](../vsto/how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data.md)   
 [Postupy: odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Postupy: programové používání stylů pro oblasti sešitů](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [ListObject – ovládací prvek](../vsto/listobject-control.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  