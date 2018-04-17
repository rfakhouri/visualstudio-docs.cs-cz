---
title: 'Postupy: vytváření nových sešitů prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], creating workbooks
- workbooks, creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0ba2054258beb762a6b554a49b7a64a77f83dd7a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-create-new-workbooks"></a>Postupy: Vytváření nových sešitů prostřednictvím kódu programu
  Když vytvoříte sešitu prostřednictvím kódu programu, je nativní <xref:Microsoft.Office.Interop.Excel.Workbook> objektu není <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelská položka.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Můžete vygenerovat <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelská položka pro <xref:Microsoft.Office.Interop.Excel.Workbook> objektu v projektu doplňku VSTO. Další informace najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="to-create-a-new-workbook"></a>K vytvoření nového sešitu  
  
1.  Použití <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> metodu <xref:Microsoft.Office.Interop.Excel.Workbooks> kolekce.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#1)]  
  
    > [!NOTE]  
    >  Můžete vytvořit na základě šablony než výchozí šablonu sešitu: předat šablonu, kterou chcete použít jako parametr, který se <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> metoda.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Postupy: otevírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-workbooks.md)   
 [Postupy: ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)   
 [Postupy: zavírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-workbooks.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)  
  
  