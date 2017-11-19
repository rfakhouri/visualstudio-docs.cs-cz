---
title: "Postupy: programové ukládání a načítání hodnot data do oblastí aplikace Excel | Microsoft Docs"
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
- Excel [Office development in Visual Studio], retrieving date values from ranges
- ranges, retrieving data values
- dates, retrieving from Excel ranges
- Excel [Office development in Visual Studio], storing date values in ranges
- date values, storing in Excel ranges
- dates, storing in Excel ranges
- ranges, storing date values
- date values
ms.assetid: e1cdd262-0356-4499-8bc5-e730f74235a2
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4d19de6848da22238dc1cf394fa3d417ea0d8c88
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-store-and-retrieve-date-values-in-excel-ranges"></a>Postup: Ukládání hodnot data do oblastí aplikace Excel a jejich načítání prostřednictvím kódu programu
  Můžete ukládat a načítat hodnoty v <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo objekt rozsahu nativní aplikace Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Pokud ukládáte hodnotu data, která spadá na nebo po 1/1/1900 v rozsahu pomocí nástrojů pro vývoj pro Office v sadě Visual Studio, je uložený ve formátu OLE automatizace (OA). Je nutné použít <xref:System.DateTime.FromOADate%2A> metoda se načíst hodnotu dat OLE automatizace (OA). Pokud je starší než 1/1/1900 datum, je uložený jako řetězec.  
  
> [!NOTE]  
>  Data aplikace Excel se liší od automatizace OLE data pro prvních dvou měsíců 1900. Existují také rozdíly pokud **1904 datum systému** zaškrtnutá možnost. Příklady kódu níže nezabývají tyto rozdíly.  
  
## <a name="using-a-namedrange-control"></a>Použití ovládacího prvku NamedRange  
  
-   V tomto příkladu je pro úpravy na úrovni dokumentů. Následující kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
#### <a name="to-store-a-date-value-in-a-named-range"></a>K uložení hodnota kalendářního data v pojmenované oblasti  
  
1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení na buňky **A1**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#50)]
     [!code-vb[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#50)]  
  
2.  Nastavená jako hodnota pro dnešní datum `NamedRange1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#51)]
     [!code-vb[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#51)]  
  
#### <a name="to-retrieve-a-date-value-from-a-named-range"></a>Načíst hodnotu data z pojmenované oblasti  
  
1.  Načíst hodnotu data z `NamedRange1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#52)]
     [!code-vb[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#52)]  
  
## <a name="using-native-excel-ranges"></a>Pomocí nativní oblastí aplikace Excel  
  
#### <a name="to-store-a-date-value-in-a-native-excel-range-object"></a>K uložení hodnota kalendářního data v objektu rozsah nativní aplikace Excel  
  
1.  Vytvoření <xref:Microsoft.Office.Interop.Excel.Range> buňku, která představuje **A1**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#25)]  
  
2.  Nastavená jako hodnota pro dnešní datum `rng`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#26)]  
  
#### <a name="to-retrieve-a-date-value-from-a-native-excel-range-object"></a>Načíst hodnotu data z objektu rozsah nativní aplikace Excel  
  
1.  Načíst hodnotu data z `rng`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#27)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s oblastmi](../vsto/working-with-ranges.md)   
 [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Postupy: odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  