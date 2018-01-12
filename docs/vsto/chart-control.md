---
title: "Ovládací prvek grafu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.ProjectItem.ExcelChart
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Chart control [Office development in Visual Studio], events
- Chart control [Office development in Visual Studio]
- Chart control [Office development in Visual Studio], data binding
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9acd6d07a44ce853bcf7330d16585e1231640d48
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="chart-control"></a>Graf – ovládací prvek
  <xref:Microsoft.Office.Tools.Excel.Chart> Ovládací prvek je objekt graf, který zpřístupní události. Když přidáte graf do listu, Visual Studio vytvoří <xref:Microsoft.Office.Tools.Excel.Chart> objektu, že můžete naprogramovat oproti přímo bez nutnosti procházení objektový model aplikace Microsoft Office Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="creating-the-control"></a>Vytvoření ovládacího prvku  
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.Chart> ovládacích prvků na list aplikace Microsoft Office Excel v době návrhu nebo za běhu v projektech na úrovni dokumentu.  
  
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.Chart> ovládacích prvků na list za běhu v doplňku VSTO. Další informace najdete v tématu [postupy: Přidání ovládacích prvků graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Dynamicky vytvořený graf objekty nejsou trvalé do listu jako umisťování ovládacích prvků při uzavření listu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="formatting"></a>Formátování  
 Veškeré formátování, který lze použít k <xref:Microsoft.Office.Interop.Excel.Chart> lze použít také k <xref:Microsoft.Office.Tools.Excel.Chart> ovládacího prvku. To zahrnuje ohraničení, písma, typ grafu, mřížky, legendy a popisky dat.  
  
## <a name="events"></a>Události  
 Tyto události jsou k dispozici pro <xref:Microsoft.Office.Tools.Excel.Chart> ovládacího prvku:  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.ActivateEvent>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Calculate>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Deactivate>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.DragOver>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.DragPlot>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseDown>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseMove>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseUp>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Resize>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.SelectEvent>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.SeriesChange>  
  
## <a name="see-also"></a>Viz také  
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Postupy: Přidání ovládacích prvků graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  