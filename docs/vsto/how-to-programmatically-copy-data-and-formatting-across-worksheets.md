---
title: 'Postupy: Kopírování dat a formátování mezi listy prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, copying data
- formatting [Office development in Visual Studio]
- data [Office development in Visual Studio], copying across worksheets
- copying data, Office development in Visual Studio
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9995b347fdfcb60acf72c79b0e1bddc20bab717b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53924862"
---
# <a name="how-to-programmatically-copy-data-and-formatting-across-worksheets"></a>Postupy: Kopírování dat a formátování mezi listy prostřednictvím kódu programu
  Můžete zkopírovat data z rozsahu na jeden seznam pro všechny ostatní listů v sešitu pomocí <xref:Microsoft.Office.Interop.Excel.Worksheets.FillAcrossSheets%2A> metody. Zadejte rozsah, a určuje, zda chcete zkopírovat data, formátování nebo obojí.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#44)]
 [!code-vb[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#44)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad vyžaduje oblast s názvem `rangeData` v listu.  
  
## <a name="see-also"></a>Viz také:  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: Přidávání nových listů do sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Postupy: Změna formátování řádků listů obsahujících zvolené buňky prostřednictvím kódu programu](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
