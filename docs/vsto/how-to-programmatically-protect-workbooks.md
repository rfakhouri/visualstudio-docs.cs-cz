---
title: 'Postupy: Zamykání sešitů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, passwords
- documents [Office development in Visual Studio], document protection
- workbooks, unprotecting
- document protection, removing from workbooks
- document protection, adding to workbooks
- workbooks, protecting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5333504ed534373b6bb65902edb2566953de7a59
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863679"
---
# <a name="how-to-programmatically-protect-workbooks"></a>Postupy: Zamykání sešitů
  Sešit Microsoft Office Excelu můžete chránit tak, aby uživatelé nelze přidat nebo odstraňování listů a také programově odemknutí sešitu. Volitelně můžete zadat heslo, uvádí, zda má být struktura chráněných (takže uživatele nelze přesunout seznamy) a určit, jestli chcete v sešitu windows chráněné.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Uzamčení sešitu nezastaví zabránit uživatelům v úpravě buňky. K ochraně dat, je nutné chránit listů. Další informace najdete v tématu [jak: Zamykání listů](../vsto/how-to-programmatically-protect-worksheets.md).  
  
 Následující příklady kódu použít proměnnou tak, aby obsahovala heslo, které pochází od uživatele.  
  
## <a name="protect-a-workbook-that-is-part-of-a-document-level-customization"></a>Zamknout sešit, který je součástí přizpůsobení na úrovni dokumentu  
  
### <a name="to-protect-a-workbook"></a>Pokud chcete zamknout sešit  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> metoda sešitu a heslo. Chcete-li použít následující příklad kódu, spusťte `ThisWorkbook` třídy, nikoli ve třídě list.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#10)]
     [!code-vb[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#10)]  
  
### <a name="to-unprotect-a-workbook"></a>Odemknout sešit  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.Unprotect%2A> metodu, pokud se vyžaduje k předání hesla. Chcete-li použít následující příklad kódu, spusťte `ThisWorkbook` třídy, nikoli ve třídě list.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#11)]  
  
## <a name="protect-a-workbook-by-using-an-application-level-add-in"></a>Zamknout sešit pomocí doplňku úrovni aplikace  
  
### <a name="to-protect-a-workbook"></a>Pokud chcete zamknout sešit  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.Protect%2A> metoda sešitu a heslo. Tento příklad kódu používá aktivním sešitu. Pokud chcete použít tento příklad, spusťte kód z `ThisAddIn` třídu ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#6)]  
  
### <a name="to-unprotect-a-workbook"></a>Odemknout sešit  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.Unprotect%2A> metoda aktivním sešitu, pokud se vyžaduje k předání hesla. Pokud chcete použít tento příklad, spusťte kód z `ThisAddIn` třídu ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Postupy: Zamykání listů](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Postupy: Skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
