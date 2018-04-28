---
title: Automatizace v aplikaci Excel s použitím rozšířených objektů | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], automating
- automation [Office development in Visual Studio], Excel
- host controls, Excel
- Excel [Office development in Visual Studio], host controls
- extended objects [Office development in Visual Studio], Excel
- host controls [Office development in Visual Studio], Excel
- automating Excel
- host items [Office development in Visual Studio], Excel
- controls [Office development in Visual Studio], Excel host controls
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7c1111a9fdd66d99f1dda40d3045ad337d499a6a
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2018
---
# <a name="automating-excel-by-using-extended-objects"></a>Automatizace v aplikaci Excel s použitím rozšířených objektů
  Při vývoji řešení pro aplikaci Excel v sadě Visual Studio, můžete použít *hostitele položky* a *hostování ovládacího prvku*s v řešení. Jedná se o objekty, které rozšiřují určité běžně používané objekty ve model objektů aplikace Excel (tedy model objektu zveřejněného prostřednictvím primární spolupracující sestavení pro aplikaci Excel), jako například <xref:Microsoft.Office.Interop.Excel.Worksheet> a <xref:Microsoft.Office.Interop.Excel.Range> objekty. Rozšířené objekty chovají jako objekty aplikace Excel, které jsou založené na, ale jejich přidat další funkce, například nové události a možnosti vazby dat k objektům.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Jsou k dispozici v obou doplňku VSTO hostitelských položek a hostitelských ovládacích prvků a na úrovni dokumentu úprav, i když se liší pro jednotlivé typy řešení kontext, ve kterém ty mohou být použity. Další informace najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="excel-host-items"></a>Hostitelské položky aplikace Excel  
 Projekty aplikace Excel umožňují přístup k několika hostitelské položky:  
  
-   <xref:Microsoft.Office.Tools.Excel.Worksheet>. Tato položka hostitele obsahuje představuje list ve vašem projektu. Taky funguje jako kontejner pro spravované ovládací prvky, včetně hostitelů a ovládacích prvků Windows Forms, a udržuje informace o ovládacích prvcích na jeho povrchu. Další informace najdete v tématu [hostitelská položka Worksheet](../vsto/worksheet-host-item.md).  
  
-   <xref:Microsoft.Office.Tools.Excel.Workbook>. Tuto položku hostitele představuje sešit ve vašem projektu a slouží jako kontejner pro součásti, které jsou sdíleny všech listů v sešitu. Další informace najdete v tématu [hostitelská položka Workbook](../vsto/workbook-host-item.md).  
  
-   <xref:Microsoft.Office.Tools.Excel.ChartSheet>. Tento hostitel položky sešit v aplikaci Excel, která obsahuje jenom na graf a zpřístupní události.  
  
     Když přidáte list grafu v době návrhu jako nový list ve vašem projektu přizpůsobení na úrovni dokumentu aplikace Microsoft Office Excel, Visual Studio automaticky vytvoří <xref:Microsoft.Office.Tools.Excel.ChartSheet> hostitelská položka.  
  
     I když <xref:Microsoft.Office.Tools.Excel.ChartSheet> je hostitelská položka sešitu v aplikaci Excel, nelze přidat všech ovládacích prvků na list grafu. Pokud chcete mít jiných ovládacích prvků na list s grafem, nepoužívejte list grafu. Místo toho můžete umístit graf jako vložený objekt na listu s použitím <xref:Microsoft.Office.Tools.Excel.Chart> hostování ovládacího prvku. Další informace najdete v tématu [ovládací prvek graf](../vsto/chart-control.md).  
  
## <a name="excel-host-controls"></a>Hostitelské ovládací prvky aplikace Excel  
 Existuje několik hostitele ovládací prvky pro aplikaci Excel, které vám pomůžou vytvořit, organizovat a automatizovat sešity a listy. Tyto hostitelské ovládací prvky poskytují události a možnosti vazby dat, které nemají své protějšky v nativní model objektů aplikace Excel.  
  
 Další informace o hostitelských ovládacích prvcích můžete použít v projekty aplikace Excel, najdete v následujících tématech:  
  
-   [Graf – ovládací prvek](../vsto/chart-control.md)  
  
-   [ListObject – ovládací prvek](../vsto/listobject-control.md)  
  
-   [NamedRange – ovládací prvek](../vsto/namedrange-control.md)  
  
-   [XMLMappedRange – ovládací prvek](../vsto/xmlmappedrange-control.md)  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vyplnění ovládacích prvků ListObject daty](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Postupy: Přidání ovládacích prvků graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Postupy: Přidání ovládacích prvků XMLMappedRange do listů](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)   
 [Postupy: Změna velikosti ovládacích prvků ListObject](../vsto/how-to-resize-listobject-controls.md)   
 [Postupy: ověření dat při přidání nového řádku do ovládacího prvku ListObject](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)   
 [Postupy: mapování sloupců objektu ListObject na Data](../vsto/how-to-map-listobject-columns-to-data.md)   
 [Návod: Programové ošetření událostí ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  