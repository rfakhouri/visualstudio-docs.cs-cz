---
title: 'Postupy: zavírání sešitů prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, closing
- Excel [Office development in Visual Studio], closing workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d63c2e3245a49ea7cf8615d485ccaed2eb3031a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-close-workbooks"></a>Postupy: Zavírání sešitů prostřednictvím kódu programu
  Můžete zavřít aktivním sešitu nebo můžete zadat sešitu zavřete.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="closing-the-active-workbook"></a>Zavření aktivním sešitu  
 Existují dva postupy pro zavření aktivním sešitu: jeden pro přizpůsobení na úrovni dokumentu a jeden pro doplňky VSTO.  
  
#### <a name="to-close-the-active-workbook-in-a-document-level-customization"></a>Zavřete aktivním sešitu v přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.Close%2A> metoda zavřete sešit přidružené k přizpůsobení. Chcete-li použít následující příklad kódu, spusťte jej `Sheet1` – třída v projektech na úrovni dokumentu pro Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#3)]  
  
#### <a name="to-close-the-active-workbook-in-a-vsto-add-in"></a>Zavřete aktivním sešitu v doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.Close%2A> metoda zavřete aktivním sešitu. Chcete-li použít následující příklad kódu, spusťte jej `ThisAddIn` – třída v projektu doplňku VSTO pro Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="closing-a-workbook-that-you-specify-by-name"></a>Zavřením sešitu, který určíte podle názvu  
 Způsob, jakým zavřete sešit, který zadáte název je stejný pro doplňky VSTO a úpravy na úrovni dokumentů.  
  
#### <a name="to-close-a-workbook-that-you-specify-by-name"></a>Zavřete sešit, který určíte podle názvu  
  
1.  Zadejte název sešitu jako argument pro <xref:Microsoft.Office.Interop.Excel.Workbooks> kolekce. Následující příklad kódu předpokládá, že sešitu s názvem **NewWorkbook** je otevřít v aplikaci Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="see-also"></a>Viz také  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Postupy: ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)   
 [Postupy: otevírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-workbooks.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)  
  
  