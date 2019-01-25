---
title: 'Postupy: Vytváření seznamů naposledy použitých souborů sešitů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, listing recently used
- RecentFiles property
- Excel [Office development in Visual Studio], recently used files listing
- recent file list, Excel
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6451aa5427799f0905d19b7b90e87f8cca3d0bbd
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863185"
---
# <a name="how-to-programmatically-list-recently-used-workbook-files"></a>Postupy: Vytváření seznamů naposledy použitých souborů sešitů
  <xref:Microsoft.Office.Interop.Excel._Application.RecentFiles%2A> Vlastnost vrací kolekci, která obsahuje názvy všech souborů, které se zobrazí v seznamu naposledy použitých souborů Microsoft Office Excel. Délka seznamu se liší v závislosti na počtu souborů, které uživatel vybral Pokud chcete zachovat. Zobrazit výsledky v rozsahu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-list-recently-used-workbooks-in-a-range-object"></a>Do seznamu naposledy použitých sešitů v rozsahu objektu  
  
1.  Projděte seznam naposledy použitých souborů a zobrazit názvy v buňkách vzhledem k <xref:Microsoft.Office.Interop.Excel.Range> objektu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Namedrange – ovládací prvek](../vsto/namedrange-control.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
