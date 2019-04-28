---
title: Hostitelská položka Document
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio]
- documents [Office development in Visual Studio], document host items
- document host items
- Word [Office development in Visual Studio], Word documents
- Word [Office development in Visual Studio]
- Word documents
- host items [Office development in Visual Studio], Document
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8710fb703b353b267e7057973865cf845ebf79a9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62976493"
---
# <a name="document-host-item"></a>Hostitelská položka Document
  <xref:Microsoft.Office.Tools.Word.Document> Hostitelský objekt je typ, který rozšiřuje <xref:Microsoft.Office.Interop.Word.Document> typu ze sestavení primární spolupráce pro aplikaci Word. <xref:Microsoft.Office.Tools.Word.Document> Hostitelský objekt poskytuje všechny stejné vlastnosti, metody a události <xref:Microsoft.Office.Interop.Word.Document> objektu, ale také poskytuje další události a funguje jako kontejner pro hostitelské ovládací prvky a ovládací prvky Windows Forms.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 V projektech na úrovni dokumentu, je výchozí <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt, který představuje dokument v projektu. V doplňku VSTO projektů, můžete vygenerovat <xref:Microsoft.Office.Tools.Word.Document> hostovat položky v době běhu.

## <a name="understand-the-document-host-item-in-document-level-projects"></a>Vysvětlení hostitelská položka document v projektech na úrovni dokumentu
 Chcete-li získat přístup k dokumentu v projektu, použijte `ThisDocument` třídy. Při vytváření projektu úrovni dokumentu aplikace Visual Studio vygeneruje `ThisDocument` třída, která bude sloužit jako komunikační propojení mezi aplikace Word a přizpůsobení kódu. `ThisDocument` Třída poskytuje přístup k členům <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt pro provádění základních úloh ve vašem vlastním přizpůsobení, jako je například spuštění kódu, když je dokument otevřel nebo zavřel. Třídu můžete použít také k přidávání ovládacích prvků do dokumentu. Díky kombinaci různých sad ovládací prvky a psaní kódu, že můžete svázat ovládací prvky k datům, shromažďování informací od uživatele a reagovat na akce uživatele. Další informace najdete v tématu [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).

 `ThisDocument` Třída poskytuje umístění, ve kterém můžete začít psát kód ve vašem projektu. Protože třída poskytuje všechny stejné vlastnosti, metody a události, jako <xref:Microsoft.Office.Interop.Word.Document> ve primárního spolupracujícího sestavení pro aplikaci Word, objekt, můžete použít také `ThisDocument` pro přístup k modelu objektů aplikace Word. Další informace najdete v tématu [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md).

### <a name="limitations-of-the-document-host-item-in-document-level-projects"></a>Omezení hostitelská položka document v projektech na úrovni dokumentu
 Úrovni dokumentu projekt může obsahovat jenom jednu <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt (to znamená, `ThisDocument` třídy). Nelze přidat nový <xref:Microsoft.Office.Tools.Word.Document> hostitele položky do projektu v době návrhu a nelze vytvořit nový <xref:Microsoft.Office.Tools.Word.Document> hostovat položky v době běhu z přizpůsobení úrovni dokumentu.

 Pokud vytvoříte nový Wordový dokument v době běhu, budou typu <xref:Microsoft.Office.Interop.Word.Document>. Protože se nejedná hostitelská položka, nemůže obsahovat všechny hostitelské ovládací prvky nebo ovládacích prvků Windows Forms. Další informace o vytváření dokumentů v době běhu, naleznete v tématu [jak: Vytváření nových dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-documents.md).

## <a name="understand-document-host-items-in-application-level-projects"></a>Vysvětlení položek hostitele dokumentu v projektech na úrovni aplikace
 V doplňku VSTO projektů, můžete vygenerovat <xref:Microsoft.Office.Tools.Word.Document> hostitelské položky v době běhu pro některé odeslaný dokument je otevřen v aplikaci Word. Můžete použít <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt přidání ovládacích prvků do bude příslušný dokument nebo zpracování události, které nejsou k dispozici na <xref:Microsoft.Office.Interop.Word.Document> objekty.

 Ke generování <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt, použijte `GetVstoObject` metody. Další informace najdete v tématu [rozšíření Wordových dokumentů a Excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

## <a name="see-also"></a>Viz také:
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
- [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)
- [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
