---
title: "Postupy: ukládání sešitů prostřednictvím kódu programu | Microsoft Docs"
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
- workbooks, saving in XML format
- workbooks, saving
- workbooks, saving backup copies
ms.assetid: 991ccf9b-5213-4094-9030-284ec167bdcc
caps.latest.revision: "50"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5be604d75183209ecdf068409e26007277cb6d98
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-save-workbooks"></a>Postupy: Ukládání sešitů prostřednictvím kódu programu
  Uložte sešit několika způsoby. Sešit můžete uložit bez Změna cesty. Pokud před nebyl uložen do sešitu, byste měli uložit sešit tak, že zadáte cestu. Aplikace Microsoft Office Excel bez explicitní cesty, uloží soubor v aktuální složce s názvem, který byl zadán, pokud byla vytvořena. Můžete také uložit kopii tohoto sešitu beze změny otevřete sešit v paměti.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="saving-a-workbook-without-changing-the-path"></a>Ukládání sešitu beze změny cesty  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Uložte sešit přidružené k přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.Save%2A> metoda ThisWorkbook – třída.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#4)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Uložení aktivním sešitu v doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.Save%2A> metody uložte aktivním sešitu. Chcete-li použít následující příklad kódu, spusťte jej `ThisAddIn` – třída v projektu doplňku VSTO pro Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="saving-a-workbook-with-a-new-path"></a>Ukládání sešitu s novou cestu  
 Zadaný sešit můžete uložit do nového umístění nebo s novým názvem volitelnému určení formátu souboru, heslo, přístupovém režimu a další.  
  
> [!NOTE]  
>  Můžete chtít nastavit <xref:Microsoft.Office.Interop.Excel._Application.DisplayAlerts%2A> vlastnost **False** před uložením sešitu s novou cestu, protože ukládání v některé formáty vyžaduje interakci. Nastavení této vlastnosti na **False** způsobí, že Excel použije všechny výchozí hodnoty.  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Uložte sešit přidružené k přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> metodu `ThisWorkbook` třídy. Chcete-li použít následující příklad kódu, spusťte jej `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#5)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Uložení aktivním sešitu v doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.SaveAs%2A> metoda active sešit uložte novou cestu. Chcete-li použít následující příklad kódu, spusťte jej `ThisAddIn` – třída v projektu doplňku VSTO pro Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="saving-a-copy-of-the-workbook"></a>Ukládání kopii sešitu  
 Kopii tohoto sešitu můžete uložit do souboru beze změny otevřete sešit v paměti. To je užitečné, pokud chcete vytvořit záložní kopii beze změny umístění sešitu.  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Uložte sešit přidružené k přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.SaveCopyAs%2A> metodu `ThisWorkbook` třídy. Chcete-li použít následující příklad kódu, spusťte jej `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#6)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Uložení aktivním sešitu v doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.SaveCopyAs%2A> metodu pro uložení kopie aktivním sešitu. Chcete-li použít následující příklad kódu, spusťte jej `ThisAddIn` – třída v projektu doplňku VSTO pro Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="robust-programming"></a>Robustní programování  
 Interaktivně zrušení některou z metod, které uložit nebo kopírovat do sešitu vyvolá chybu spuštění ve vašem kódu. Například, pokud procedura volá <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> metoda, ale nemá, vyzve není zakázat z Excelu, a vaše uživatel klikne na **zrušit** po zobrazení výzvy aplikace Excel vyvolá chybu spuštění.  
  
## <a name="see-also"></a>Viz také  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Hostitelská položka Workbook](../vsto/workbook-host-item.md)   
 [Postupy: zavírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-workbooks.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)  
  
  