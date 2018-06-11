---
title: 'Postupy: programové používání stylů pro oblasti sešitů'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, styles
- styles, workbook ranges
- workbooks, styles
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d1fd06384febf4e886c28bd4811d10413e0eeb54
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256637"
---
# <a name="how-to-programmatically-apply-styles-to-ranges-in-workbooks"></a>Postupy: programové používání stylů pro oblasti sešitů
  Můžete použít názvů stylů pro oblasti v sešitech. Excel poskytuje řadu předdefinovaných stylů.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 **Formát buněk** dialogové okno zobrazí všechny možnosti, můžete použít k formátování buněk a každá z těchto možností je k dispozici z vašeho kódu. Chcete-li zobrazit tohoto dialogového okna v aplikaci Excel, klikněte na tlačítko **buněk** na **formát** nabídky.  
  
## <a name="to-apply-a-style-to-a-named-range-in-a-document-level-customization"></a>Pokud chcete použít styl na pojmenované oblasti v přizpůsobení na úrovni dokumentu  
  
1.  Vytvořit nový styl a nastavit jeho atributy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#53](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#53)]
     [!code-vb[Trin_VstcoreExcelAutomation#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#53)]  
  
2.  Vytvoření <xref:Microsoft.Office.Tools.Excel.NamedRange> řídit, přiřadit text a pak použít nový styl. Tento kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#54](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#54)]
     [!code-vb[Trin_VstcoreExcelAutomation#54](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#54)]  
  
## <a name="to-clear-a-style-from-a-named-range-in-a-document-level-customization"></a>Zrušte styl z pojmenované oblasti v přizpůsobení na úrovni dokumentu  
  
1.  Použijte normální styl rozsahu. Tento kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#55](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#55)]
     [!code-vb[Trin_VstcoreExcelAutomation#55](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#55)]  
  
## <a name="to-apply-a-style-to-a-named-range-in-a-vsto-add-in"></a>Pokud chcete použít styl na pojmenované oblasti v doplňku VSTO  
  
1.  Vytvořit nový styl a nastavit jeho atributy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#28](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#28](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#28)]  
  
2.  Vytvoření <xref:Microsoft.Office.Interop.Excel.Range>, přiřadit text a pak použít nový styl.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#29](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#29](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#29)]  
  
## <a name="to-clear-a-style-from-a-named-range-in-an-vsto-add-in"></a>Zrušte styl z pojmenované oblasti v doplňku VSTO  
  
1.  Použijte normální styl rozsahu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#56](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#56)]
     [!code-vb[Trin_VstcoreExcelAutomation#56](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#56)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce s rozsahy](../vsto/working-with-ranges.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  