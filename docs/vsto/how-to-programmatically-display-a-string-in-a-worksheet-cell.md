---
title: 'Postupy: Zobrazování řetězec v buňkách listů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- text [Office development in Visual Studio], adding to worksheets
- worksheets, displaying text in cells
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 021fe02e501fc5a8921ec8f2a50329653ca45401
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53849765"
---
# <a name="how-to-programmatically-display-a-string-in-a-worksheet-cell"></a>Postupy: Zobrazování řetězec v buňkách listů prostřednictvím kódu programu
  Tento příklad ukazuje, jak zobrazit text v buňce prostřednictvím kódu programu. K zobrazení textu v buňkách, použijte buď <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo rozsah objekt nativní aplikace Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="use-a-namedrange-control"></a>Použití ovládacího prvku NamedRange  
 Tento příklad používá <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `message`. Ovládací prvek musí být přidaný do přizpůsobení úrovni dokumentu v době návrhu. Následující kód musí být umístěn ve třídě list, není v `ThisWorkbook` třídy.  
  
### <a name="to-display-text-in-a-namedrange-control"></a>K zobrazení textu v ovládacím prvkem namedrange  
  
1.  Nastavte hodnotu <xref:Microsoft.Office.Tools.Excel.NamedRange> mít pod kontrolou **Hello World**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#68)]
     [!code-vb[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#68)]  
  
## <a name="use-a-native-excel-range"></a>Použít nativní Excelového rozsahu  
 Následující kód vytvoří novou oblast prostřednictvím kódu programu a poté přiřadí hodnotu k ní.  
  
### <a name="to-display-text-in-an-excel-range"></a>K zobrazení textu v oblasti aplikace Excel  
  
1.  Načtení rozsahu na buňku **A1** na `Sheet1` a nastavte hodnotu na **Hello World**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#69)]
     [!code-vb[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#69)]  
  
## <a name="see-also"></a>Viz také:  
 [Návod: Shromažďování dat pomocí formuláře Windows](../vsto/walkthrough-collecting-data-using-a-windows-form.md)   
 [Řešení potíží s řešení pro systém Office](../vsto/troubleshooting-office-solutions.md)   
 [Namedrange – ovládací prvek](../vsto/namedrange-control.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
