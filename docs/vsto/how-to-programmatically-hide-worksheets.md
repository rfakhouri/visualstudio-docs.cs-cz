---
title: 'Postupy: Skrývání listů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden worksheets
- worksheets, hiding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 188c7fbf16002086a4968b91c068cd67357292de
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870490"
---
# <a name="how-to-programmatically-hide-worksheets"></a>Postupy: Skrývání listů prostřednictvím kódu programu
  Můžete zobrazit nebo skrýt všechny listu v sešitu. Chcete-li skrýt listu, pomocí hostitelská položka worksheet nebo přistupovat ke listu pomocí kolekce listů sešitu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="use-the-worksheet-host-item"></a>Použití hostitelská položka worksheet  
 Pokud v době návrhu v přizpůsobení na úrovni dokumentu byla přidána do listu, použijte <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> vlastnost skrýt zadaného listu.  
  
### <a name="to-hide-a-worksheet-using-a-worksheet-host-item"></a>Chcete-li skrýt na listu s použitím hostitelská položka worksheet  
  
1.  Nastavte <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> vlastnost `Sheet1` položka hostitele na <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> hodnota výčtu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#25)]  
  
## <a name="use-the-sheets-collection-of-the-excel-workbook"></a>Kolekce stylů Excelový sešit  
 Přístup k listů prostřednictvím aplikace Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce v následujících případech:  
  
-   Chcete skrýt sešitu v doplňku VSTO.  
  
-   List, který chcete skrýt byl vytvořen v době běhu v přizpůsobení na úrovni dokumentu.  
  
### <a name="to-hide-a-worksheet-using-the-sheets-collection-of-the-excel-workbook"></a>Chcete-li skrýt na listu s použitím kolekci seznamů sešitu aplikace Excel  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A> vlastnost list <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> hodnota výčtu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#26)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: Odstraňování listů ze sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Postupy: Přesouvání listů v sešitech prostřednictvím kódu programu](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Postupy: Zamykání listů](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)  
