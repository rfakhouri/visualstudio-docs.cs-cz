---
title: 'Postupy: Programově odemykání listů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ccf7de70c3ef741119ec22f8fa9bc76868a47030
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955949"
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>Postupy: Programově odemykání listů
  Můžete programově odebrat ochranu z list aplikace Microsoft Office Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Následující příklad používá proměnnou `getPasswordFromUser`, který obsahuje heslo získané od uživatele.

## <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>K odemknutí sešitu v přizpůsobení na úrovni dokumentu

1. Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> metoda listu a předejte jí hesla, v případě potřeby. Tento příklad předpokládá, že pracujete s listem s názvem `Sheet1`.

     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]

## <a name="to-unprotect-a-worksheet-in-a-vsto-add-in"></a>K odemknutí sešitu v doplňku VSTO

1. Volání <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A> metoda z aktivního listu a předejte jí hesla, v případě potřeby.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]

## <a name="see-also"></a>Viz také:
- [Práce s listy](../vsto/working-with-worksheets.md)
- [Postupy: Zamykání listů](../vsto/how-to-programmatically-protect-worksheets.md)
- [Postupy: Zamykání sešitů](../vsto/how-to-programmatically-protect-workbooks.md)
- [Postupy: Skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)
- [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)
