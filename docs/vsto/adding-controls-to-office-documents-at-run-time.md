---
title: "Přidání ovládacích prvků do dokumentů Office za běhu | Microsoft Docs"
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
- Office documents [Office development in Visual Studio, Windows Forms controls
- host controls [Office development in Visual Studio], adding
- Windows Forms controls [Office development in Visual Studio], adding
- Office documents [Office development in Visual Studio, host controls
- user controls [Office development in Visual Studio], adding at run time
- documents [Office development in Visual Studio], Windows Forms controls
- document-level customizations [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- document-level customizations [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], adding at run time
- helper methods [Office development in Visual Studio]
ms.assetid: 4f43b3eb-f0ec-44e2-9885-6ede327c6913
caps.latest.revision: "102"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: db8a4fad73bb710662ce63bd299751c725e0c6ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="adding-controls-to-office-documents-at-run-time"></a>Přidání ovládacích prvků do dokumentů Office za běhu
  Ovládací prvky na dokument aplikace Microsoft Office Word a sešitu aplikace Microsoft Office Excel můžete přidat za běhu. Můžete také odebrat je za běhu. Ovládací prvky, které můžete přidat nebo odebrat za běhu, se nazývají *dynamických ovládacích prvků*.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 Toto téma obsahuje následující části:  
  
-   [Správa ovládacích prvků za běhu pomocí ovládacího prvku kolekce](#ControlsCollection).  
  
-   [Hostitelské ovládací prvky přidávání do dokumentů](#HostControls).  
  
-   [Přidání ovládacích prvků Windows Forms do dokumentů](#WindowsForms).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: Přidání ovládacích prvků na plochu dokumentu za běhu?](http://go.microsoft.com/fwlink/?LinkId=132782).  
  
##  <a name="ControlsCollection"></a>Správa ovládacích prvků za běhu pomocí ovládacího prvku kolekce  
 Chcete-li přidat, získat nebo odebrat ovládacích prvků za běhu, použijte pomocné metody <xref:Microsoft.Office.Tools.Excel.ControlCollection> a <xref:Microsoft.Office.Tools.Word.ControlCollection> objekty.  
  
 Přístup k těmto objektům způsob závisí na typu projektu, které vyvíjíte:  
  
-   V projektech na úrovni dokumentu pro Excel, použijte <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> vlastnost `Sheet1`, `Sheet2`, a `Sheet3` třídy. Další informace o těchto tříd naleznete v tématu [hostitelská položka Worksheet](../vsto/worksheet-host-item.md).  
  
-   V projektech na úrovni dokumentu pro Word, použijte <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> vlastnost `ThisDocument` třídy. Další informace o této třídy najdete v tématu [hostitelská položka Document](../vsto/document-host-item.md).  
  
-   V projektu doplňku VSTO pro Excel nebo Word pomocí vlastnosti ovládacích prvků <xref:Microsoft.Office.Tools.Excel.Worksheet> nebo <xref:Microsoft.Office.Tools.Word.Document> generovaná za běhu. Další informace o generování tyto objekty v době běhu najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="adding-controls"></a>Přidání ovládacích prvků  
 <xref:Microsoft.Office.Tools.Excel.ControlCollection> a <xref:Microsoft.Office.Tools.Word.ControlCollection> typů obsahuje pomocné metody, které můžete použít k přidání hostitelské ovládací prvky a běžné ovládací prvky Windows Forms k dokumentům a listů. Každý název metody má formát `Add` *třídu ovládacího prvku*, kde *třídu ovládacího prvku* je název třídy ovládací prvek, který chcete přidat. Chcete-li například přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do dokumentu pomocí <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddNamedRange%2A> metoda.  
  
 Následující příklad kódu přidá <xref:Microsoft.Office.Tools.Excel.NamedRange> k `Sheet1` v projektech na úrovni dokumentu pro Excel.  
  
 [!code-vb[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#3)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#3)]  
  
### <a name="accessing-and-deleting-controls"></a>Přístup k informacím a odstranění ovládacích prvků  
 Můžete použít vlastnost ovládací prvky <xref:Microsoft.Office.Tools.Excel.Worksheet> nebo <xref:Microsoft.Office.Tools.Word.Document> k iteraci v rámci všech ovládacích prvků v dokumentu, včetně kontrol, které jste přidali v době návrhu. Ovládací prvky, které přidáte v době návrhu se také nazývají *statické ovládací prvky*.  
  
 Volání metody odstranění ovládacího prvku, nebo pomocí volání metody odebrat jednotlivých ovládacích prvků kolekcí můžete odebrat dynamických ovládacích prvků. Následující příklad kódu používá <xref:Microsoft.Office.Tools.Excel.ControlCollection.Remove%2A> metoda odebrat <xref:Microsoft.Office.Tools.Excel.NamedRange> z `Sheet1` v projektech na úrovni dokumentu pro Excel.  
  
 [!code-vb[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#4)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#4)]  
  
 Nelze odebrat statické ovládací prvky v době běhu. Pokud se pokusíte použít metodu odstranění nebo odebrání k odebrání statické ovládacího prvku, <xref:Microsoft.Office.Tools.CannotRemoveControlException> bude vyvolána.  
  
> [!NOTE]  
>  Neodebírejte ovládacích prvků v programu `Shutdown` obslužné rutiny události dokumentu. Prvky uživatelského rozhraní dokumentu již nejsou k dispozici při `Shutdown` událost se vyvolá. Pokud chcete odebrat ovládacích prvků, než zavře dokumentu, přidejte kód na obslužnou rutinu události pro jinou událost, například <xref:Microsoft.Office.Tools.Word.Document.BeforeClose> nebo <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> pro Word, nebo <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeClose>, nebo <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeSave> pro aplikaci Excel.  
  
##  <a name="HostControls"></a>Hostitelské ovládací prvky přidávání do dokumentů  
 Když do dokumentů prostřednictvím kódu programu přidáte hostitelské ovládací prvky, je nutné zadat název, který jednoznačně identifikuje ovládacího prvku a musíte určit, kde chcete přidat ovládací prvek v dokumentu. Konkrétní pokyny naleznete v následujících tématech:  
  
-   [Postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md)  
  
-   [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)  
  
-   [Postupy: Přidání ovládacích prvků graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md)  
  
-   [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)  
  
-   [Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)  
  
 Další informace o hostitelských ovládacích prvcích najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
 Pokud dokument je uložit a potom uzavřen, všechny dynamicky vytvořený hostitelské ovládací prvky jsou odpojené od jejich události a nich došlo ke ztrátě jejich funkce vazby dat. Můžete přidat kód pro vaše řešení se znovu vytvořit hostitelské ovládací prvky, když znovu otevřete dokument. Další informace najdete v tématu [uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
> [!NOTE]  
>  Nejsou zadány pomocné metody pro následující hostování ovládacích prvků, protože tyto ovládací prvky nemohou být přidány do dokumentů prostřednictvím kódu programu: <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>, <xref:Microsoft.Office.Tools.Word.XMLNode>, a <xref:Microsoft.Office.Tools.Word.XMLNodes>.  
  
##  <a name="WindowsForms"></a>Přidání Windows Forms ovládacích prvků do dokumentů  
 Když přidáte prostřednictvím kódu programu ovládacího prvku Windows Forms k dokumentu, je nutné zadat umístění ovládacího prvku a název, který jednoznačně identifikuje ovládacího prvku. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Poskytuje pomocné metody pro každý ovládací prvek. Tyto metody jsou přetížený, takže můžete předat rozsah nebo konkrétní souřadnice umístění ovládacího prvku.  
  
 Po uložení dokumentu a poté uzavřen, se odeberou všechny dynamicky vytvářených ovládacích prvků Windows Forms z dokumentu. Můžete přidat kód pro vaše řešení se znovu vytvořit ovládacích prvků, když znovu otevřete dokument. Pokud vytvoříte dynamické ovládací prvky Windows Forms pomocí doplňku VSTO, obálky ActiveX pro ovládací prvky jsou ponechána v dokumentu. Další informace najdete v tématu [uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
> [!NOTE]  
>  Ovládací prvky Windows Forms nelze přidat do chráněných dokumentů prostřednictvím kódu programu. Pokud jste prostřednictvím kódu programu Odemknout dokument aplikace Word nebo sešit aplikace Excel k přidání ovládacího prvku, musíte napsat další kód odebrat obálky ovládacího prvku ActiveX při zavření v dokumentu. Obálky ovládacího prvku ActiveX není automaticky odstraněn z chráněné dokumenty.  
  
### <a name="adding-custom-controls"></a>Přidání vlastních ovládacích prvků  
 Pokud chcete přidat <xref:System.Windows.Forms.Control> nepodporuje k dispozici pomocné metody, jako je například vlastní uživatelský ovládací prvek, použít následující metody:  
  
-   Pro aplikaci Excel, použijte jednu z <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> metody <xref:Microsoft.Office.Tools.Excel.ControlCollection> objektu.  
  
-   Pro Word, použijte jednu z <xref:Microsoft.Office.Tools.Word.ControlCollection.AddControl%2A> metody <xref:Microsoft.Office.Tools.Word.ControlCollection> objektu.  
  
 Chcete-li přidat ovládací prvek, předat <xref:System.Windows.Forms.Control>, umístění pro ovládací prvek a název, který jednoznačně identifikuje metodu AddControl ovládacího prvku. Metoda AddControl vrátí objekt, který definuje, jak ovládacího prvku komunikuje s list nebo dokument. Vrátí metodu AddControl <xref:Microsoft.Office.Tools.Excel.ControlSite> (pro aplikaci Excel) nebo <xref:Microsoft.Office.Tools.Word.ControlSite> objektu (pro Word).  
  
 Následující příklad kódu ukazuje, jak používat <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> metody dynamicky přidat vlastní uživatelský ovládací prvek na list v projektech na úrovni dokumentu aplikace Excel. V tomto příkladu je název uživatelského ovládacího prvku `UserControl1`a <xref:Microsoft.Office.Interop.Excel.Range> jmenuje `range1`. Pokud chcete použít v tomto příkladu, spusťte z `Sheet`  *n*  – třída v projektu.  
  
 [!code-vb[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#2)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#2)]  
  
### <a name="using-members-of-custom-controls"></a>Používání členů vlastních ovládacích prvků  
 Po přidání ovládacího prvku do listu nebo dokumentu pomocí jedné z metod AddControl, nyní máte dva objekty různé ovládacího prvku:  
  
-   <xref:System.Windows.Forms.Control> Představující vlastního ovládacího prvku.  
  
-   ControlSite, objekt OLE nebo OLEControl objekt, který reprezentuje ovládací prvek po byla přidána do listu nebo dokumentu.  
  
 Mnoho vlastnosti a metody jsou sdílené mezi tyto ovládací prvky. Je důležité, přístup k tito členové, a to pomocí vhodného řízení:  
  
-   Pro přístup k členy, které patří pouze do vlastního ovládacího prvku, použijte <xref:System.Windows.Forms.Control>.  
  
-   Pro přístup k členy, které jsou sdíleny ovládacích prvků, použijte objekt ControlSite, objekt OLE nebo OLEControl.  
  
 Pokud máte přístup k sdíleného člena z <xref:System.Windows.Forms.Control>, může selhat bez upozornění a oznámení, nebo ji může vytvořit neplatná výsledky. Vždy použijte metody nebo vlastnosti objektu ControlSite, objekt OLE nebo OLEControl Pokud metody nebo vlastnosti, které jsou potřebné není k dispozici. pak by měl odkazujete <xref:System.Windows.Forms.Control>.  
  
 Například i <xref:Microsoft.Office.Tools.Excel.ControlSite> třídy a <xref:System.Windows.Forms.Control> třídy mají vlastnost nejvyšší. Pro získání nebo nastavení vzdálenost mezi horní části ovládacího prvku a horní části dokumentu, použijte <xref:Microsoft.Office.Tools.Excel.ControlSite.Top%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.ControlSite>, nikoli <xref:System.Windows.Forms.Control.Top%2A> vlastnost <xref:System.Windows.Forms.Control>.  
  
 [!code-vb[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#3)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#3)]  
  
## <a name="see-also"></a>Viz také  
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md)   
 [Postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Postupy: Přidání ovládacích prvků graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Windows Forms – ovládací prvky na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Postupy: Přidání ovládacích prvků do dokumentů Office Windows Forms](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
