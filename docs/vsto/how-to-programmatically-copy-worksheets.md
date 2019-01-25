---
title: 'Postupy: Kopírování listů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, copying
- Excel [Office development in Visual Studio], copying worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 64121ffcb69eb4bc3cdaa901ffe3d52014630779
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54865382"
---
# <a name="how-to-programmatically-copy-worksheets"></a>Postupy: Kopírování listů prostřednictvím kódu programu
  Můžete vytvořit kopii tohoto listu a listu vložte před nebo po existujícího listu v sešitu. Pokud nezadáte, kam chcete vložit do listu, Excel vytvoří nový sešit obsahující nový list.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
> [!NOTE]  
>  Ať už prostřednictvím kódu programu zkopírujte do listu, nebo koncový uživatel ručně zkopíruje do listu, není žádný kód za nový list a ovládacích prvků na nový list nefungují. Důvodem je, že je nově zkopírovaný list <xref:Microsoft.Office.Interop.Excel.Worksheet> objekt a ne <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt. Ovládacích prvků Windows Forms a hostitelských ovládacích prvků můžete přidat jenom do hostitelské položky. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
## <a name="to-add-a-copied-worksheet-to-a-workbook-in-a-document-level-customization"></a>Chcete-li přidat zkopírovaný list do sešitu v přizpůsobení na úrovni dokumentu  
  
1.  Použití <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> metoda kopírování první sešit v aktuálním sešitu a umístěte kopii za třetí list.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#16](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomation#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#16)]  
  
## <a name="to-add-a-copied-worksheet-to-a-workbook-in-a-vsto-add-in"></a>Chcete-li přidat zkopírovaný list do sešitu v doplňku VSTO  
  
1.  Použití <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> metoda kopírování první sešit v aktuálním sešitu a umístěte kopii za třetí list.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#12](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#12](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#12)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Postupy: Přidávání nových listů do sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Postupy: Odstraňování listů ze sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Postupy: Výběr listů prostřednictvím kódu programu](../vsto/how-to-programmatically-select-worksheets.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
