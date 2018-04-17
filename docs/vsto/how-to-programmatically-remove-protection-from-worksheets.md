---
title: 'Postupy: programové odemykání listů | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c9e34e184462f1ec7822b5c2fce63aaff4a7f515
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>Postupy: Odemykání listů prostřednictvím kódu programu
  Ochranu můžete odebrat prostřednictvím kódu programu z listu aplikace Microsoft Office Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Následující příklad používá proměnnou `getPasswordFromUser`, který obsahuje heslo získaný od uživatele.  
  
### <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>Chcete-li zrušit ochranu sešitu v přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> metoda listu a předejte jí heslo, pokud je to nutné. Tento příklad předpokládá, že pracujete s na listu s názvem `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]  
  
### <a name="to-unprotect-a-worksheet-in-an-vsto-add-in"></a>Chcete-li zrušit ochranu sešitu v doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A> metoda aktivního listu a předejte jí heslo, pokud je to nutné.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: zamykání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Postupy: zamykání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-workbooks.md)   
 [Postupy: skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)  
  
  