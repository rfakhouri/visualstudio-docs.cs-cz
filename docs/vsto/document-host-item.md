---
title: "Hostitelská položka dokumentů | Microsoft Docs"
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
- documents [Office development in Visual Studio]
- documents [Office development in Visual Studio], document host items
- document host items
- Word [Office development in Visual Studio], Word documents
- Word [Office development in Visual Studio]
- Word documents
- host items [Office development in Visual Studio], Document
ms.assetid: 4c1963f2-e88e-4c68-9f3d-13dedebddde4
caps.latest.revision: "47"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: de243ee4b36d180b93e1b64f2a08c013a05d5360
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="document-host-item"></a>Hostitelská položka Document
  <xref:Microsoft.Office.Tools.Word.Document> Hostitelská položka je typ, který rozšiřuje <xref:Microsoft.Office.Interop.Word.Document> typu ze sestavení primární spolupráce pro aplikaci Word. <xref:Microsoft.Office.Tools.Word.Document> Hostitelská položka poskytuje všechny stejné vlastnosti, metod a události <xref:Microsoft.Office.Interop.Word.Document> objektu, ale také zpřístupní další události a slouží jako kontejner pro hostitele a ovládacích prvků Windows Forms.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 V projektech na úrovni dokumentu, je výchozí <xref:Microsoft.Office.Tools.Word.Document> položky hostitele, který představuje dokument ve vašem projektu. V doplňku VSTO projekty, můžete vygenerovat <xref:Microsoft.Office.Tools.Word.Document> hostitele položky v době běhu.  
  
## <a name="understanding-the-document-host-item-in-document-level-projects"></a>Principy hostitelská položka Document v projekty na úrovni dokumentu  
 Chcete-li získat přístup k dokumentu v projektu, použijte `ThisDocument` třídy. Když vytvoříte projekt na úrovni dokumentu a, Visual Studio vygeneruje `ThisDocument` třída, která bude sloužit jako datový spoj mezi Word a přizpůsobení kódu. `ThisDocument` Třída umožňuje přístup k členy <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka provádět základní úkoly ve vašem vlastním přizpůsobení, jako je například spuštění kódu, když je dokument otevřít nebo uzavřený. Třídu můžete použít také k přidání ovládacích prvků do dokumentu. Kombinování různé sady ovládacích prvků a psaní kódu, že ovládací prvky můžete vázat na data, shromáždit informace od uživatele a reagovat na akce uživatele. Další informace najdete v tématu [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).  
  
 `ThisDocument` Třída poskytuje umístění, ve kterém můžete spustit psaní kódu v projektu. Protože třída poskytuje všechny stejné vlastnosti, metod a události, jako <xref:Microsoft.Office.Interop.Word.Document> objekt v primárních sestavení vzájemné spolupráce pro Word, můžete použít také `ThisDocument` pro přístup k modelu objektů aplikace Word. Další informace najdete v tématu [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md).  
  
### <a name="limitations-of-the-document-host-item-in-document-level-projects"></a>Omezení hostitelská položka Document v projekty na úrovni dokumentu  
 Projekt na úrovni dokumentu a může obsahovat jenom jednu <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka (to znamená `ThisDocument` třídy). Nelze přidat nové <xref:Microsoft.Office.Tools.Word.Document> hostitele položek do projektu v době návrhu a nelze vytvořit nový <xref:Microsoft.Office.Tools.Word.Document> hostitele položky v době běhu z přizpůsobení na úrovni dokumentu.  
  
 Pokud vytvoříte nový dokument aplikace Word v době běhu, bude typu <xref:Microsoft.Office.Interop.Word.Document>. Protože není položku hostitele, nemůže obsahovat žádné hostitelské ovládací prvky nebo ovládací prvky Windows Forms. Další informace o vytváření dokumentů v době běhu najdete v tématu [postupy: Programové vytvoření nových dokumentů](../vsto/how-to-programmatically-create-new-documents.md).  
  
## <a name="understanding-document-host-items-in-application-level-projects"></a>Hostitelské položky dokumentů Principy v projektech na úrovni aplikace  
 V doplňku VSTO projekty, můžete vygenerovat <xref:Microsoft.Office.Tools.Word.Document> hostitele položky v době běhu pro všechny dokumentu, který je otevřený v aplikaci Word. Můžete použít <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka k přidávání ovládacích prvků v přidružené dokumentu nebo ke zpracování událostí, které nejsou k dispozici na <xref:Microsoft.Office.Interop.Word.Document> objekty.  
  
 Generovat <xref:Microsoft.Office.Tools.Word.Document> hostitele položek, použijte getvstoobject – metoda. Další informace najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)  
  
  