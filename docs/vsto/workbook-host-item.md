---
title: Hostitelská položka Workbook
ms.date: 02/02/2017
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: f15d93818c2db553d22d9639e6460f6637d33c80
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53952862"
---
# <a name="workbook-host-item"></a>Hostitelská položka Workbook
  <xref:Microsoft.Office.Tools.Excel.Workbook> Hostitelský objekt je typ, který rozšiřuje <xref:Microsoft.Office.Interop.Excel.Workbook> typu ze sestavení primární spolupráce pro aplikaci Excel. <xref:Microsoft.Office.Tools.Excel.Workbook> Hostitelský objekt poskytuje všechny stejné vlastnosti, metody a události <xref:Microsoft.Office.Interop.Excel.Workbook> objektu, ale poskytuje taky další funkce.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 V projektech na úrovni dokumentu, je výchozí <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelský objekt, který představuje sešitu ve vašem projektu. V doplňku VSTO projektů, můžete vygenerovat <xref:Microsoft.Office.Tools.Excel.Workbook> hostovat položky v době běhu.  
  
## <a name="understand-the-workbook-host-item-in-document-level-projects"></a>Vysvětlení hostitelská položka workbook v projektech na úrovni dokumentu  
 Chcete-li získat přístup k sešitu ve vašem projektu, použijte `ThisWorkbook` třídy. `ThisWorkbook` Třída poskytuje přístup k členům <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelský objekt pro provádění základních úloh ve vašem vlastním přizpůsobení, jako je například spuštění kódu, když je sešit otevřena nebo zavřena. Další informace najdete v tématu [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).  
  
 `ThisWorkbook` Třída poskytuje umístění, ve kterém můžete začít psát kód ve vašem projektu. Protože třída poskytuje všechny stejné vlastnosti, metody a události, jako <xref:Microsoft.Office.Interop.Excel.Workbook> ve primárního spolupracujícího sestavení pro aplikaci Excel, objekt, můžete použít také `ThisWorkbook` pro přístup k modelu objektů aplikace Excel. Další informace najdete v tématu [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).  
  
 Dvakrát klikněte na panel **ThisWorkbook** položky projektu v **Průzkumníku řešení** zobrazíte Návrhář sešitů a chcete-li zobrazit vlastnosti a události v sešitu **vlastnosti**okna.  
  
### <a name="limitations-of-the-workbook-host-item-in-document-level-projects"></a>Omezení hostitelská položka workbook v projektech na úrovni dokumentu  
 Úrovni dokumentu projekt může obsahovat jenom jednu <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelský objekt (to znamená, `ThisWorkbook` třídy). Nelze přidat nový <xref:Microsoft.Office.Tools.Excel.Workbook> hostitele položky do projektu v době návrhu a nelze vytvořit nový <xref:Microsoft.Office.Tools.Excel.Workbook> hostovat položky v době běhu z přizpůsobení úrovni dokumentu.  
  
 Pokud vytvoříte nový sešit aplikace Excel v době běhu, budou typu <xref:Microsoft.Office.Interop.Excel.Workbook>. Protože se nejedná hostitelská položka, nemůže obsahovat všechny hostitelské ovládací prvky nebo ovládacích prvků Windows Forms. Další informace o vytváření sešitů za běhu, naleznete v tématu [jak: Vytváření nových sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-workbooks.md).  
  
 <xref:Microsoft.Office.Tools.Excel.Workbook> Hostitelský objekt nepostupuje jako kontejner pro hostitelské ovládací prvky. Proto všechny viditelné ovládací prvky nelze přidat do sešitu, ale můžete přidat komponenty, například <xref:System.Data.DataSet>tak, aby komponenty mohou sdílet všechny listy. V projektu úrovni dokumentu součásti, které jsou k dispozici v sešitu můžete najít na **komponenty** kartě **Data** kartu, a **všechny formuláře Windows** kartě  **Panel nástrojů**.  
  
> [!NOTE]  
>  Vývojářské nástroje balíku Office v sadě Visual Studio sdílené sešity nepodporuje.  
  
## <a name="understand-workbook-host-items-in-vsto-add-in-projects"></a>Vysvětlení položek hostitele pracovního sešitu v projekty doplňků VSTO  
 V doplňku VSTO projektů, můžete vygenerovat <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelský objekt za běhu pro libovolný sešit, který je otevřen v aplikaci Excel. Ke generování <xref:Microsoft.Office.Tools.Excel.Workbook> hostitelský objekt, použijte `GetVstoObject` metody. Další informace najdete v tématu [rozšíření Wordových dokumentů a Excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="see-also"></a>Viz také:  
 [Ukázky vývoje pro Office a názorné postupy](../vsto/office-development-samples-and-walkthroughs.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
