---
title: "Postupy: nastavování barev oblastí aplikace Excel | Microsoft Docs"
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
- formatting [Office development in Visual Studio]
- color, Excel ranges
- ranges, applying color
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5e9b5f6bc38cdcb4b4ee11543ea70e3b137a937f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  