---
title: Hostitelská položka Worksheet
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- host items [Office development in Visual Studio], Worksheet
- Excel [Office development in Visual Studio], worksheets
- Worksheet host items
- worksheets, events
- Worksheet host items, events
- Excel worksheets
- worksheets, Excel
- worksheets
- events [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e4a5287648d515d1aca340ab55d5f21b494610b5
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56612475"
---
# <a name="worksheet-host-item"></a>Hostitelská položka Worksheet
  <xref:Microsoft.Office.Tools.Excel.Worksheet> Hostitelský objekt je typ, který rozšiřuje <xref:Microsoft.Office.Interop.Excel.Worksheet> typu ze sestavení primární spolupráce pro aplikaci Excel. <xref:Microsoft.Office.Tools.Excel.Worksheet> Hostitelský objekt poskytuje všechny stejné vlastnosti, metody a události <xref:Microsoft.Office.Interop.Excel.Worksheet> objektu, ale také poskytuje další události a funguje jako kontejner pro hostitelské ovládací prvky a ovládací prvky Windows Forms.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Projekty na úrovni dokumentu, můžete přidat <xref:Microsoft.Office.Tools.Excel.Worksheet> hostovat položky do projektu v době návrhu. V doplňku VSTO projektů, můžete vygenerovat <xref:Microsoft.Office.Tools.Excel.Worksheet> hostovat položky v době běhu.

## <a name="understand-worksheet-host-items-in-document-level-projects"></a>Vysvětlení list – hostitelské položky v projektech na úrovni dokumentu
 Při vytváření projektu úrovni dokumentu pro Excel, sada Visual Studio automaticky vytvoří tři <xref:Microsoft.Office.Tools.Excel.Worksheet> hostovat položky v projektu. Výchozí názvy z listů `Sheet1`, `Sheet2`, a `Sheet3`. Pokud vytvoříte projekt založený na existující sešit, počet položek hostitele, které závisí na počtu listů v sešitu.

 Tyto třídy list poskytují přístup k členům <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt pro provádění základních úloh ve vašem vlastním přizpůsobení, jako je třeba změna obsah listu. Tyto třídy můžete také použít k přidávání ovládacích prvků na listech. Díky kombinaci různých sad ovládací prvky a psaní kódu, že můžete svázat ovládací prvky k datům, shromažďování informací od uživatele a reagovat na akce uživatele. Další informace najdete v tématu [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).

 Tříd listu zadat umístění, ve kterém můžete začít psát kód ve vašem projektu. Protože třída poskytuje všechny stejné vlastnosti, metody a události, jako <xref:Microsoft.Office.Interop.Excel.Worksheet> objektu ve primárního spolupracujícího sestavení pro aplikaci Excel, tyto třídy můžete také použít pro přístup k modelu objektů aplikace Excel. Další informace najdete v tématu [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).

 V projektech na úrovni dokumentu, můžete přidat další <xref:Microsoft.Office.Tools.Excel.Worksheet> hostovat položky do projektu v době návrhu tak, že přidáte do nového listu v sešitu v návrháři.

### <a name="rename-worksheets"></a>Přejmenovat listů
 V projektu úrovni dokumentu můžete přejmenovat listů v návrháři aplikace Visual Studio, ale pouze změní zobrazovaný název listu. Výchozí název listu je stále programový název. Pokud přejmenujete do listu **vlastnosti** okno programový název se změní.

### <a name="limitations-of-the-worksheet-host-item-in-document-level-projects"></a>Omezení hostitelská položka worksheet v projektech na úrovni dokumentu
 Nelze vytvořit nový <xref:Microsoft.Office.Tools.Excel.Worksheet> hostovat položky za běhu v projektu úrovni dokumentu. Pokud vytvoříte nový Excelový list za běhu, budou typu <xref:Microsoft.Office.Interop.Excel.Worksheet>. Protože se nejedná hostitelská položka, nemůže obsahovat všechny hostitelské ovládací prvky nebo ovládacích prvků Windows Forms. Další informace o vytváření dokumentů v době běhu, naleznete v tématu [jak: Přidávání nových listů do sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md).

## <a name="understand-worksheet-host-items-in-vsto-add-in-projects"></a>Vysvětlení list – hostitelské položky v projekty doplňků VSTO
 V projektech na úrovni aplikace, můžete vygenerovat <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelské položky v době běhu pro jakékoli list, který je otevřen v aplikaci Excel. Můžete použít <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt k přidávání ovládacích prvků do přidružené listu, nebo pro zpracování událostí, které nejsou k dispozici na <xref:Microsoft.Office.Interop.Excel.Worksheet> objekty.

 Ke generování <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt, použijte `GetVstoObject` metody. Další informace najdete v tématu [rozšíření Wordových dokumentů a Excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

## <a name="see-also"></a>Viz také:
- [Ukázky vývoje pro Office a názorné postupy](../vsto/office-development-samples-and-walkthroughs.md)
- [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)
- [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
- [Hostitelská položka Workbook](../vsto/workbook-host-item.md)
- [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
