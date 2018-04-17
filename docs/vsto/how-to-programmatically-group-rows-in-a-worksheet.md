---
title: 'Postupy: programové skupiny řádků v listech | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 894e3971c257a6461aa975a9d6bb1cf933234440
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-group-rows-in-a-worksheet"></a>Postupy: Seskupování řádků v listech prostřednictvím kódu programu
  Můžete seskupit jeden nebo více celou řádků. Chcete-li vytvořit skupinu v listu, použijte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo objekt rozsahu nativní aplikace Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>Použití ovládacího prvku NamedRange  
 Pokud přidáte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do projektu úrovni dokumentu v době návrhu, můžete použít ovládací prvek prostřednictvím kódu programu vytvořte skupinu. V následujícím příkladu se předpokládá, že existují tři <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacích prvků na stejné listu: `data2001`, `data2002`, a `dataAll`. Každé pojmenované oblasti odkazuje na celý řádek do listu.  
  
#### <a name="to-create-a-group-of-namedrange-controls-on-a-worksheet"></a>Chcete-li vytvořit skupinu ovládacích prvků NamedRange do listu  
  
1.  Skupina tří pojmenované oblasti voláním <xref:Microsoft.Office.Tools.Excel.NamedRange.Group%2A> metoda každého rozsahu. Tento kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#32)]
     [!code-vb[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#32)]  
  
    > [!NOTE]  
    >  Chcete-li zrušit seskupení řádků, zavolejte <xref:Microsoft.Office.Tools.Excel.NamedRange.Ungroup%2A> metoda.  
  
## <a name="using-native-excel-ranges"></a>Pomocí nativní oblastí aplikace Excel  
 Kód předpokládá, že máte tři oblastí aplikace Excel s názvem `data2001`, `data2002`, a `dataAll` na listu.  
  
#### <a name="to-create-a-group-of-excel-ranges-in-a-worksheet"></a>Chcete-li vytvořit skupinu oblastí aplikace Excel v listu  
  
1.  Skupina tří pojmenované oblasti voláním <xref:Microsoft.Office.Interop.Excel.Range.Group%2A> metoda každého rozsahu. V následujícím příkladu se předpokládá, že existují tři <xref:Microsoft.Office.Interop.Excel.Range> ovládací prvky s názvem `data2001`, `data2002`, a `dataAll` na stejném listu. Každé pojmenované oblasti odkazuje na celý řádek do listu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#33)]
     [!code-vb[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#33)]  
  
    > [!NOTE]  
    >  Chcete-li zrušit seskupení řádků, zavolejte <xref:Microsoft.Office.Interop.Excel.Range.Ungroup%2A> metoda.  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  