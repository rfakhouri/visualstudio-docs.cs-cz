---
title: "Hostitelská položka Workbook | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel workbooks
- Workbook host items
- host items [Office development in Visual Studio], Workbook
- workbooks, Excel
- Workbook host items, events
- workbooks
- Excel [Office development in Visual Studio], workbooks
- workbooks, events
- events [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 1c1e6de8313b3e7b94ac88627ef3cdc463c92906
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="workbook-host-item"></a>Hostitelská položka Workbook
  <xref:Microsoft.Office.Tools.Excel.Workbook> Hostitelská položka je typ, který rozšiřuje <xref:Microsoft.Office.Interop.Excel.Workbook> typu ze sestavení primární spolupráce pro aplikaci Excel. <xref:Microsoft.Office.Tools.Excel.Workbook> Hostitelská položka poskytuje všechny stejné vlastnosti, metod a události <xref:Microsoft.Office.Interop.Excel.Workbook> objektu, ale také poskytuje další funkce.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 V projektech na úrovni dokumentu, je výchozí <xref:Microsoft.Office.Tools.Excel.Workbook> položky hostitele, který představuje sešit v projektu. V doplňku VSTO projekty, můžete vygenerovat <xref:Microsoft.Office.Tools.Excel.Workbook> hostitele položky v době běhu.  
  
## <a name="understanding-the-workbook-host-item-in-document-level-projects"></a>Principy hostitelská položka sešitu v projekty na úrovni dokumentu  
 Chcete-li získat přístup k sešitu v projektu, použijte `ThisWorkbook` třídy. `ThisWorkbook` Třída umožňuje přístup k členy <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelská položka provádět základní úkoly ve vašem vlastním přizpůsobení, jako je například spuštění kódu, když je sešit otevřít nebo uzavřený. Další informace najdete v tématu [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).  
  
 `ThisWorkbook` Třída poskytuje umístění, ve kterém můžete spustit psaní kódu v projektu. Protože třída poskytuje všechny stejné vlastnosti, metod a události, jako <xref:Microsoft.Office.Interop.Excel.Workbook> objektu v primární spolupracující sestavení pro aplikaci Excel, můžete použít také `ThisWorkbook` pro přístup k modelu objektů aplikace Excel. Další informace najdete v tématu [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).  
  
 Dvakrát klikněte **ThisWorkbook** položky projektu v **Průzkumníku řešení** k zobrazení návrháře sešit a zobrazit vlastnosti a události tohoto sešitu v **vlastnosti**okno.  
  
### <a name="limitations-of-the-workbook-host-item-in-document-level-projects"></a>Omezení hostitelská položka sešitu v projekty na úrovni dokumentu  
 Projekt na úrovni dokumentu a může obsahovat jenom jednu <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelská položka (to znamená `ThisWorkbook` třídy). Nelze přidat nové <xref:Microsoft.Office.Tools.Excel.Workbook> hostitele položek do projektu v době návrhu a nelze vytvořit nový <xref:Microsoft.Office.Tools.Excel.Workbook> hostitele položky v době běhu z přizpůsobení na úrovni dokumentu.  
  
 Pokud vytvoříte nový sešit aplikace Excel v době běhu, bude typu <xref:Microsoft.Office.Interop.Excel.Workbook>. Protože není položku hostitele, nemůže obsahovat žádné hostitelské ovládací prvky nebo ovládací prvky Windows Forms. Další informace o vytváření sešitů za běhu, najdete v části [postupy: Programové vytvoření nových sešitů](../vsto/how-to-programmatically-create-new-workbooks.md).  
  
 <xref:Microsoft.Office.Tools.Excel.Workbook> Hostitelská položka není fungovat jako kontejner pro hostitelské ovládací prvky. Proto všechny ovládací prvky viditelné nelze přidat k sešitu, ale můžete přidat součásti, například <xref:System.Data.DataSet>tak, aby komponenty může být sdílen všech listů. V projektech na úrovni dokumentu, součásti, které jsou k dispozici pro sešit naleznete na **součást** kartě **Data** kartě a **všechny formuláře Windows** kartě  **Sada nástrojů**.  
  
> [!NOTE]  
>  Nástroje pro vývoj pro Office v sadě Visual Studio nepodporuje sdílené sešity.  
  
## <a name="understanding-workbook-host-items-in-vsto-add-in-projects"></a>Hostitelská položka sešitu Principy projekty doplňku VSTO  
 V doplňku VSTO projekty, můžete vygenerovat <xref:Microsoft.Office.Tools.Excel.Workbook> hostitele položky v době běhu pro všechny sešit, který je otevřít v aplikaci Excel. Generovat <xref:Microsoft.Office.Tools.Excel.Workbook> hostitele položek, použijte getvstoobject – metoda. Další informace najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="see-also"></a>Viz také  
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  