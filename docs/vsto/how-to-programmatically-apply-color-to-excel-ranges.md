---
title: 'Postupy: Nastavování barev oblastí aplikace Excel'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- formatting [Office development in Visual Studio]
- color, Excel ranges
- ranges, applying color
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4d85803e478931022e5872ddde2746b5b90feacf
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56614126"
---
# <a name="how-to-programmatically-apply-color-to-excel-ranges"></a>Postupy: Nastavování barev oblastí aplikace Excel
  Pokud chcete použít barvu textu v rámci oblasti buněk, použijte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo rozsah objekt nativní aplikace Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="use-a-namedrange-control"></a>Použití ovládacího prvku NamedRange
 Tento příklad je určený pro přizpůsobení na úrovni dokumentu.

### <a name="to-apply-color-to-a-namedrange-control"></a>Chcete-li použít barvu do ovládacího prvku NamedRange

1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku na buňku A1.

     [!code-csharp[Trin_VstcoreExcelAutomation#65](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#65)]
     [!code-vb[Trin_VstcoreExcelAutomation#65](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#65)]

2.  Nastavení barvy textu <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku.

     [!code-csharp[Trin_VstcoreExcelAutomation#66](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#66)]
     [!code-vb[Trin_VstcoreExcelAutomation#66](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#66)]

## <a name="use-native-excel-ranges"></a>Použít nativní oblastí aplikace Excel

### <a name="to-apply-color-to-a-native-excel-range-object"></a>Použít barvu na objekt nativní oblasti aplikace Excel

1.  Vytvoření rozsahu na buňku A1 a nastavte barvu textu.

     [!code-csharp[Trin_VstcoreExcelAutomation#67](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#67)]
     [!code-vb[Trin_VstcoreExcelAutomation#67](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#67)]

## <a name="see-also"></a>Viz také:
- [Práce s oblastmi](../vsto/working-with-ranges.md)
- [Namedrange – ovládací prvek](../vsto/namedrange-control.md)
- [Postupy: Používání stylů pro oblasti sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)
- [Postupy: Odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)
- [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
