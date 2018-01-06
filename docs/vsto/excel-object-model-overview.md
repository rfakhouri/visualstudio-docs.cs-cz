---
title: "Přehled modelu objektů v aplikaci Excel | Microsoft Docs"
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
- Worksheet object
- Range object
- object models [Office development in Visual Studio], Excel
- object models [Office development in Visual Studio], Office
- Workbook class
- objects [Office development in Visual Studio], Office object models
- Excel object model
- Office object models
ms.assetid: e4b2e46b-ea6c-4a88-a416-a7d4f495fc33
caps.latest.revision: "66"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f2727d3c1608db15ab4b46285c0ad6971864978e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="excel-object-model-overview"></a>Přehled modelu objektů aplikace Excel
  Pro vývoj řešení, které používají aplikace Microsoft Office Excel, můžete pracovat s objekty poskytované model objektů aplikace Excel. Toto téma představuje nejdůležitější objekty:  
  
-   <xref:Microsoft.Office.Interop.Excel.Application>  
  
-   <xref:Microsoft.Office.Interop.Excel.Workbook>  
  
-   <xref:Microsoft.Office.Interop.Excel.Worksheet>  
  
-   <xref:Microsoft.Office.Interop.Excel.Range>  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Objektový model přesně dodržuje uživatelské rozhraní. <xref:Microsoft.Office.Interop.Excel.Application> Objekt představuje celou aplikaci a všechny <xref:Microsoft.Office.Interop.Excel.Workbook> objektu obsahuje kolekci `Worksheet` objekty. Zde, je hlavní abstrakce, která představuje buněk <xref:Microsoft.Office.Interop.Excel.Range> objekt, který umožňuje pracovat s jednotlivých buněk nebo skupiny buněk.  
  
 Kromě model objektů aplikace Excel projektech pro systém Office v sadě Visual Studio poskytují *hostitele položky* a *hostování ovládacích prvků* , rozšířit některé objekty ve model objektů aplikace Excel. Hostitelských položek a hostitelských ovládacích prvků chovají jako objekty aplikace Excel, které budou rozšíření, ale mají také další funkce, jako je například funkce datové vazby a další události. Další informace najdete v tématu [automatizace aplikace Excel pomocí rozšířených objekty](../vsto/automating-excel-by-using-extended-objects.md) a [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
 Toto téma obsahuje stručný přehled modelu objektů aplikace Excel. Zdroje, kde můžete další informace o celý model objektů aplikace Excel najdete v tématu [pomocí dokumentace modelu objektů aplikace Excel](#ExcelOMDocumentation).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: použití obslužné rutiny událostí v aplikaci Excel 2007 doplňku?](http://go.microsoft.com/fwlink/?LinkID=130291), a [jak provést I: použití obrazce vytvořte bublinový Graf v aplikaci Excel? ](http://go.microsoft.com/fwlink/?LinkID=130313).  
  
## <a name="accessing-objects-in-an-excel-project"></a>Přístup k objektům v projektu aplikace Excel  
 Při vytváření nového projektu doplňku VSTO pro Excel, Visual Studio automaticky vytvoří soubor ThisAddIn.vb nebo ThisAddIn.cs kódu. Máte přístup k objektu Application pomocí `Me.Application` nebo `this.Application`.  
  
 Když vytvoříte nový projekt na úrovni dokumentu pro Excel, máte možnost vytvořit nový projekt sešitu aplikace Excel nebo Excel šablony. Ve nový projekt aplikace Excel pro sešit a šablony projektů sady Visual Studio automaticky vytvoří následující soubory kódu.  
  
|Visual Basic|C#|  
|------------------|---------|  
|ThisWorkbook.vb|ThisWorkbook.cs|  
|Sheet1.vb|Sheet1.cs|  
|Sheet2.vb|Sheet2.cs|  
|Sheet3.vb|Sheet3.cs|  
  
 Můžete použít `Globals` třídy ve vašem projektu a přístup k `ThisWorkbook`, `Sheet1`, `Sheet2`, nebo `Sheet3` z mimo příslušné třídy. Další informace najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md). Následující příklad volání <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> metodu `Sheet1` bez ohledu na to, zda kód je umístěn v jednom z `Sheet`  *n*  třídy nebo `ThisWorkbook` třídy.  
  
 [!code-csharp[Trin_VstcoreExcelAutomation#82](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#82)]
 [!code-vb[Trin_VstcoreExcelAutomation#82](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#82)]  
  
 Vzhledem k tomu, že je vysoce strukturovaná data v dokumentu aplikace Excel, je objektový model hierarchické a přímočará. Excel poskytuje stovky objekty, se kterými chcete pracovat, ale můžete začít funkčním na objektový model se zaměříte na velmi malou podmnožinu dostupných objektů. Tyto objekty zahrnují následující čtyři:  
  
-   Aplikace  
  
-   sešit  
  
-   list  
  
-   Rozsah  
  
 Velká část práci v aplikaci Excel se soustředí kolem tyto čtyři objekty a jejich členové.  
  
### <a name="application-object"></a>Objekt aplikace  
 Aplikace Excel <xref:Microsoft.Office.Interop.Excel.Application> objekt představuje vlastní aplikace Excel. <xref:Microsoft.Office.Interop.Excel.Application> Objekt poskytuje značnou část informace o běžící aplikaci, možnosti u dané instance, a otevřete aktuální uživatelské objekty v rámci instance.  
  
> [!NOTE]  
>  By neměl nastavený <xref:Microsoft.Office.Interop.Excel.ApplicationClass.EnableEvents%2A> vlastnost <xref:Microsoft.Office.Interop.Excel.Application> objektu v aplikaci Excel a **false**. Nastavení této vlastnosti na hodnotu false zabrání vyvolání všechny události, včetně události hostitelské ovládací prvky aplikace Excel.  
  
### <a name="workbook-object"></a>Objekt sešitu  
 <xref:Microsoft.Office.Interop.Excel.Workbook> Objekt představuje jeden sešit v aplikaci Excel.  
  
 Nástroje pro vývoj pro Office v sadě Visual Studio rozšiřuje <xref:Microsoft.Office.Interop.Excel.Workbook> objekt tím, že poskytuje <xref:Microsoft.Office.Tools.Excel.Workbook> typu. Tento typ poskytuje přístup ke všem funkcím <xref:Microsoft.Office.Interop.Excel.Workbook> objektu. Další informace najdete v tématu [hostitelská položka Workbook](../vsto/workbook-host-item.md).  
  
### <a name="worksheet-object"></a>List – objekt  
 <xref:Microsoft.Office.Interop.Excel.Worksheet> Je členem objektu <xref:Microsoft.Office.Interop.Excel.Worksheets> kolekce. Mnoho vlastností, metod a události <xref:Microsoft.Office.Interop.Excel.Worksheet> jsou stejná nebo podobná členy poskytované <xref:Microsoft.Office.Interop.Excel.Application> nebo <xref:Microsoft.Office.Interop.Excel.Workbook> objekty.  
  
 Poskytuje aplikace Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekci jako vlastnost <xref:Microsoft.Office.Interop.Excel.Workbook> objektu. Každý člen <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce je buď <xref:Microsoft.Office.Interop.Excel.Worksheet> nebo <xref:Microsoft.Office.Interop.Excel.Chart> objektu.  
  
 Nástroje pro vývoj pro Office v sadě Visual Studio rozšiřují <xref:Microsoft.Office.Interop.Excel.Worksheet> objekt tím, že poskytuje <xref:Microsoft.Office.Tools.Excel.Worksheet> typu. Tento typ poskytuje přístup ke všem funkcím <xref:Microsoft.Office.Interop.Excel.Worksheet> objektu, jakož i nové funkce, jako je například schopnost hostitele spravované ovládací prvky a zpracovávat nové události. Další informace najdete v tématu [hostitelská položka Worksheet](../vsto/worksheet-host-item.md).  
  
### <a name="range-object"></a>Objekt rozsahu  
 <xref:Microsoft.Office.Interop.Excel.Range> Objektu je objekt, který budete používat většinu v rámci aplikace Excel. Předtím, než můžete upravit všechny oblasti v aplikaci Excel, musíte jej jako express <xref:Microsoft.Office.Interop.Excel.Range> objektu a pracovat s metody a vlastnosti rozsahu. A <xref:Microsoft.Office.Interop.Excel.Range> objekt představuje buňku, řádek, sloupec, výběr buněk, který obsahuje jeden nebo více bloků buněk, které nemusí nebo může být souvislý nebo dokonce i skupiny buněk na několik listů.  
  
 Visual Studio rozšiřuje <xref:Microsoft.Office.Interop.Excel.Range> objekt tím, že poskytuje <xref:Microsoft.Office.Tools.Excel.NamedRange> a <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> typy. Tyto typy mají většinu stejné funkce jako <xref:Microsoft.Office.Interop.Excel.Range> objektu, jakož i nové funkce, jako je například funkce vazby dat a nové události. Další informace najdete v tématu [NamedRange – ovládací prvek](../vsto/namedrange-control.md) a [xmlmappedrange – ovládací prvek](../vsto/xmlmappedrange-control.md).  
  
##  <a name="ExcelOMDocumentation"></a>Pomocí dokumentace modelu objektů aplikace Excel  
 Úplné informace o model objektů aplikace Excel najdete odkaz primární spolupracující sestavení (PIA) aplikace Excel a VBA objektu modelu.  
  
### <a name="primary-interop-assembly-reference"></a>Odkaz sestavení primární spolupráce  
 PIA – Excel referenční dokumentaci k nástroji popisuje typy v sestavení primární spolupráce pro aplikaci Excel. Tato dokumentace je k dispozici z následujícího umístění: [odkaz na sestavení zprostředkovatel komunikace s objekty aplikace Excel 2010 primární](http://go.microsoft.com/fwlink/?LinkId=189585).  
  
 Další informace o návrhu PIA aplikace Excel, jako jsou rozdíly mezi třídy a rozhraní v primární a jak jsou implementované události v primární, najdete v části [přehled třídy a rozhraní v Office primární zprostředkovatel komunikace s objekty sestavení](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
### <a name="vba-object-model-reference"></a>Odkaz na objekt modelu VBA  
 Reference objektu modelu VBA dokumenty model objektů aplikace Excel, jako je zpřístupněné pro Visual Basic pro aplikace (VBA) kód. Další informace najdete v tématu [odkaz na objekt modelu aplikace Excel 2010](http://go.microsoft.com/fwlink/?LinkId=199768).  
  
 Všechny objekty a členy ve model odkaz na VBA odpovídají typy a členy v PIA aplikace Excel. Například odpovídá objektu listu ve model odkaz na VBA <xref:Microsoft.Office.Interop.Excel.Worksheet> objekt v PIA aplikace Excel. I když reference VBA objektu modelu poskytuje příklady kódu pro většinu vlastností, metod a událostí, musí překládat VBA kód v této referenci na Visual Basic a Visual C#, pokud chcete používat v projektu aplikace Excel, který vytvoříte pomocí sady Visual Studio.  
  
### <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Řešení pro aplikaci Excel](../vsto/excel-solutions.md)|Vysvětluje, jak můžete vytvořit přizpůsobení na úrovni dokumentu a doplňků VSTO pro aplikaci Microsoft Office Excel.|  
|[Práce s oblastmi](../vsto/working-with-ranges.md)|Obsahuje příklady, které ukazují, jak provádět běžné úlohy s rozsahy.|  
|[Práce s listy](../vsto/working-with-worksheets.md)|Obsahuje příklady, které ukazují, jak provádět běžné úkoly s listů.|  
|[Práce se sešity](../vsto/working-with-workbooks.md)|Obsahuje příklady, které ukazují, jak provádět běžné úkoly s sešity.|  
  
  