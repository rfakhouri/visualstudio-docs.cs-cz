---
title: "Postupy: zamykání sešitů prostřednictvím kódu programu | Microsoft Docs"
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
- workbooks, passwords
- documents [Office development in Visual Studio], document protection
- workbooks, unprotecting
- document protection, removing from workbooks
- document protection, adding to workbooks
- workbooks, protecting
ms.assetid: 553c67b9-e2a4-46b6-878c-5b4b4efa4589
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7dcbedb2c30758c762af0c301c239dd03fe4b10f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-protect-workbooks"></a>Postupy: Zamykání sešitů prostřednictvím kódu programu
  Sešitu aplikace Microsoft Office Excel můžete chránit tak, aby uživatelé nelze přidat nebo odstraňování listů a také prostřednictvím kódu programu ochranu sešitu. Volitelně můžete zadat heslo, uvádí, zda má strukturu chráněné (takže uživatele nelze přesunout listy) a uveďte, zda má windows sešit chráněný.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Ochrana sešitu nezastaví uživatele z úpravy buněk. K ochraně dat, je nutné chránit listů. Další informace najdete v tématu [postupy: ochrana listů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-worksheets.md).  
  
 Následující příklady kódu pomocí proměnné heslo, které se získávají z uživatele.  
  
## <a name="protecting-a-workbook-that-is-part-of-a-document-level-customization"></a>Ochrana sešit, který je součástí přizpůsobení na úrovni dokumentu  
  
#### <a name="to-protect-a-workbook"></a>K ochraně sešitu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> metoda sešit a obsahovat heslo. Chcete-li použít následující příklad kódu, spusťte jej `ThisWorkbook` třída, není v seznamu vlastností třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#10)]
     [!code-vb[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#10)]  
  
#### <a name="to-unprotect-a-workbook"></a>Chcete-li zrušit ochranu sešitu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.Unprotect%2A> metodu předáním heslo v případě potřeby. Chcete-li použít následující příklad kódu, spusťte jej `ThisWorkbook` třída, není v seznamu vlastností třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#11)]  
  
## <a name="protecting-a-workbook-by-using-an-application-level-add-in"></a>Ochrana sešitu pomocí doplňku úrovni aplikace  
  
#### <a name="to-protect-a-workbook"></a>K ochraně sešitu  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.Protect%2A> metoda sešit a obsahovat heslo. Tento příklad kódu používá aktivním sešitu. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#6)]  
  
#### <a name="to-unprotect-a-workbook"></a>Chcete-li zrušit ochranu sešitu  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.Unprotect%2A> metoda aktivním sešitu, předávání heslo v případě potřeby. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Viz také  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Postupy: zamykání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Postupy: skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  