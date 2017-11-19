---
title: "Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu | Microsoft Docs"
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
- GetVstoObject method
- application-level add-ins [Office development in Visual Studio], adding controls to documents
- host items [Office development in Visual Studio], creating at run time in add-ins
- application-level add-ins [Office development in Visual Studio], extending Word documents
- application-level add-ins [Office development in Visual Studio], extending Excel workbooks
- controls [Office development in Visual Studio], adding at run time
- HasVstoObject method
ms.assetid: c1607314-4cf8-439c-b4c5-709db8b71cff
caps.latest.revision: "61"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93010f03384e3cb3930911115ee92b3bb9205b9e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time"></a>Rozšíření wordových dokumentů a excelových sešitů v doplňcích VSTO za běhu
  Doplňku VSTO můžete použít k přizpůsobení dokumentů aplikace Word a sešitů aplikace Excel následujícími způsoby:  
  
-   Přidání spravovaných ovládacích prvků do všechny otevřené dokumenty a listu.  
  
-   Převést stávající seznamu objektu na listu aplikace Excel na rozšířená <xref:Microsoft.Office.Tools.Excel.ListObject> který zpřístupní události a může být vázána k datům pomocí vazby modelu Windows Forms data.  
  
-   Přístup úrovni aplikace události, které jsou vystavené Word a Excel pro konkrétní dokumentům, sešitům a listů.  
  
 Chcete-li používat tuto funkci, vygenerovat objektu v době běhu, který rozšiřuje dokumentu nebo sešitu.  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty doplňku VSTO pro následující aplikace: Excel a Word. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  
  
## <a name="generating-extended-objects-in-vsto-add-ins"></a>Vytváření rozšířených objektů v doplňcích VSTO  
 *Rozšířené objekty* jsou instancemi typů poskytované sady Visual Studio Tools pro systém Office runtime, které zajišťují funkce objekty, které nativně existovat v objektové modely Word či Excel (nazývá *nativních objektů Office*). Chcete-li vygenerovat rozšířené objektu pro objekt Word či Excel, použijte getvstoobject – metoda. Při prvním volání metody getvstoobject – pro zadaný objekt Word či Excel, vrátí nový objekt, který rozšiřuje zadaný objekt. Pokaždé, když volat metodu a zadejte stejné aplikace Word nebo v aplikaci Excel na objekt, vrátí stejný objekt rozšířené.  
  
 Typ objektu rozšířené má stejný název jako typ objektu pro nativní Office, ale tento typ je definovaný v <xref:Microsoft.Office.Tools.Excel> nebo <xref:Microsoft.Office.Tools.Word> oboru názvů. Například, pokud volání getvstoobject – metoda rozšíření <xref:Microsoft.Office.Interop.Word.Document> objektu, vrátí metoda <xref:Microsoft.Office.Tools.Word.Document> objektu.  
  
 Getvstoobject – metody jsou určeny k použije především na projekty doplňku VSTO. Můžete také použít tyto metody v projekty na úrovni dokumentu, ale chovat jinak a máte méně používá.  
  
 Pokud chcete zjistit, zda objekt rozšířené už je vygenerovaný pro konkrétní objekt nativní Office, použijte metodu hasvstoobject –. Další informace najdete v tématu [určení, zda Office objekt rozšířilo](#HasVstoObject).  
  
### <a name="generating-host-items"></a>Generování hostitelské položky  
 Při použití getvstoobject – rozšířit o objekt na úrovni dokumentu (to znamená, <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, nebo <xref:Microsoft.Office.Interop.Word.Document>), se nazývá vráceného objektu *hostitelská položka*. Hostitelská položka je typ, který může obsahovat jiné objekty, včetně jiných rozšířených objektů a ovládacích prvků. Je podobná odpovídající typ v Word či Excel primární spolupracující sestavení, ale má další funkce. Další informace o hostitelských položkách najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
 Po vygenerování hostitelskou položku můžete přidat spravovaných ovládacích prvků do dokumentu, sešitu nebo listu. Další informace najdete v tématu [Přidání spravované ovládací prvky k dokumentům a listů](#AddControls).  
  
##### <a name="to-generate-a-host-item-for-a-word-document"></a>Generovat položku hostitele pro dokument aplikace Word  
  
-   Následující příklad kódu ukazuje, jak vygenerovat položku hostitele pro aktivní dokument.  
  
     [!code-vb[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#8)]
     [!code-csharp[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#8)]  
  
##### <a name="to-generate-a-host-item-for-an-excel-workbook"></a>Generovat položku hostitel pro sešit aplikace Excel  
  
-   Následující příklad kódu ukazuje, jak generovat položku hostitele pro aktivním sešitu.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#2)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#2)]  
  
##### <a name="to-generate-a-host-item-for-an-excel-worksheet"></a>Generovat položku hostitele pro listu aplikace Excel  
  
-   Následující příklad kódu ukazuje, jak vygenerovat položku hostitele pro aktivního listu v projektu.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#1)]  
  
### <a name="generating-listobject-host-controls"></a>Generování ListObject hostitelské ovládací prvky  
 Při použití getvstoobject – metoda rozšíření <xref:Microsoft.Office.Interop.Excel.ListObject>, vrátí metoda <xref:Microsoft.Office.Tools.Excel.ListObject>. <xref:Microsoft.Office.Tools.Excel.ListObject> Obsahuje všechny funkce původního <xref:Microsoft.Office.Interop.Excel.ListObject>, ale má také další funkce, například možnost bylo vázané na data pomocí vazby modelu Windows Forms data. Další informace najdete v tématu [ListObject – ovládací prvek](../vsto/listobject-control.md).  
  
##### <a name="to-generate-a-host-control-for-a-listobject"></a>Generovat hostitelského ovládacího prvku pro ListObject  
  
-   Následující příklad kódu ukazuje, jak vygenerovat <xref:Microsoft.Office.Tools.Excel.ListObject> pro první <xref:Microsoft.Office.Interop.Excel.ListObject> v aktivním listu v projektu.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#3)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#3)]  
  
##  <a name="AddControls"></a>Přidání spravované ovládací prvky k dokumentům a listů  
 Po vygenerování <xref:Microsoft.Office.Tools.Word.Document> nebo <xref:Microsoft.Office.Tools.Excel.Worksheet>, můžete přidat ovládací prvky v dokumentu nebo listu, která tyto rozšířené objekty představují. K tomu použít vlastnost ovládacích prvků <xref:Microsoft.Office.Tools.Word.Document> nebo <xref:Microsoft.Office.Tools.Excel.Worksheet>. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Můžete přidat ovládací prvky Windows Forms nebo *hostování ovládacích prvků*. Řízení hostitele je ovládací prvek poskytované [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] který zabalí odpovídající ovládacího prvku v Word či Excel primární spolupracující sestavení. Řízení hostitele zpřístupní všechny chování podkladového objektu nativní Office, ale také vyvolá události a mohou být vázány na data pomocí vazby modelu Windows Forms data. Další informace najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
> [!NOTE]  
>  Nelze přidat <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládacího prvku do listu, nebo <xref:Microsoft.Office.Tools.Word.XMLNode> nebo <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládacího prvku do dokumentu pomocí doplňku VSTO. Tyto hostitelské ovládací prvky nelze přidat prostřednictvím kódu programu. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
### <a name="persisting-and-removing-controls"></a>Uchování a odebírání ovládacích prvků  
 Při přidání spravované ovládací prvky dokumentu nebo listu, ovládací prvky nejsou trvalé, když je dokument uložit a potom uzavřen. Všechny hostitelské ovládací prvky jsou odebrány, aby pouze základní nativní objekty Office jsou ponechána. Například <xref:Microsoft.Office.Tools.Excel.ListObject> stane <xref:Microsoft.Office.Interop.Excel.ListObject>. Budou odebrány také všechny ovládací prvky Windows Forms, ale ActiveX obálek pro ovládací prvky jsou ponechána v dokumentu. Je nutné zahrnout kódu vaší Add-in VSTO vyčištění ovládacích prvků, nebo znovu vytvořte ovládacích prvků při příštím otevření dokumentu. Další informace najdete v tématu [uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
## <a name="accessing-application-level-events-on-documents-and-workbooks"></a>Přístup k událostem na úrovni aplikace na dokumentů a sešitů  
 Některé události dokumentu, sešitu a listu v nativní objektové modely Word a Excel jsou vyvolány pouze na úrovni aplikace. Například <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> událost se vyvolá, když je dokument otevřít v aplikaci Word, ale tato událost je definována v <xref:Microsoft.Office.Interop.Word.Application> třída, místo <xref:Microsoft.Office.Interop.Word.Document> třídy.  
  
 Použijete-li v doplňku VSTO pouze nativní objektů Office, musíte zpracování těchto událostí na úrovni aplikace a pak zapsat další kód k určení, zda dokument, který vyvolá událost, je ten, který jste upravili. Hostitelské položky nabízí tyto události na úrovni dokumentu, takže je snazší zpracování událostí pro konkrétní dokument. Můžete vygenerovat položku hostitele a pak zpracovat událost pro tuto položku hostitele.  
  
### <a name="example-that-uses-native-word-objects"></a>Příklad, který používá objekty nativní aplikace Word  
 Následující příklad kódu ukazuje, jak zpracovat události úrovni aplikace pro dokumenty aplikace Word. `CreateDocument` Metoda vytvoří nový dokument a pak definuje <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> obslužné rutiny události, které zabrání ukládání tohoto dokumentu. Protože to je na úrovni aplikace událost, která se vyvolá pro <xref:Microsoft.Office.Interop.Word.Application> objektu, obslužné rutiny události musí porovnat `Doc` parametr s `document1` objekt, který chcete zjistit, jestli `document1` představuje uložený dokument.  
  
 [!code-vb[Trin_WordAddInDynamicControls#12](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#12)]
 [!code-csharp[Trin_WordAddInDynamicControls#12](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#12)]  
  
### <a name="examples-that-use-a-host-item"></a>Příklady, které používají položku hostitele  
 Následující příklady kódu zjednodušit tento proces tak, že zpracování <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> události <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka. `CreateDocument2` Metoda v těchto příkladech generovat <xref:Microsoft.Office.Tools.Word.Document> který rozšiřuje `document2` definuje objekt a poté <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> obslužné rutiny události, který brání dokument uloží. Protože této obslužné rutiny události se nazývá pouze tehdy, když `document2` je uložen, události obslužná rutina může uložení zrušit akci bez jakékoli další pracuje ověření, který dokument byl uložen.  
  
 Následující příklad kódu ukazuje tuto úlohu.  
  
 [!code-vb[Trin_WordAddInDynamicControls#13](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#13)]
 [!code-csharp[Trin_WordAddInDynamicControls#13](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#13)]  
  
##  <a name="HasVstoObject"></a>Určení, zda bylo rozšířeno objekt sady Office  
 Pokud chcete zjistit, zda objekt rozšířené už je vygenerovaný pro konkrétní objekt nativní Office, použijte metodu hasvstoobject –. Tato metoda vrátí hodnotu **true** Jestliže rozšířené objekt již byl vygenerován; jinak vrátí **false**.  
  
 Použijte metodu Globals.Factory.HasVstoMethod. Předat do nativní Word či Excel objektu, například <xref:Microsoft.Office.Interop.Word.Document> nebo <xref:Microsoft.Office.Interop.Excel.Worksheet>, který chcete testovat pro objekt rozšířené.  
  
 Hasvstoobject – metoda je užitečná, pokud chcete spustit kód jenom v případě, že zadaný objekt Office má rozšířené objekt. Například, pokud máte Add-in VSTO slova, která zpracovává <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> je uložen událost se má odebrat z dokumentu před ním spravované ovládací prvky, hasvstoobject – metoda můžete použít k určení, zda bylo rozšířeno dokumentu. Pokud dokument nebylo rozšířeno, nemůže obsahovat spravované ovládací prvky, a proto obslužné rutiny události můžete jednoduše vraťte zpět bez pokusu o vyčištění ovládacích prvků na dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)  
  
  