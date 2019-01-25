---
title: 'Postupy: Seskupování řádků v listech prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, creating groups
- groups, creating in worksheets
- ranges, creating groups
- worksheets, clearing groups
- groups
- groups [Office development in Visual Studio], clearing in worksheets
- worksheets, ungrouping rows and columns
- rows [Office development in Visual Studio], ungrouping
- columns [Office development in Visual Studio], ungrouping
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5249edccaed24dbdc6eb42b5da3e78825f1a2053
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54874405"
---
# <a name="how-to-programmatically-group-rows-in-a-worksheet"></a>Postupy: Seskupování řádků v listech prostřednictvím kódu programu
  Můžete seskupit nejméně jeden celý řádek. Chcete-li vytvořit skupinu na listu, použijte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo rozsah objekt nativní aplikace Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="use-a-namedrange-control"></a>Použití ovládacího prvku NamedRange  
 Pokud chcete přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení na úrovni dokumentu projektu v době návrhu, můžete použít ovládací prvek můžete prostřednictvím kódu programu vytvořit skupinu. V následujícím příkladu se předpokládá, že existují tři <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacích prvků ve stejném listu: `data2001`, `data2002`, a `dataAll`. Každý pojmenované oblasti odkazuje na celý řádek v listu.  
  
### <a name="to-create-a-group-of-namedrange-controls-on-a-worksheet"></a>Chcete-li vytvořit skupinu ovládacích prvků NamedRange do listu  
  
1.  Seskupit tři pojmenované oblasti voláním <xref:Microsoft.Office.Tools.Excel.NamedRange.Group%2A> metoda každého rozsahu. Tento kód musí být umístěn ve třídě list, není v `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#32)]
     [!code-vb[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#32)]  
  
    > [!NOTE]  
    >  Chcete-li zrušit seskupení řádků, zavolejte <xref:Microsoft.Office.Tools.Excel.NamedRange.Ungroup%2A> metody.  
  
## <a name="use-native-excel-ranges"></a>Použít nativní oblastí aplikace Excel  
 Kód předpokládá, že máte tři oblasti aplikace Excel s názvem `data2001`, `data2002`, a `dataAll` v listu.  
  
### <a name="to-create-a-group-of-excel-ranges-in-a-worksheet"></a>Můžete vytvořit skupinu oblastí aplikace Excel na listu  
  
1.  Seskupit tři pojmenované oblasti voláním <xref:Microsoft.Office.Interop.Excel.Range.Group%2A> metoda každého rozsahu. V následujícím příkladu se předpokládá, že existují tři <xref:Microsoft.Office.Interop.Excel.Range> ovládací prvky s názvem `data2001`, `data2002`, a `dataAll` na stejném listu. Každý pojmenované oblasti odkazuje na celý řádek v listu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#33)]
     [!code-vb[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#33)]  
  
    > [!NOTE]  
    >  Chcete-li zrušit seskupení řádků, zavolejte <xref:Microsoft.Office.Interop.Excel.Range.Ungroup%2A> metody.  
  
## <a name="see-also"></a>Viz také:  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Namedrange – ovládací prvek](../vsto/namedrange-control.md)   
 [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
