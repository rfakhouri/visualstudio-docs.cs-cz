---
title: "Postupy: Změna velikosti ovládacích prvků v buňkách listu | Microsoft Docs"
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
- controls [Office development in Visual Studio], resizing
- managed controls, resizing
- worksheets, resizing
- Windows Forms controls [Office development in Visual Studio], resizing
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 01e9dfbe244d373eaa4e66c13e02c781b32b8691
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-resize-controls-within-worksheet-cells"></a>Postupy: Změna velikosti ovládacích prvků v buňkách listu
  Změna velikosti sloupců a řádků v listu, změňte velikost na výšku nebo šířku buňku, která byla po změně velikosti všechny hostitelské ovládací prvky obsažené v buňkách automaticky. Ovládací prvky Windows Forms automaticky velikost ve výchozím nastavení.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Pokud přidáte ovládací prvky v době návrhu, musíte nastavit možnosti pro každý ovládací prvek umístění.  
  
 Pokud jste prostřednictvím kódu programu Přidání ovládacího prvku Windows Forms a zadejte rozsah argument, ovládacího prvku změní při změně velikosti buněk v rozsahu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="resizing-controls-at-design-time"></a>Změna velikosti ovládacích prvků v době návrhu  
  
#### <a name="to-make-controls-resize-with-cells-at-design-time"></a>Chcete-li změnit velikost s buňkami v době návrhu ovládací prvky  
  
1.  Z **sada nástrojů**, přetáhněte ovládací prvek Windows Forms do listu.  
  
2.  Klikněte pravým tlačítkem na ovládací prvek a pak klikněte na **formát ovládacího prvku**.  
  
3.  V **formát ovládacího prvku** dialogové okno, klikněte **vlastnosti** kartě.  
  
4.  V části **umístění objektu**, vyberte **přesunout a velikosti** a potom klikněte na **OK**.  
  
     Změna velikosti buněk, který obsahuje ovládací prvek ovládacího prvku přizpůsobí buňky.  
  
## <a name="resizing-controls-at-run-time"></a>Změna velikosti ovládacích prvků za běhu  
 Pokud přidáte ovládacího prvku Windows Forms v době běhu a předat <xref:Microsoft.Office.Interop.Excel.Range> jako umístění pro ovládací prvek, bude ovládací prvek automaticky přizpůsobit při změně velikosti buňky listu, která obsahuje rozsah.  
  
#### <a name="to-make-controls-resize-with-cells-at-run-time"></a>Chcete-li změnit velikost s buňkami v době běhu – ovládací prvky  
  
1.  Přidání ovládacího prvku na rozsah A1.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#5](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#5)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#5)]  
  
     Změna velikosti buněk, který obsahuje ovládací prvek ovládacího prvku přizpůsobí buňky.  
  
## <a name="resetting-control-placement"></a>Resetování umístění ovládacího prvku  
 Můžete resetovat umístění a změna velikosti ovládacího prvku nastavením `Placement` vlastnost na jednu z následujících <xref:Microsoft.Office.Interop.Excel.XlPlacement> hodnoty:  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMove>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMoveAndSize>  
  
#### <a name="to-change-the-behavior-of-a-control-so-that-it-does-not-resize-or-move-with-the-cell"></a>Chcete-li změnit chování ovládacího prvku tak, aby není změna velikosti nebo přesunutí s buňky  
  
1.  Volání vlastnosti umístění ovládacího prvku a nastavte hodnotu na <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#6](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#6)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#6)]  
  
## <a name="see-also"></a>Viz také  
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Postupy: Přidání ovládacích prvků do dokumentů Office Windows Forms](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Postupy: skrytí ovládacích prvků na listech při tisku](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Omezení ovládacích prvků modelu Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  