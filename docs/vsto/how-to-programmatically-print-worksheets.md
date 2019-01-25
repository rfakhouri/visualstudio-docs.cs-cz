---
title: 'Postupy: Tisk listů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- printing [Office development in Visual Studio], worksheets
- worksheets, printing
- print preview, worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e76b53488f1375606980e504bf94dae6343ff267
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863419"
---
# <a name="how-to-programmatically-print-worksheets"></a>Postupy: Tisk listů prostřednictvím kódu programu
  Můžete vytisknout libovolného listu v sešitu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="print-a-worksheet-in-a-document-level-customization"></a>Vytisknout list v přizpůsobení na úrovni dokumentu  
  
### <a name="to-print-a-worksheet"></a>Chcete-li vytisknout list  
  
1. Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintOut%2A> metoda `Sheet1`, požádat o dvě kopie a náhled před tiskem dokumentu.  
  
    [!code-csharp[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#22)]
    [!code-vb[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#22)]  
  
   <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> Metoda vám umožňuje zobrazit zadaný objekt v **Náhled** okna. Následující kód předpokládá, že máte <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt s názvem `Sheet1`.  
  
### <a name="to-preview-a-page-before-printing"></a>Náhled stránky před tiskem  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> metoda listu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#23)]  
  
## <a name="print-a-worksheet-in-a-vsto-add-in"></a>Vytisknout list v doplňku VSTO  
  
### <a name="to-print-a-worksheet"></a>Chcete-li vytisknout list  
  
1. Volání <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintOut%2A> metoda aktivního listu, požádat o dvě kopie a zobrazit jejich náhled dokumentu před tiskem.  
  
    [!code-csharp[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#14)]
    [!code-vb[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#14)]  
  
   <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> Metoda vám umožňuje zobrazit zadaný objekt v **Náhled** okna.  
  
### <a name="to-preview-a-page-before-printing"></a>Náhled stránky před tiskem  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> metoda aktivního listu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: Kontrola pravopisu v listech prostřednictvím kódu programu](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)   
 [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
