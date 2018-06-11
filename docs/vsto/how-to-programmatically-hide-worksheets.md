---
title: 'Postupy: skrývání listů prostřednictvím kódu programu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden worksheets
- worksheets, hiding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b17076b60a6b7d486135f9e7a79e69b952a8639c
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257131"
---
# <a name="how-to-programmatically-hide-worksheets"></a>Postupy: skrývání listů prostřednictvím kódu programu
  Můžete zobrazit nebo skrýt všechny listu sešitu. Skrýt listu, použijte hostitelská položka worksheet nebo listu přistupovat pomocí kolekce listy sešitu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="use-the-worksheet-host-item"></a>Použití hostitelská položka worksheet  
 Pokud list byl přidán v době návrhu přizpůsobení na úrovni dokumentu, použijte <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> vlastnost ke skrytí zadaný listu.  
  
### <a name="to-hide-a-worksheet-using-a-worksheet-host-item"></a>Chcete-li skrýt na listu s použitím hostitelská položka worksheet  
  
1.  Nastavte <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> vlastnost `Sheet1` hostitele položky <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> hodnota výčtu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#25)]  
  
## <a name="use-the-sheets-collection-of-the-excel-workbook"></a>Použít kolekci listy sešitu aplikace Excel  
 Přístup k listů prostřednictvím aplikace Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce v následujících případech:  
  
-   Chcete skrýt list v doplňku VSTO.  
  
-   Sešit, který chcete skrýt byl vytvořen v době běhu v přizpůsobení na úrovni dokumentu.  
  
### <a name="to-hide-a-worksheet-using-the-sheets-collection-of-the-excel-workbook"></a>Chcete-li skrýt na listu s použitím kolekce listy sešitu aplikace Excel  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A> vlastnost listu tak, aby <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> hodnota výčtu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#26)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: odstraňování listů ze sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Postupy: přesouvání listů v sešitech prostřednictvím kódu programu](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Postupy: zamykání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)  
  