---
title: "Postupy: vytváření seznamů naposledy použitých souborů sešitů | Microsoft Docs"
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
- workbooks, listing recently used
- RecentFiles property
- Excel [Office development in Visual Studio], recently used files listing
- recent file list, Excel
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e8a64f8a934e8cd7cdbbed11a87d15e795d19d0f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-list-recently-used-workbook-files"></a>Postupy: Vytváření seznamů naposledy použitých souborů sešitů prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Excel._Application.RecentFiles%2A> Vlastnost vrací kolekci, která obsahuje názvy všech souborů, které se zobrazují v aplikaci Microsoft Office Excel seznam naposledy použitých souborů. Délka seznamu se liší v závislosti na počtu souborů, které uživatel vybral Pokud chcete zachovat. Můžete zobrazit výsledky v rozsahu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-list-recently-used-workbooks-in-a-range-object"></a>Do sešitů seznamu nedávno použité v rozsahu objektu  
  
1.  Projděte seznam naposledy použitých souborů a zobrazit názvy v buňkách vzhledem k <xref:Microsoft.Office.Interop.Excel.Range> objektu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>Viz také  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  