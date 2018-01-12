---
title: "Postupy: zobrazování v buňkách listů prostřednictvím kódu programu řetězec | Microsoft Docs"
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
- text [Office development in Visual Studio], adding to worksheets
- worksheets, displaying text in cells
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4a76d2588ec07c461794381a2edd502d367be274
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-display-a-string-in-a-worksheet-cell"></a>Postupy: Zobrazování řetězců v buňkách listů prostřednictvím kódu programu
  Tento příklad ukazuje, jak zobrazit text v buňce prostřednictvím kódu programu. Chcete-li zobrazit text v buňce, použijte buď <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo objekt rozsahu nativní aplikace Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>Použití ovládacího prvku NamedRange  
 Tento příklad používá <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `message`. Ovládací prvek musí být přidaný do přizpůsobení úrovni dokumentu v době návrhu. Následující kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
#### <a name="to-display-text-in-a-namedrange-control"></a>K zobrazení textu v ovládacím prvku NamedRange  
  
1.  Nastavte hodnotu <xref:Microsoft.Office.Tools.Excel.NamedRange> řídit k **Hello, World**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#68)]
     [!code-vb[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#68)]  
  
## <a name="using-a-native-excel-range"></a>Použití oblastí aplikace Excel nativní  
 Následující kód vytvoří nový rozsah prostřednictvím kódu programu a potom k němu přiřadí hodnotu.  
  
#### <a name="to-display-text-in-an-excel-range"></a>Zobrazení textu v oblasti aplikace Excel  
  
1.  Načtení rozsahu na buňky **A1** na `Sheet1` a nastavte hodnotu na **Hello, World**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#69)]
     [!code-vb[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#69)]  
  
## <a name="see-also"></a>Viz také  
 [Návod: Shromažďování dat pomocí formuláře Windows](../vsto/walkthrough-collecting-data-using-a-windows-form.md)   
 [Řešení potíží s řešení pro systém Office](../vsto/troubleshooting-office-solutions.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  