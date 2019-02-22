---
title: 'Postupy: Zavírání sešitů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, closing
- Excel [Office development in Visual Studio], closing workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 626f4e2328a208412d1e4e10857f336f37578f51
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56620067"
---
# <a name="how-to-programmatically-close-workbooks"></a>Postupy: Zavírání sešitů prostřednictvím kódu programu
  Můžete zavřít aktivní sešitu nebo můžete zadat sešitu zavřete.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="close-the-active-workbook"></a>Zavřít aktivní sešitu
 Jsou dva postupy pro uzavření aktivním sešitu: jeden pro přizpůsobení na úrovni dokumentu a jeden pro doplňky VSTO.

### <a name="to-close-the-active-workbook-in-a-document-level-customization"></a>Zavřít aktivní sešitu v přizpůsobení na úrovni dokumentu

1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.Close%2A> metoda zavřete sešit přidružené k přizpůsobení. Chcete-li použít následující příklad kódu, spusťte `Sheet1` třídy v projektu úrovni dokumentu pro Excel.

     [!code-csharp[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#3)]

### <a name="to-close-the-active-workbook-in-a-vsto-add-in"></a>Zavřít aktivní sešitu v doplňku VSTO

1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.Close%2A> metoda zavřete aktivní sešitu. Chcete-li použít následující příklad kódu, spusťte `ThisAddIn` třídy v projektu doplňku VSTO pro Excel.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#1)]

## <a name="close-a-workbook-that-you-specify-by-name"></a>Zavřete sešit, který určíte podle názvu
 Způsob, jakým zavřete sešit, který určíte podle názvu je stejný pro přizpůsobení na úrovni dokumentu a doplňky VSTO.

### <a name="to-close-a-workbook-that-you-specify-by-name"></a>Zavřete sešit, který určíte podle názvu

1.  Zadejte název sešitu jako argument <xref:Microsoft.Office.Interop.Excel.Workbooks> kolekce. Následující příklad kódu předpokládá, že sešit s názvem **NewWorkbook** je otevřen v aplikaci Excel.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#2)]

## <a name="see-also"></a>Viz také:
- [Práce se sešity](../vsto/working-with-workbooks.md)
- [Postupy: Ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)
- [Postupy: Otevírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-workbooks.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
