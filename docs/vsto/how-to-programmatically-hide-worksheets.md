---
title: "Postupy: skrývání listů prostřednictvím kódu programu | Microsoft Docs"
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
- hidden worksheets
- worksheets, hiding
ms.assetid: 3208f633-137f-47f9-9c9c-2cf8e3c72096
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ef9d6e72f7d69e3b71b8ea6f6acea9021be6b2cf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-hide-worksheets"></a>Postupy: Skrývání listů prostřednictvím kódu programu
  Můžete zobrazit nebo skrýt všechny listu sešitu. Skrýt listu, použijte hostitelská položka worksheet nebo listu přistupovat pomocí kolekce listy sešitu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-the-worksheet-host-item"></a>Pomocí hostitelská položka Worksheet  
 Pokud list byl přidán v době návrhu přizpůsobení na úrovni dokumentu, použijte <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> vlastnost ke skrytí zadaný listu.  
  
#### <a name="to-hide-a-worksheet-using-a-worksheet-host-item"></a>Chcete-li skrýt na listu s použitím hostitelská položka worksheet  
  
1.  Nastavte <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> vlastnost `Sheet1` hostitele položky <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> hodnota výčtu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#25)]  
  
## <a name="using-the-sheets-collection-of-the-excel-workbook"></a>Pomocí kolekce listy sešitu aplikace Excel  
 Přístup k listů prostřednictvím aplikace Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce v následujících případech:  
  
-   Chcete skrýt list v doplňku VSTO.  
  
-   Sešit, který chcete skrýt byl vytvořen v době běhu v přizpůsobení na úrovni dokumentu.  
  
#### <a name="to-hide-a-worksheet-using-the-sheets-collection-of-the-excel-workbook"></a>Chcete-li skrýt na listu s použitím kolekce listy sešitu aplikace Excel  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A> vlastnost listu tak, aby <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> hodnota výčtu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#26)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: odstraňování listů ze sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Postupy: přesouvání listů v sešitech prostřednictvím kódu programu](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Postupy: zamykání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)  
  