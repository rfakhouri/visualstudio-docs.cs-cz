---
title: Přehled ovládacích prvků hostitele hostitelských položek a | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- host controls [Office development in Visual Studio], adding
- Office documents [Office development in Visual Studio, host controls
- host items [Office development in Visual Studio]
- application development [Office development in Visual Studio], host items
- Office applications [Office development in Visual Studio], host items
- host controls [Office development in Visual Studio], listed
- Excel [Office development in Visual Studio], host items
- host controls [Office Development in Visual Stuio], naming
- host controls [Office development in Visual Studio]
- host controls [Office development in Visual Studio], about host controls
- document-level customizations [Office development in Visual Studio], host controls
- Office applications [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- controls [Office development in Visual Studio], host controls
- application development [Office development in Visual Studio], host controls
- Excel [Office development in Visual Studio], host controls
- host items [Office development in Visual Studio], about host items
- host items [Office development in Visual Studio], listed
- documents [Office development in Visual Studio], host items
- data binding [Office development in Visual Studio], host controls
- Office documents [Office development in Visual Studio, host items
- Word [Office development in Visual Studio], host items
- document-level customizations [Office development in Visual Studio], host items
- Word [Office development in Visual Studio], host controls
- host controls [Office development in Visual Studio], deleting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 84e0b2cf74eb8c0d3faca8d1c28d3bea91c87f76
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="host-items-and-host-controls-overview"></a>Přehled hostitelských položek a hostitelských ovládacích prvků
  Hostitelských položek a hostitelských ovládacích prvků jsou typy, které pomáhají zajistit programovací model pro řešení Office, které jsou vytvořené pomocí nástroje pro vývoj pro Office v sadě Visual Studio. Hostitelských položek a hostitelských ovládacích prvků zkontrolujte interakci s objektové modely aplikace Microsoft Office Word a Microsoft Office Excel, které jsou založené na modelu COM, více jako interakci s spravovaných objektů, jako je Windows Forms – ovládací prvky.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="host-items"></a>Hostitelské položky  
 Hostitelské položky jsou typy, které jsou v horní části objektu modelu hierarchií v projektech Office. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Definuje následující položky hostitele pro Word a Excel řešení:  
  
-   <xref:Microsoft.Office.Tools.Word.Document>  
  
-   <xref:Microsoft.Office.Tools.Excel.Workbook>  
  
-   <xref:Microsoft.Office.Tools.Excel.Worksheet>  
  
-   <xref:Microsoft.Office.Tools.Excel.ChartSheet>  
  
 Každý z těchto typů rozšiřuje objekt, který existuje nativně v modelu objektu Word či Excel názvem *nativní objekt Office*. Například <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka rozšiřuje <xref:Microsoft.Office.Interop.Word.Document> objekt, který je definován v primární spolupracující sestavení pro aplikaci Word.  
  
 Hostitelské položky obvykle mají stejné základní funkce jako odpovídající objektů Office, ale jsou rozšířené o následující funkce:  
  
-   Možnost hostitelů spravovaných ovládacích prvků, včetně hostitelů a ovládacích prvků Windows Forms.  
  
-   Širší modely událostí. Některé události dokumentu, sešitu a listu v nativní objektové modely Word a Excel jsou vyvolány pouze na úrovni aplikace. Hostitelské položky nabízí tyto události na úrovni dokumentu, takže je snazší zpracování událostí pro konkrétní dokument.  
  
### <a name="understanding-host-items-in-document-level-projects"></a>Principy hostitelské položky v projekty na úrovni dokumentu  
 V projektech na úrovni dokumentu hostitelské položky vytvořit vstupní bod pro kód a mají návrhářů, které pomáhají budete vyvíjet řešení.  
  
 <xref:Microsoft.Office.Tools.Word.Document> a <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelské položky přidruženy návrhářů, které jsou vizuální reprezentace dokumentu nebo listu, jako je Windows Forms návrháře. Pokud chcete upravit obsah v dokumentu nebo přímo v aplikaci Word nebo v aplikaci Excel a přetáhněte ovládací prvky na návrhovou plochu, můžete použít tento Návrhář. Další informace najdete v tématu [hostitelská položka Document](../vsto/document-host-item.md) a [hostitelská položka Worksheet](../vsto/worksheet-host-item.md).  
  
 <xref:Microsoft.Office.Tools.Excel.Workbook> Hostitelská položka není slouží jako kontejner pro ovládací prvky, které mají uživatelské rozhraní. Místo toho návrháře pro tuto položku hostitele funguje jako součást panelu, který umožňuje přetáhněte součást, například <xref:System.Data.DataSet>, na jeho návrhovou plochu. Další informace najdete v tématu [hostitelská položka Workbook](../vsto/workbook-host-item.md).  
  
 Hostitelské položky nelze vytvořit, v projektech na úrovni dokumentů prostřednictvím kódu programu. Místo toho použijte `ThisDocument`, `ThisWorkbook`, nebo `Sheet` *n* třídy, které Visual Studio se automaticky vytvoří ve vašem projektu v době návrhu. Tyto generované třídy odvozeny od hostitelských položek a poskytují vstupní bod pro kód. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
### <a name="understanding-host-items-in-vsto-add-in-projects"></a>Principy hostitelské položky v projekty doplňku VSTO  
 Když vytvoříte doplňku VSTO, nemají přístup k položkám všechny hostitele ve výchozím nastavení. Však můžete vygenerovat <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, a <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitele položek v aplikaci Word a doplňků VSTO pro Excel za běhu.  
  
 Po vygenerování hostitelská položka můžete provádět úlohy, jako je například přidávání ovládacích prvků do dokumentů. Další informace najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="host-controls"></a>Hostitelské ovládací prvky  
 Hostitelské ovládací prvky rozšíření různé objekty uživatelského rozhraní (UI) v aplikaci Word a Excel objektové modely, například Microsoft.Office.Interop.Word.ContentControl a <xref:Microsoft.Office.Interop.Excel.Range> objekty.  
  
 Následující hostitelské ovládací prvky jsou k dispozici pro projekty aplikace Excel:  
  
-   [Graf – ovládací prvek](../vsto/chart-control.md)  
  
-   [ListObject – ovládací prvek](../vsto/listobject-control.md)  
  
-   [NamedRange – ovládací prvek](../vsto/namedrange-control.md)  
  
-   [XMLMappedRange – ovládací prvek](../vsto/xmlmappedrange-control.md)  
  
 Následující hostitelské ovládací prvky jsou k dispozici pro projekty aplikace Word:  
  
-   [Bookmark – ovládací prvek](../vsto/bookmark-control.md)  
  
-   [Ovládací prvky obsahu](../vsto/content-controls.md)  
  
-   [XMLNode – ovládací prvek](../vsto/xmlnode-control.md)  
  
-   [XMLNodes – ovládací prvek](../vsto/xmlnodes-control.md)  
  
 Hostitelské ovládací prvky, které jsou přidány do dokumentů Office chovají jako nativní objekty Office; hostitelské ovládací prvky však mít další funkce, včetně události a možnosti pro datové vazby. Například, pokud chcete zaznamenat události nativní <xref:Microsoft.Office.Interop.Excel.Range> objektů v aplikaci Excel, je nutné nejprve zpracovat událost změny listu. Pak je třeba určit, zda změn došlo k chybě v rámci <xref:Microsoft.Office.Interop.Excel.Range>. Naproti tomu <xref:Microsoft.Office.Tools.Excel.NamedRange> má hostitelského ovládacího prvku <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> událost, která dokáže zpracovat přímo.  
  
 Vztah mezi položkou hostitele a hostitelských ovládacích prvků je velmi podobný vztah mezi ovládacích prvků formuláře Windows a Windows Forms. Stejně, jako by toto textové pole ve formuláři Windows, můžete umístit <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení na <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelská položka. Následující obrázek znázorňuje vztah mezi hostitelských položek a hostitelských ovládacích prvků.  
  
 ![Vztah mezi hostitelských položek a hostitelských ovládacích prvků](../vsto/media/hostitemscontrols.png "vztah mezi hostitelských položek a hostitelských ovládacích prvků")  
  
 Můžete také použít ovládací prvky Windows Forms v řešeních pro systém Office přidáním přímo na plochu dokument aplikace Word a Excel. Další informace najdete v tématu [ovládacích prvků Windows Forms na přehled dokumenty Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
> [!NOTE]  
>  Přidání hostitelské ovládací prvky nebo ovládací prvky Windows Forms k vnořený dokument aplikace Word není podporováno.  
  
### <a name="adding-host-controls-to-your-documents"></a>Přidání hostitele ovládacích prvků do dokumentů  
 Ve projekty na úrovni dokumentu můžete přidat hostitele ovládacích prvků do dokumentů aplikace Word nebo sešitů aplikace Excel v době návrhu následujícími způsoby:  
  
-   Hostitelské ovládací prvky přidat do dokumentu v době návrhu stejným způsobem by přidat nativní objekt.  
  
-   Přetáhněte ovládací prvky hostitele z **sada nástrojů** do své dokumenty a listů. Hostitelské ovládací prvky aplikace Excel jsou k dispozici v **ovládací prvky aplikace Excel** ve projekty aplikace Excel a Word hostitele ovládací prvky jsou k dispozici v **ovládací prvky aplikace Word** ve projekty aplikace Word.  
  
-   Přetáhněte ovládací prvky hostitele z **zdroje dat** okna do své dokumenty a listů. Umožňuje přidání ovládacích prvků, které jsou již vázána na data. Další informace najdete v tématu [vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Na úrovni dokumentu a projekty doplňku VSTO můžete také přidat některé hostitelské ovládací prvky do dokumentů za běhu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Další informace o tom, jak přidat hostitele ovládacích prvků do dokumentů najdete v následujících tématech:  
  
-   [Postupy: Přidání ovládacích prvků Graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md)  
  
-   [Postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md)  
  
-   [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)  
  
-   [Postupy: Přidání ovládacích prvků XMLMappedRange do listů](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)  
  
-   [Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)  
  
-   [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)  
  
-   [Postupy: Přidání ovládacích prvků XMLNode do dokumentů aplikace Word](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)  
  
-   [Postupy: Přidání ovládacích prvků XMLNodes do dokumentů aplikace Word](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)  
  
### <a name="naming-host-controls"></a>Pojmenování hostitelské ovládací prvky  
 Při přetažení z hostitelského ovládacího prvku **sada nástrojů** dokumentu ovládací prvek je automaticky s názvem typ ovládacího prvku pomocí pořadové číslo na konci. Například jsou pojmenované záložky **bookmark1**, **bookmark2**a tak dále. Pokud používáte nativní funkce Word či Excel přidání ovládacího prvku, můžete jí určitý název v době, musíte ji vytvořit. Vaše ovládací prvky můžete přejmenovat tak, že změníte hodnotu **název** vlastnost **vlastnosti** okno.  
  
> [!NOTE]  
>  Vyhrazená slova pro název hostitelské ovládací prvky se nedá použít. Například, pokud přidáte <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení do listu a změňte název **systému**, při sestavování projektu dojít k chybám.  
  
### <a name="deleting-host-controls"></a>Odstraňování hostitelské ovládací prvky  
 V projektech na úrovni dokumentu můžete odstranit hostitelské ovládací prvky v době návrhu výběrem ovládacího prvku na sešit aplikace Excel nebo dokument aplikace Word a stisknutím klávesy Delete. Ale musí používat **definovat název** dialogové okno v aplikaci Excel odstranit <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvky.  
  
 Pokud přidáte hostitelského ovládacího prvku na dokument v době návrhu, neměli byste je odstraňovat prostřednictvím kódu programu v době běhu vzhledem k tomu, že při příštím pokusu pomocí ovládacího prvku v kódu, je vyvolána výjimka. `Delete` Metoda hostitelského ovládacího prvku pouze odebere hostitelské ovládací prvky, které jsou přidány do dokumentu za běhu. Když zavoláte `Delete` metoda hostitelského ovládacího prvku, který byl vytvořen v době návrhu, je vyvolána výjimka.  
  
 Například <xref:Microsoft.Office.Tools.Excel.NamedRange.Delete%2A> metodu <xref:Microsoft.Office.Tools.Excel.NamedRange> pouze úspěšně odstraní <xref:Microsoft.Office.Tools.Excel.NamedRange> Pokud je prostřednictvím kódu programu přidaná do listu, která se označuje jako dynamicky vytváření ovládacích prvků hostitele. Ovládací prvky dynamicky vytvořený hostitele může být odebrán také předáním název ovládacího prvku na `Remove` metodu <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> nebo <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> vlastnost. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Pokud koncoví uživatelé odstranit hostitelského ovládacího prvku z dokumentu za běhu, řešení může selhat neočekávaným způsobem. Funkce ochrany dokumentu ve Wordu a Excelu můžete chránit před odstraněním hostitelské ovládací prvky. Další informace najdete v tématu [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
> [!NOTE]  
>  Neodebírejte ovládací prvky během prostřednictvím kódu programu `Shutdown` obslužné rutiny události dokumentu nebo listu. Prvky uživatelského rozhraní nejsou nadále k dispozici při `Shutdown` dojde k události. Pokud chcete odebrat ovládacích prvků, než se aplikace zavře, přidejte kód na jinou obslužnou rutinu události, jako `BeforeClose` nebo `BeforeSave`.  
  
### <a name="programming-against-host-control-events"></a>Programové ošetření událostí ovládacího prvku hostitele  
 Jedním ze způsobů, hostitelské ovládací prvky rozšíření objektů Office je přidání událostí. Například <xref:Microsoft.Office.Interop.Excel.Range> objektu v aplikaci Excel a <xref:Microsoft.Office.Interop.Word.Bookmark> objektu v aplikaci Word nemají události, ale [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] rozšiřuje tyto objekty přidáním programovatelný události. Můžete používat a kódu pro tyto události stejný způsobem, jakým přistupujete události ovládacích prvků ve Windows Forms: pomocí rozevíracího seznamu těchto událostí v jazyce Visual Basic a stránku vlastností události v jazyce C#. Další informace najdete v tématu [návod: programování proti události ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md).  
  
> [!NOTE]  
>  By neměl nastavený <xref:Microsoft.Office.Interop.Excel._Application.EnableEvents%2A> vlastnost <xref:Microsoft.Office.Interop.Excel.Application> objektu v aplikaci Excel a **false**. Nastavení této vlastnosti na **false** brání vyvolání všechny události, včetně události hostitelské ovládací prvky aplikace Excel.  
  
## <a name="see-also"></a>Viz také  
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  