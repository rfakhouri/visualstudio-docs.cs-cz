---
title: Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7b7461ba184850ba53099327fdad44e3103dcd87
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
ms.locfileid: "34548619"
---
# <a name="extend-word-documents-and-excel-workbooks-in-vsto-add-ins-at-runtime"></a>Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu
  Doplňku VSTO můžete použít k přizpůsobení dokumentů aplikace Word a sešitů aplikace Excel následujícími způsoby:  
  
-   Přidání spravovaných ovládacích prvků do všechny otevřené dokumenty a listu.  
  
-   Převést stávající seznamu objektu na listu aplikace Excel na rozšířená <xref:Microsoft.Office.Tools.Excel.ListObject> který zpřístupní události a může být vázána k datům pomocí vazby modelu Windows Forms data.  
  
-   Přístup úrovni aplikace události, které jsou vystavené Word a Excel pro konkrétní dokumentům, sešitům a listů.  
  
 Chcete-li používat tuto funkci, generovat objekt za běhu, který rozšiřuje dokumentu nebo sešitu.  
  
 **Platí pro:** informace v tomto článku se vztahují na projekty doplňku VSTO pro následující aplikace: Excel a Word. Další informace najdete v tématu [dostupné funkce podle aplikace a projekt typu Office](../vsto/features-available-by-office-application-and-project-type.md).  
  
## <a name="generate-extended-objects-in-vsto-add-ins"></a>Generování rozšířených objektů v doplňků VSTO  
 *Rozšířené objekty* jsou instancemi typů poskytované sady Visual Studio Tools pro systém Office runtime, které zajišťují funkce objekty, které nativně existovat v objektové modely Word či Excel (nazývá *nativních objektů Office*). Chcete-li vygenerovat rozšířené objektu pro objekt Word či Excel, použijte `GetVstoObject` metoda. Při prvním volání `GetVstoObject` metodu pro zadaný Word či Excel objektu, vrátí nový objekt, který rozšiřuje zadaný objekt. Pokaždé, když volat metodu a zadejte stejné aplikace Word nebo v aplikaci Excel na objekt, vrátí stejný objekt rozšířené.  
  
 Typ objektu rozšířené má stejný název jako typ objektu pro nativní Office, ale tento typ je definovaný v <xref:Microsoft.Office.Tools.Excel> nebo <xref:Microsoft.Office.Tools.Word> oboru názvů. Například když zavoláte `GetVstoObject` – metoda rozšíření <xref:Microsoft.Office.Interop.Word.Document> objektu, vrátí metoda <xref:Microsoft.Office.Tools.Word.Document> objektu.  
  
 `GetVstoObject` Metody jsou určeny k použije především na projekty doplňku VSTO. Můžete také použít tyto metody v projekty na úrovni dokumentu, ale chovat jinak a máte méně používá.  
  
 Chcete-li zjistit, zda objekt rozšířené už je vygenerovaný pro konkrétní objekt nativní Office, použijte `HasVstoObject` metoda. Další informace najdete v tématu [určit, zda objekt Office rozšířilo](#HasVstoObject).  
  
### <a name="generate-host-items"></a>Generovat hostitelské položky  
 Při použití `GetVstoObject` rozšířit o objekt na úrovni dokumentu (to znamená, <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, nebo <xref:Microsoft.Office.Interop.Word.Document>), se nazývá vráceného objektu *hostitelská položka*. Hostitelská položka je typ, který může obsahovat jiné objekty, včetně jiných rozšířených objektů a ovládacích prvků. Je podobná odpovídající typ v Word či Excel primární spolupracující sestavení, ale má další funkce. Další informace o hostitelských položkách najdete v tématu [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
 Po vygenerování hostitelskou položku můžete přidat spravovaných ovládacích prvků do dokumentu, sešitu nebo listu. Další informace najdete v tématu [přidat spravovaných ovládacích prvků k dokumentům a listů](#AddControls).  
  
#### <a name="to-generate-a-host-item-for-a-word-document"></a>Generovat položku hostitele pro dokument aplikace Word  
  
-   Následující příklad kódu ukazuje, jak vygenerovat položku hostitele pro aktivní dokument.  
  
     [!code-vb[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#8)]
     [!code-csharp[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#8)]  
  
#### <a name="to-generate-a-host-item-for-an-excel-workbook"></a>Generovat položku hostitel pro sešit aplikace Excel  
  
-   Následující příklad kódu ukazuje, jak generovat položku hostitele pro aktivním sešitu.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#2)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#2)]  
  
#### <a name="to-generate-a-host-item-for-an-excel-worksheet"></a>Generovat položku hostitele pro listu aplikace Excel  
  
-   Následující příklad kódu ukazuje, jak vygenerovat položku hostitele pro aktivního listu v projektu.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#1)]  
  
### <a name="generate-listobject-host-controls"></a>Generovat ovládacích prvků ListObject hostitele  
 Při použití `GetVstoObject` metoda rozšířit <xref:Microsoft.Office.Interop.Excel.ListObject>, vrátí metoda <xref:Microsoft.Office.Tools.Excel.ListObject>. <xref:Microsoft.Office.Tools.Excel.ListObject> Obsahuje všechny funkce původní <xref:Microsoft.Office.Interop.Excel.ListObject>. Také obsahuje další funkce a mohou být vázány na data pomocí vazby modelu Windows Forms data. Další informace najdete v tématu [ListObject – ovládací prvek](../vsto/listobject-control.md).  
  
#### <a name="to-generate-a-host-control-for-a-listobject"></a>Generovat hostitelského ovládacího prvku pro ListObject  
  
-   Následující příklad kódu ukazuje, jak vygenerovat <xref:Microsoft.Office.Tools.Excel.ListObject> pro první <xref:Microsoft.Office.Interop.Excel.ListObject> v aktivním listu v projektu.  
  
     [!code-vb[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#3)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#3)]  
  
###  <a name="AddControls"></a> Přidání spravovaných ovládacích prvků do dokumentů a listů  
 Po vygenerování <xref:Microsoft.Office.Tools.Word.Document> nebo <xref:Microsoft.Office.Tools.Excel.Worksheet>, můžete přidat ovládací prvky v dokumentu nebo listu, která tyto rozšířené objekty představují. K přidávání ovládacích prvků, použijte `Controls` vlastnost <xref:Microsoft.Office.Tools.Word.Document> nebo <xref:Microsoft.Office.Tools.Excel.Worksheet>. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Můžete přidat ovládací prvky Windows Forms nebo *hostování ovládacích prvků*. Řízení hostitele je ovládací prvek poskytované [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] který zabalí odpovídající ovládacího prvku v Word či Excel primární spolupracující sestavení. Řízení hostitele zpřístupní všechny chování podkladového objektu nativní Office. Také vyvolá události a mohou být vázány na data pomocí vazby modelu Windows Forms data. Další informace najdete v tématu [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
> [!NOTE]  
>  Nelze přidat <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládacího prvku do listu, nebo <xref:Microsoft.Office.Tools.Word.XMLNode> nebo <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládacího prvku do dokumentu pomocí doplňku VSTO. Tyto hostitelské ovládací prvky nelze přidat prostřednictvím kódu programu. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
### <a name="persist-and-remove-controls"></a>Zachovat a odebrání ovládacích prvků  
 Při přidání spravované ovládací prvky dokumentu nebo listu, ovládací prvky nejsou trvalé, když je dokument uložit a potom uzavřen. Všechny hostitelské ovládací prvky jsou odebrány, aby pouze základní nativní objekty Office jsou ponechána. Například <xref:Microsoft.Office.Tools.Excel.ListObject> stane <xref:Microsoft.Office.Interop.Excel.ListObject>. Budou odebrány také všechny ovládací prvky Windows Forms, ale ActiveX obálek pro ovládací prvky jsou ponechána v dokumentu. Je nutné zahrnout kódu vaší Add-in VSTO vyčištění ovládacích prvků, nebo znovu vytvořte ovládacích prvků při příštím otevření dokumentu. Další informace najdete v tématu [uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
## <a name="access-application-level-events-on-documents-and-workbooks"></a>Událostí na úrovni aplikace přístup na dokumentů a sešitů  
 Některé události dokumentu, sešitu a listu v nativní objektové modely Word a Excel jsou vyvolány pouze na úrovni aplikace. Například <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> událost se vyvolá, když je dokument otevřít v aplikaci Word, ale tato událost je definována v <xref:Microsoft.Office.Interop.Word.Application> třída, místo <xref:Microsoft.Office.Interop.Word.Document> třídy.  
  
 Použijete-li v doplňku VSTO pouze nativní objektů Office, musíte zpracování těchto událostí na úrovni aplikace a pak zapsat další kód k určení, zda dokument, který vyvolá událost, je ten, který jste upravili. Hostitelské položky nabízí tyto události na úrovni dokumentu, takže je snazší zpracování událostí pro konkrétní dokument. Můžete vygenerovat položku hostitele a pak zpracovat událost pro tuto položku hostitele.  
  
### <a name="example-that-uses-native-word-objects"></a>Příklad, který používá nativních objektů aplikace Word  
 Následující příklad kódu ukazuje, jak zpracovat události úrovni aplikace pro dokumenty aplikace Word. `CreateDocument` Metoda vytvoří nový dokument a pak definuje <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> obslužné rutiny události, které zabrání ukládání tohoto dokumentu. Událost je na úrovni aplikace událost, která se vyvolá pro <xref:Microsoft.Office.Interop.Word.Application> objekt a obslužné rutiny události musí porovnat `Doc` parametr s `document1` objekt, který chcete zjistit, jestli `document1` představuje uložený dokument.  
  
 [!code-vb[Trin_WordAddInDynamicControls #12](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#12)]
 [!code-csharp[Trin_WordAddInDynamicControls#12](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#12)]  
  
### <a name="examples-that-use-a-host-item"></a>Příklady, které používají položku hostitele  
 Následující příklady kódu zjednodušit tento proces tak, že zpracování <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> události <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka. `CreateDocument2` Metoda v těchto příkladech generuje <xref:Microsoft.Office.Tools.Word.Document> který rozšiřuje `document2` definuje objekt a poté <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> obslužné rutiny události, který brání dokument uloží. Obslužné rutiny události se nazývá pouze tehdy, když `document2` je uloženo a uložení můžete zrušit akci bez jakékoli další pracuje ověření, který dokument byl uložen.  
  
 Následující příklad kódu ukazuje tuto úlohu.  
  
 [!code-vb[Trin_WordAddInDynamicControls #13](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#13)]
 [!code-csharp[Trin_WordAddInDynamicControls#13](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#13)]  
  
##  <a name="HasVstoObject"></a> Určení, zda bylo rozšířeno objekt sady Office  
 Chcete-li zjistit, zda objekt rozšířené už je vygenerovaný pro konkrétní objekt nativní Office, použijte `HasVstoObject` metoda. Tato metoda vrátí hodnotu **true** Jestliže rozšířené objekt již byl vygenerován.  
  
 Použití `Globals.Factory.HasVstoMethod` metoda. Předat do nativní Word či Excel objektu, například <xref:Microsoft.Office.Interop.Word.Document> nebo <xref:Microsoft.Office.Interop.Excel.Worksheet>, který chcete testovat pro objekt rozšířené.  
  
 `HasVstoObject` Metoda je užitečná, pokud chcete spustit kód jenom v případě, že zadaný objekt Office má rozšířené objekt. Například, pokud máte Add-in VSTO slova, která zpracovává <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> událostí, které chcete odebrat z dokumentu spravované ovládací prvky, před uložením, použijte `HasVstoObject` metoda k určení, zda bylo rozšířeno dokumentu. Pokud dokument nebylo rozšířeno, nemůže mít spravovaných ovládacích prvků a obslužné rutiny události může vrátit bez pokusu o vyčištění ovládacích prvků na dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)  
  
  