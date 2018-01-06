---
title: "Xmlmappedrange – ovládací prvek | Microsoft Docs"
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
- XMLMappedRange control, data binding
- XMLMappedRange control
- XMLMappedRange control, events
ms.assetid: af1ae1b7-6cbe-4d6b-bc22-d9a3c8740665
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 27cd0f62c7670d56143180d24074e5c6002051f7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="xmlmappedrange-control"></a>XmlMappedRange – ovládací prvek
  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Řízení je rozsah, který je vytvořen pouze v případě, že element bez opakování schématu je namapovaný na buňku v aplikaci Microsoft Office Excel. Například když `maxOccurs` atribut elementu schématu se rovná 1. Po Visual Studio vytvoří XML mapovat rozsah, můžete je ovládat přímo bez nutnosti procházení model objektů aplikace Excel. Odstranit lze pouze <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládací prvek v rámci aplikace Excel, když dojde k odebrání mapování elementu.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést i pomocí XML mapování v aplikaci Excel?](http://go.microsoft.com/fwlink/?LinkID=130288).  
  
## <a name="binding-data-to-the-control"></a>Vazba dat k ovládacímu prvku  
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Řízení podporuje vazbu na jedno datové pole (jednoduché datové vazby). <xref:Microsoft.Office.Tools.Excel.ListObject> Řízení může podporuje rozšířené datové vazby a se automaticky vytvoří při opakovaných element schématu je namapovaný na buňku. Další informace najdete v tématu [ListObject – ovládací prvek](../vsto/listobject-control.md).  
  
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Ovládací prvek je vázána na zdroje dat pomocí <xref:System.Windows.Forms.Control.DataBindings%2A> vlastnost. Když <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> se přidá do buňky listu, Visual Studio automaticky generuje datové sady z dat v mapovaných buněk a sváže s této datové sady. Výchozí vlastnosti vazby dat z <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> je <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Value2%2A>.  
  
 Pokud data v vázané datové sady se aktualizují pomocí jakéhokoli mechanismu <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládací prvek odráží změny.  
  
## <a name="formatting"></a>Formátování  
 Můžete použít stejné formátování pro <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládací prvek, který lze použít <xref:Microsoft.Office.Interop.Excel.Range>. To zahrnuje ohraničení, písma, číselném formátu a stylů.  
  
## <a name="events"></a>Události  
 K dispozici pro události <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> řízení, představují:  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Deselected>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.SelectionChange>  
  
## <a name="see-also"></a>Viz také  
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Postupy: Přidání ovládacích prvků XMLMappedRange do listů](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Postupy: mapování schémat na listy v sadě Visual Studio](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  