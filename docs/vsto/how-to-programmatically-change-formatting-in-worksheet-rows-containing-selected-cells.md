---
title: "Postupy: formátování řádků listů obsahujících zvolené buňky prostřednictvím kódu programu změnit | Microsoft Docs"
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
- rows [Office development in Visual Studio]
- formatting [Office development in Visual Studio]
- worksheets, changing formatting
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 441adcf3b8f803d1473cd36a6d73474b06cf6efe
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells"></a>Postupy: Změna formátování řádků listů obsahujících zvolené buňky prostřednictvím kódu programu
  Můžete změnit písmo celý řádek, který obsahuje vybrané buňky tak, aby text tučně.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-make-the-current-row-bold-and-the-previously-bolded-row-normal"></a>Tučným písmem na aktuálním řádku a dříve uveden tučně řádek normální  
  
1.  Deklarujte statickou proměnnou ke sledování dříve vybraný řádek.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#37](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#37)]
     [!code-vb[Trin_VstcoreExcelAutomation#37](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#37)]  
  
2.  Načíst odkaz na aktuální buňky pomocí <xref:Microsoft.Office.Interop.Excel._Application.ActiveCell%2A> vlastnost.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#38](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#38)]
     [!code-vb[Trin_VstcoreExcelAutomation#38](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#38)]  
  
3.  Styl aktuálního řádku tučné pomocí <xref:Microsoft.Office.Interop.Excel.Range.EntireRow%2A> vlastnost aktivní buňce.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#39](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#39)]
     [!code-vb[Trin_VstcoreExcelAutomation#39](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#39)]  
  
4.  Ujistěte se, že aktuální hodnota `previousRow` není 0. 0 (nula) označuje, že se jedná o první přihlášení pomocí tohoto kódu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#40](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#40)]
     [!code-vb[Trin_VstcoreExcelAutomation#40](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#40)]  
  
5.  Zajistěte, aby byl na aktuálním řádku liší od předchozí řádek.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#41](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#41)]
     [!code-vb[Trin_VstcoreExcelAutomation#41](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#41)]  
  
6.  Načtení a odkaz na rozsah, který představuje řádek, který byl dříve vybraném a nastavte které řádek není tučně.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#42](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#42)]
     [!code-vb[Trin_VstcoreExcelAutomation#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#42)]  
  
7.  Na aktuálním řádku uložte tak, aby se stala na předchozí řádek na další průchodu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#43](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#43)]
     [!code-vb[Trin_VstcoreExcelAutomation#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#43)]  
  
 Následující příklad ukazuje metodu dokončení.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_VstcoreExcelAutomation#36](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#36)]
 [!code-vb[Trin_VstcoreExcelAutomation#36](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#36)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: programové používání stylů pro oblasti sešitů](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Postupy: kopírování dat a formátování mezi listy prostřednictvím kódu programu](../vsto/how-to-programmatically-copy-data-and-formatting-across-worksheets.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  