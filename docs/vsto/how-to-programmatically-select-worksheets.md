---
title: "Postupy: výběr listů prostřednictvím kódu programu | Microsoft Docs"
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
- worksheets, selecting
- Excel projects, selecting worksheets
ms.assetid: 9e7cdb11-e825-4c9f-abcd-d46fd20dc5e0
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: dd84ad38955620ad09ab9fab5fc178241e682948
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-select-worksheets"></a>Postupy: Výběr listů prostřednictvím kódu programu
  <xref:Microsoft.Office.Tools.Excel.Worksheet.Select%2A> Metoda vybere zadaný objekt, který přesune výběr uživatele do nového objektu. Použití <xref:Microsoft.Office.Tools.Excel.Worksheet.Activate%2A> metoda, pokud chcete, aby fokus na objekt beze změny výběru uživatele.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Pokud chcete vybrat existující list v doplňku VSTO nebo pokud list byl vytvořen v době běhu v přizpůsobení na úrovni dokumentu, je nutné přejít pomocí aplikace Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce sešitu aplikace Excel; jinak, dostanete <xref:Microsoft.Office.Tools.Excel.Worksheet>hostitelská položka přímo.  
  
## <a name="using-the-worksheet-host-item"></a>Pomocí hostitelská položka Worksheet  
 V přizpůsobení na úrovni dokumentu, přidejte následující kód do **Sheet1.vb** nebo **Sheet1.cs**.  
  
#### <a name="to-select-the-first-worksheet-in-a-workbook-using-a-host-item"></a>Vyberte první listu v pomocí hostitelská položka sešitu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.Select%2A> metodu `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#19](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomation#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#19)]  
  
## <a name="using-the-sheets-collection-of-the-excel-workbook"></a>Pomocí kolekce listy sešitu aplikace Excel  
 Přístup k sešitu aplikace Excel pomocí <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce.  
  
#### <a name="to-select-the-first-worksheet-in-a-workbook-using-the-sheets-collection-of-the-excel-workbook"></a>Vyberte první listu v sešitu pomocí kolekce listy sešitu aplikace Excel  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel.Sheets.Select%2A> metodu <xref:Microsoft.Office.Interop.Excel.Sheets> kolekci vyberte první list v aktivním sešitu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#20](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomation#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#20)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: tisk listů prostřednictvím kódu programu](../vsto/how-to-programmatically-print-worksheets.md)   
 [Postupy: odstraňování listů ze sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Postupy: skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Postupy: zamykání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)  
  
  