---
title: "Postupy: programové odemykání listů | Microsoft Docs"
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
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1b4564baab3cf2daa6e8859a66dbc6e9e06ffdef
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  