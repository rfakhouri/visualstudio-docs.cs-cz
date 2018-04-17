---
title: 'Postupy: nastavování barev oblastí aplikace Excel | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- formatting [Office development in Visual Studio]
- color, Excel ranges
- ranges, applying color
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b518cfb4f1ef7c5d757e4a68bbc12b51c6c61ae3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-apply-color-to-excel-ranges"></a>Postupy: Nastavování barev oblastí aplikace Excel prostřednictvím kódu programu
  Použít barvu textu v rámci oblasti buněk, použijte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo objekt rozsahu nativní aplikace Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>Použití ovládacího prvku NamedRange  
 V tomto příkladu je pro úpravy na úrovni dokumentů.  
  
#### <a name="to-apply-color-to-a-namedrange-control"></a>Chcete-li použít barvu do ovládacího prvku NamedRange  
  
1.  Vytvoření <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení na buňky A1.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#65](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#65)]
     [!code-vb[Trin_VstcoreExcelAutomation#65](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#65)]  
  
2.  Nastavení barvy textu v <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#66](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#66)]
     [!code-vb[Trin_VstcoreExcelAutomation#66](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#66)]  
  
## <a name="using-native-excel-ranges"></a>Pomocí nativní oblastí aplikace Excel  
  
#### <a name="to-apply-color-to-a-native-excel-range-object"></a>Chcete-li použít barvu nativní objektem rozsah aplikace Excel  
  
1.  Vytvořit rozsah v buňce A1 a poté nastavte barvu textu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#67](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#67)]
     [!code-vb[Trin_VstcoreExcelAutomation#67](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#67)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s oblastmi](../vsto/working-with-ranges.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Postupy: programové používání stylů pro oblasti sešitů](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Postupy: odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  