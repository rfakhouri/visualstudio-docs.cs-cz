---
title: 'Postupy: Používání stylů pro oblasti sešitů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, styles
- styles, workbook ranges
- workbooks, styles
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f74b2d08a268bc79bcd7d2fd33513b5ccf5b1415
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62817450"
---
# <a name="how-to-programmatically-apply-styles-to-ranges-in-workbooks"></a>Postupy: Používání stylů pro oblasti sešitů prostřednictvím kódu programu
  Pojmenované stylů můžete použít k oblastem v sešitech. Excel poskytuje řadu předdefinovaných stylů.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 **Formát buňky** dialogové okno zobrazí všechny možnosti, můžete použít k formátování buňky a každá z těchto možností je k dispozici z vašeho kódu. K tomuto dialogovému oknu zobrazení v aplikaci Excel, klikněte na tlačítko **buňky** na **formátu** nabídky.

## <a name="to-apply-a-style-to-a-named-range-in-a-document-level-customization"></a>Použít styl na pojmenované oblasti v přizpůsobení na úrovni dokumentu

1. Vytvořte nový styl a nastavte jeho atributy.

     [!code-csharp[Trin_VstcoreExcelAutomation#53](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#53)]
     [!code-vb[Trin_VstcoreExcelAutomation#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#53)]

2. Vytvoření <xref:Microsoft.Office.Tools.Excel.NamedRange> řídit, přiřadit text a pak použít nový styl. Tento kód musí být umístěn ve třídě list, není v `ThisWorkbook` třídy.

     [!code-csharp[Trin_VstcoreExcelAutomation#54](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#54)]
     [!code-vb[Trin_VstcoreExcelAutomation#54](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#54)]

## <a name="to-clear-a-style-from-a-named-range-in-a-document-level-customization"></a>Vymazat styl z pojmenované oblasti v přizpůsobení na úrovni dokumentu

1. Použijte normální styl rozsahu. Tento kód musí být umístěn ve třídě list, není v `ThisWorkbook` třídy.

     [!code-csharp[Trin_VstcoreExcelAutomation#55](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#55)]
     [!code-vb[Trin_VstcoreExcelAutomation#55](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#55)]

## <a name="to-apply-a-style-to-a-named-range-in-a-vsto-add-in"></a>Použít styl na pojmenované oblasti v doplňku VSTO

1. Vytvořte nový styl a nastavte jeho atributy.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#28](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#28](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#28)]

2. Vytvoření <xref:Microsoft.Office.Interop.Excel.Range>přiřadit text a pak použít nový styl.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#29](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#29](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#29)]

## <a name="to-clear-a-style-from-a-named-range-in-a-vsto-add-in"></a>Vymazat styl z pojmenované oblasti v doplňku VSTO

1. Použijte normální styl rozsahu.

     [!code-csharp[Trin_VstcoreExcelAutomation#56](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#56)]
     [!code-vb[Trin_VstcoreExcelAutomation#56](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#56)]

## <a name="see-also"></a>Viz také:
- [Práce s oblastmi](../vsto/working-with-ranges.md)
- [Namedrange – ovládací prvek](../vsto/namedrange-control.md)
- [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
