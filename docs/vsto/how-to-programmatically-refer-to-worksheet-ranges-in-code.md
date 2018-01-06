---
title: "Postupy: odkazování na oblasti listů v kódu programu | Microsoft Docs"
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
- ranges, referring to
- worksheets, referring to ranges
- referring to worksheet ranges
- Excel [Office development in Visual Studio], referring to worksheet ranges
ms.assetid: 113633b8-426a-4d02-b6b8-d459d1f110ea
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 829cd94dc97d91afc9f3f991d088627ac9e1ccdc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-refer-to-worksheet-ranges-in-code"></a>Postupy: Odkazování na oblasti listů v kódu programu
  Použít podobným způsobem jako odkazy na obsah <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo objekt rozsahu nativní aplikace Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>Použití ovládacího prvku NamedRange  
 Následující příklad přidá <xref:Microsoft.Office.Tools.Excel.NamedRange> do listu a potom přidá text do buňky v rozsahu.  
  
#### <a name="to-refer-to-a-namedrange-control"></a>K odkazování na ovládacího prvku NamedRange  
  
1.  Přiřadit řetězec tak, aby <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku. Tento kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#46](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#46)]
     [!code-vb[Trin_VstcoreExcelAutomation#46](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#46)]  
  
## <a name="using-native-excel-ranges"></a>Pomocí nativní oblastí aplikace Excel  
 Následující příklad přidá rozsah nativní aplikace Excel do listu, pak přidá text do buňky v rozsahu.  
  
#### <a name="to-refer-to-a-native-range-object"></a>Odkazovat na objekt nativní rozsahu  
  
1.  Přiřadit řetězec tak, aby <xref:Microsoft.Office.Interop.Excel.Range.Value2%2A> vlastnost rozsahu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#47](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#47)]
     [!code-vb[Trin_VstcoreExcelAutomation#47](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#47)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s oblastmi](../vsto/working-with-ranges.md)   
 [Postupy: Kontrola pravopisu v listech prostřednictvím kódu programu](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)   
 [Postupy: programové používání stylů pro oblasti sešitů](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Postupy: programové automatické naplňování oblastí s přírůstkově se měnícími daty](../vsto/how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data.md)   
 [Postupy: hledání textu v oblastech listů prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-text-in-worksheet-ranges.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  