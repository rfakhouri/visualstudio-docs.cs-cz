---
title: "Postupy: Programové přidávání a odstraňování komentářů v listech | Microsoft Docs"
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
- ranges, comments
- worksheets, comments
- comments, worksheets
ms.assetid: 3408ce22-a7b7-4e2b-bfc1-dc24d679ee73
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4d9949cd9686c846c3baec67553b8cab203bc843
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-and-delete-worksheet-comments"></a>Postupy: Přidávání a odstraňování komentářů v listech prostřednictvím kódu programu
  Prostřednictvím kódu programu můžete přidat a odstranit komentářů v listech aplikace Microsoft Office Excel. Komentáře lze přidávat pouze do jedné buňky, není do buněk s více rozsahů.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="adding-and-deleting-a-comment-in-a-document-level-project"></a>Přidávání a odstraňování komentářů v projektech na úrovni dokumentu  
 Následující příklady předpokládá, že je jednotlivých buněk <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `dateComment` na listu s názvem `Sheet1`.  
  
#### <a name="to-add-a-new-comment-to-a-named-range"></a>Chcete-li přidat nový komentář na pojmenované oblasti  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.NamedRange.AddComment%2A> metodu <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení a zadejte text poznámky. Tento kód musí být umístěny v `Sheet1` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#30)]  
  
#### <a name="to-delete-a-comment-from-a-named-range"></a>Chcete-li odstranit komentář z pojmenované oblasti  
  
1.  Ověřte, zda existuje komentář na rozsah a odstraňte ji. Tento kód musí být umístěny v `Sheet1` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#29)]  
  
## <a name="adding-and-deleting-a-comment-in-an-vsto-add-in-project"></a>Přidávání a odstraňování komentářů v projektu doplňku VSTO  
 Následující příklady předpokládá, že je jednotlivých buněk <xref:Microsoft.Office.Interop.Excel.Range> s názvem `dateComment` na aktivním listu.  
  
#### <a name="to-add-a-new-comment-to-an-excel-range"></a>Chcete-li přidat nový komentář k oblasti aplikace Excel  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel.Range.AddComment%2A> metodu <xref:Microsoft.Office.Interop.Excel.Range> a zadejte text poznámky.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#20)]  
  
#### <a name="to-delete-a-comment-from-an-excel-range"></a>Chcete-li odstranit komentář z oblasti aplikace Excel  
  
1.  Ověřte, zda existuje komentář na rozsah a odstraňte ji.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#19)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: zobrazování komentářů v listech prostřednictvím kódu programu](../vsto/how-to-programmatically-display-worksheet-comments.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)  
  
  