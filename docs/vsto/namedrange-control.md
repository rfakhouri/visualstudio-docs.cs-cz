---
title: "NamedRange – ovládací prvek | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.Toolbox.Range
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, named
- NamedRange control, events
- NamedRange control, data binding
- NamedRange control
ms.assetid: 07878c7c-cb5a-4f98-95c4-e828de25dae5
caps.latest.revision: "56"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 42914166995c002d7eeb0c1c730edf860e6c1a68
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="namedrange-control"></a>NamedRange – ovládací prvek
  <xref:Microsoft.Office.Tools.Excel.NamedRange> Řízení je rozsah, který se má jedinečný název, zpřístupní události a mohou být vázány na data. Další informace najdete v tématu [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="creating-the-control"></a>Vytvoření ovládacího prvku  
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacích prvků na list aplikace Microsoft Office Excel v době návrhu nebo za běhu v projekty na úrovni dokumentu.  
  
 Můžete přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacích prvků na list za běhu v doplňku VSTO. Další informace najdete v tématu [postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Ve výchozím nastavení, nejsou trvalé dynamicky vytvořený pojmenované oblasti v listu jako umisťování ovládacích prvků při uzavření listu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 <xref:Microsoft.Office.Tools.Excel.NamedRange>ovládací prvky může obsahovat jenom na konkrétní listy rozsahů. <xref:Microsoft.Office.Tools.Excel.NamedRange>ovládací prvky nemohou mít relativních názvů, které platí pro všechny listy a nesmí se skládat z rozsahů, které jsou rozmístěny dva nebo víc listů v sešitech (3D rozsahy).  
  
## <a name="binding-data-to-the-control"></a>Vazba dat k ovládacímu prvku  
 Pojmenované oblasti zdají být vhodným kandidátem pro rozšířené datové vazby, protože může mít velké množství buněk; rozsah je však pouze o sadu buněk, které nelze mapovat snadno na konkrétní sloupce z datové sady. Proto <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvky podporují jenom jednoduché datové vazby. <xref:Microsoft.Office.Tools.Excel.ListObject> Řízení lze použít pro rozšířené datové vazby. Další informace najdete v tématu [ListObject – ovládací prvek](../vsto/listobject-control.md).  
  
 <xref:Microsoft.Office.Tools.Excel.NamedRange> Může být vázán k zdroje dat pomocí <xref:System.Windows.Forms.Control.DataBindings%2A> vlastnosti. Výchozí vlastnosti vazby dat z <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek je <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A>.  
  
 Pokud aktualizaci dat v datové sadě vázané prostřednictvím jakéhokoli mechanismu <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek odráží změny.  
  
## <a name="formatting"></a>Formátování  
 Formátování, které lze použít pro <xref:Microsoft.Office.Interop.Excel.Range> lze použít pro <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku. To zahrnuje ohraničení, písma, číselném formátu a styly.  
  
## <a name="renaming-the-control"></a>Přejmenování ovládacího prvku  
 Když přidáte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do listu z **sada nástrojů**, Visual Studio automaticky vygeneruje název ovládacího prvku. Můžete změnit název v **vlastnosti** okno.  
  
## <a name="events"></a>Události  
 Tyto události jsou k dispozici pro <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku:  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Deselected>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange>  
  
## <a name="see-also"></a>Viz také  
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)   
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Návod: Programové ošetření událostí ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  