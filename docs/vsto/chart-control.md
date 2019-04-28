---
title: Graf – ovládací prvek
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.ProjectItem.ExcelChart
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Chart control [Office development in Visual Studio], events
- Chart control [Office development in Visual Studio]
- Chart control [Office development in Visual Studio], data binding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 21ca64f6661c4f0d7182bf20887ff8bdf754a6fc
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440316"
---
# <a name="chart-control"></a>Graf – ovládací prvek
  <xref:Microsoft.Office.Tools.Excel.Chart> Je ovládací prvek grafu objektu, který zpřístupňuje události. Když přidáte grafu na listu, vytvoří Visual Studio <xref:Microsoft.Office.Tools.Excel.Chart> objektu, můžete programovat proti přímo bez nutnosti procházení objektový model aplikace Microsoft Office Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="create-the-control"></a>Vytvoření ovládacího prvku
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.Chart> ovládacích prvků na list aplikace Microsoft Office Excel v době návrhu nebo za běhu v projektu úrovni dokumentu.

 Můžete přidat <xref:Microsoft.Office.Tools.Excel.Chart> ovládacích prvků na list za běhu v doplňku VSTO. Další informace najdete v tématu [jak: Přidání ovládacích prvků graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md).

> [!NOTE]
> Nejsou trvalé objekty dynamicky generovaný grafu v listu jako hostitele Určuje, kdy je uzavřen do listu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).

## <a name="formatting"></a>Formátování
 Veškeré formátování, který lze použít <xref:Microsoft.Office.Interop.Excel.Chart> lze také použít u <xref:Microsoft.Office.Tools.Excel.Chart> ovládacího prvku. To zahrnuje ohraničení, písma, grafy, mřížky, legendy a popisky dat.

## <a name="events"></a>Události
 Tyto události jsou k dispozici pro <xref:Microsoft.Office.Tools.Excel.Chart> ovládacího prvku:

- <xref:Microsoft.Office.Tools.Excel.Chart.ActivateEvent>

- <xref:Microsoft.Office.Tools.Excel.Chart.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Excel.Chart.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Excel.Chart.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Excel.Chart.Calculate>

- <xref:Microsoft.Office.Tools.Excel.Chart.Deactivate>

- <xref:System.ComponentModel.Component.Disposed>

- <xref:Microsoft.Office.Tools.Excel.Chart.DragOver>

- <xref:Microsoft.Office.Tools.Excel.Chart.DragPlot>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseDown>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseMove>

- <xref:Microsoft.Office.Tools.Excel.Chart.MouseUp>

- <xref:Microsoft.Office.Tools.Excel.Chart.Resize>

- <xref:Microsoft.Office.Tools.Excel.Chart.SelectEvent>

- <xref:Microsoft.Office.Tools.Excel.Chart.SeriesChange>

## <a name="see-also"></a>Viz také:
- [Ukázky vývoje pro Office a názorné postupy](../vsto/office-development-samples-and-walkthroughs.md)
- [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)
- [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)
- [Postupy: Přidání ovládacích prvků graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md)
- [Vytvoření vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
