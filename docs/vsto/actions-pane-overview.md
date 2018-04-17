---
title: Přehled podokna akcí | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- actions panes [Office development in Visual Studio], about actions panes
- actions panes [Office development in Visual Studio]
- smart documents [Office development in Visual Studio]
- user controls [Office development in Visual Studio], actions panes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 902301021a698dfd0f6e9f09b000c1e4e403e029
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="actions-pane-overview"></a>Přehled podokna akcí
  Podokna akcí je nastavit vlastní **akcích dokumentu** podokna úloh, který je připojený ke konkrétní dokument aplikace Microsoft Office Word nebo sešitu aplikace Microsoft Office Excel. Je umístěn uvnitř do podokna úloh Office spolu s další podokna integrované úlohy, jako **zdroj dat XML** v aplikaci Excel nebo **styly a formátování** podokna úloh v aplikaci Word. Ovládací prvky Windows Forms nebo ovládacích prvků WPF slouží k návrhu uživatelské rozhraní podokna akce.  

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  

 Podokna akcí můžete vytvořit pouze v přizpůsobení na úrovni dokumentu pro Word či Excel. Podokna akcí nelze vytvořit v doplňku VSTO. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  

> [!NOTE]  
>  V podokně Akce se liší od vlastní podokna úloh. Vlastní podokna úloh jsou přidružené k aplikaci, ne určitého dokumentu. Vlastní podokna úloh můžete vytvořit v doplňcích VSTO pro některé aplikace Microsoft Office. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  

 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: použití WPF ovládací prvky uvnitř aplikaci Excel podokna akce?](http://go.microsoft.com/fwlink/?LinkId=132763).  

## <a name="displaying-the-actions-pane"></a>Zobrazení podokna akce  
 V podokně Akce je reprezentována <xref:Microsoft.Office.Tools.ActionsPane> třídy. Když vytvoříte projekt na úrovni dokumentu a, instance této třídy je k dispozici kódu pomocí `ActionsPane` pole z `ThisWorkbook` (pro aplikaci Excel) nebo `ThisDocument` (pro aplikaci Word) třídy ve vašem projektu. Pokud chcete zobrazit v podokně Akce, přidání ovládacího prvku Windows Forms k <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> vlastnost `ActionsPane` pole. Následující příklad kódu přidá ovládací prvek s názvem `actions` do podokna akce.  

 [!code-csharp[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#7)]
 [!code-vb[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#7)]  

 V době běhu také explicitně přidat k němu ovládacího prvku se zobrazí v podokně Akce. Jakmile se zobrazí v podokně Akce, můžete dynamicky přidat nebo odebrat ovládací prvky v odpovědi na akce uživatele. Obvykle přidáte kód, který se zobrazí v podokně Akce v `Startup` obslužné rutiny události z `ThisDocument` nebo `ThisWorkbook` tak, aby v podokně Akce když uživatel poprvé otevře dokument. Můžete však zobrazení podokna akce jenom v odpovědi na akci uživatele v dokumentu. Například může přidáte kód, který `Click` události ovládacího prvku na dokumentu.  

### <a name="adding-multiple-controls-to-the-actions-pane"></a>Přidání více ovládacích prvků do podokna akce  
 Chcete-li přidat více ovládacích prvků do podokna akce, ve většině případů doporučujeme seskupování ovládacích prvků v ovládacím prvku uživatele a pak přidat uživatelský ovládací prvek na <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> vlastnost. Tento proces zahrnuje následující kroky:  

1.  Přidáním vytvořit uživatelské rozhraní (UI) v podokně Akce **ovládací prvek podokna akce** nebo **uživatelský ovládací prvek** položku do projektu. Oba tyto položky obsahují vlastní Windows Forms <xref:System.Windows.Forms.UserControl> třídy. **Ovládací prvek podokna akce** a **uživatelský ovládací prvek** položky jsou ekvivalentní; jediným rozdílem je jejich název.  

2.  Přidání ovládacích prvků Windows Forms k <xref:System.Windows.Forms.UserControl> pomocí návrháře, nebo psaní kódu.  

    > [!NOTE]  
    >  Můžete také přidat ovládacích prvků WPF do podokna akce přidáním WPF <xref:System.Windows.Controls.UserControl> do Windows Forms <xref:System.Windows.Forms.UserControl>. Další informace najdete v tématu [pomocí ovládacích prvků WPF v řešeních pro systém Office](../vsto/using-wpf-controls-in-office-solutions.md).  

3.  Přidá instanci vlastního uživatelského ovládacího prvku na ovládací prvky, které jsou součástí `ActionsPane` pole z `ThisWorkbook` (pro aplikaci Excel) nebo `ThisDocument` (pro aplikaci Word) třídy ve vašem projektu.  

 Příklady, které ukazují, tento proces podrobněji najdete v tématu [postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md).  

## <a name="hiding-the-actions-pane"></a>Skrytí podokna akce  
 I když <xref:Microsoft.Office.Tools.ActionsPane> třída má <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> metoda a <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> vlastnost, nelze odstranit podokna akce z uživatelského rozhraní pomocí jakékoli členy <xref:Microsoft.Office.Tools.ActionsPane> třídy sám sebe. Volání <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> metoda nebo nastavení <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> vlastnost **false** skryje pouze ovládací prvky v podokně Akce; ji není skrytí podokna úloh.  

 Skrytí podokna úloh ve vašem řešení, máte několik možností:  

-   Pro Word, nastavte <xref:Microsoft.Office.Interop.Word.TaskPane.Visible%2A> vlastnost <xref:Microsoft.Office.Interop.Word.TaskPane> objekt, který reprezentuje podokna úloh akcích dokumentu a **false**. Následující příklad kódu je určený pro spouštění z `ThisDocument` třídy ve vašem projektu.  

     [!code-csharp[Trin_VstcoreActionsPaneWord#34](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#34)]
     [!code-vb[Trin_VstcoreActionsPaneWord#34](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#34)]  

-   Pro aplikaci Excel, nastavte <xref:Microsoft.Office.Interop.Excel._Application.DisplayDocumentActionTaskPane%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.Workbook.Application%2A> do objektu **false**. Následující příklad kódu je určený pro spouštění z `ThisWorkbook` třídy ve vašem projektu.  

     [!code-csharp[Trin_VstcoreActionsPaneExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#11)]  

-   Pro Word či Excel, můžete také nastavit <xref:Microsoft.Office.Core.CommandBar.Visible%2A> vlastnost panelu příkaz, který představuje do podokna úloh do **false**. Následující příklad kódu je určený pro spouštění z `ThisDocument` nebo `ThisWorkbook` třídy ve vašem projektu.  

     [!code-csharp[Trin_VstcoreActionsPaneExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#9)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#9)]  

### <a name="clearing-the-actions-pane-when-the-document-is-opened"></a>Vymazání akce podokně při dokumentu je otevřen.  
 Pokud uživatel uloží dokument, když je zobrazen v podokně Akce, v podokně Akce je viditelná pokaždé, když je otevřen v dokumentu, zda obsahuje všechny ovládací prvky v podokně Akce. Pokud chcete na ovládací prvek, když se objeví, zavolejte <xref:Microsoft.Office.Tools.ActionsPane.Clear%2A> metodu `ActionsPane` pole `Startup` obslužné rutiny události z `ThisDocument` nebo `ThisWorkbook` zajistit, že v podokně Akce není viditelná při otevření dokumentu.  

### <a name="determining-when-the-actions-pane-is-closed"></a>Určení, když podokně akcí je uzavřený.  
 Neexistuje žádná událost, která se vyvolá při zavření v podokně Akce. I když <xref:Microsoft.Office.Tools.ActionsPane> třída má <xref:Microsoft.Office.Tools.ActionsPane.VisibleChanged> událost, tato událost se vyvolá, když koncový uživatel zavření v podokně Akce. Místo toho tato událost se vyvolá, když jsou voláním skrytý ovládací prvky v podokně Akce <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> metoda nebo nastavením <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> vlastnost **false**.  

 Pokud koncový uživatel zavření v podokně Akce, může uživatel zobrazit ho znovu pomocí jedné z následujících postupů v uživatelském rozhraní (UI) aplikace.  

##### <a name="to-display-the-actions-pane-by-using-the-ui-of-word-or-excel"></a>Chcete-li zobrazit v podokně akce pomocí uživatelského rozhraní aplikace Word a Excel  

1.  Na pásu karet klikněte na **zobrazení** kartě.  

2.  V **zobrazit či skrýt** klikněte na možnost **akcích dokumentu** přepínací tlačítko.  

## <a name="programming-actions-pane-events"></a>Programování akce podokně události  
 Můžete přidat víc uživatelských ovládacích prvků do podokna akce a poté napsat kód pro reakce na události na dokumentu pomocí zobrazení a skrytí uživatelské ovládací prvky. Pokud namapujete prvky schématu XML do dokumentu, můžete zobrazit určité uživatelské ovládací prvky v podokně akce vždy, když je kurzor uvnitř jeden z elementů XML. Další informace najdete v tématu [postupy: mapování schémat Word dokumenty v sadě Visual Studio](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md) a [postupy: mapování schémat na listy v sadě Visual Studio](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md).  

 Také můžete napsat kód pro reakce na události z libovolného objektu, včetně hostitelského ovládacího prvku, aplikace nebo dokumentu události. Další informace najdete v části [návod: programování proti události ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md).  

## <a name="binding-data-to-controls-on-the-actions-pane"></a>Vazba dat s ovládacími prvky v podokně Akce  
 Ovládací prvky v podokně Akce měly stejné funkce vazby dat jako ve Windows Forms – ovládací prvky. Ovládací prvky můžete vázat na zdroje dat jako datové sady, typové datové sady a XML. Další informace najdete v tématu [datové vazby a rozhraní Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  

 V podokně Akce a ovládacích prvků na dokument můžete vázat na stejnou datovou sadu. Můžete například vytvořit hlavní a podrobný vztah mezi ovládacími prvky v podokně Akce a ovládacích prvků na list. Další informace najdete v tématu [návod: vytvoření vazby dat s ovládacími prvky v podokně akcí aplikace Excel](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md).  

## <a name="validating-data-in-actions-pane-controls"></a>Ověřování dat v podokně Akce ovládací prvky  
 Je-li zobrazit okno se zprávou v <xref:System.Windows.Forms.Control.Validating> obslužné rutiny události ovládacího prvku v podokně Akce, události může být vyvolána podruhé, když se aktivuje z ovládacího prvku do pole zpráva. Aby tento problém, použijte <xref:System.Windows.Forms.ErrorProvider> ovládacího prvku pro zobrazení všech chybových zpráv ověření.  

## <a name="user-control-stacking-order"></a>Uživatelský ovládací prvek pořadí překrývání  
 Pokud používáte více uživatelských ovládacích prvků, můžete napsat kód pro správně zásobníku uživatelské ovládací prvky v podokně Akce, zda je ukotvena vodorovně nebo svisle. Skládání pořadí uživatelské ovládací prvky v podokně Akce lze nastavit pomocí <xref:Microsoft.Office.Tools.StackStyle> výčet <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> vlastnost. Další informace najdete v tématu [postupy: Správa rozložení ovládacích prvků v podoknech akcí](../vsto/how-to-manage-control-layout-on-actions-panes.md)  

 <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> Vlastnosti můžete provést následující <xref:Microsoft.Office.Tools.StackStyle> hodnot výčtu.  

|Skládání styl|Definice|  
|--------------------|----------------|  
|FromBottom|Zásobníku v dolní části podokna akce.|  
|FromLeft|Zásobníku v levé části podokna akce.|  
|FromRight|Zásobník vpravo v podokně Akce.|  
|FromTop|Zásobník z horní části podokna akce.|  
|Žádné|Žádné pořadí překrývání definované; pořadí je řízena sám vývojář.|  

 Následující kód nastaví <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> vlastnost zásobníku uživatelské ovládací prvky z horní části podokna akce.  

 [!code-csharp[Trin_VstcoreActionsPaneExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#10)]
 [!code-vb[Trin_VstcoreActionsPaneExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#10)]  

## <a name="anchoring-controls"></a>Ukotvení – ovládací prvky  
 Pokud uživatel změní velikost podokna akce za běhu, ovládací prvky můžete změnit velikost se v podokně Akce. Můžete použít <xref:System.Windows.Forms.Control.Anchor%2A> vlastností ovládacího prvku Windows Forms do ovládacích prvků ukotvení do podokna akce. Ovládací prvky Windows Forms do uživatelského ovládacího prvku můžete také ukotvení stejným způsobem. Další informace najdete v tématu [postupy: ukotvení ovládacích prvků Windows Forms](/dotnet/framework/winforms/controls/how-to-anchor-controls-on-windows-forms).  

## <a name="resizing-the-actions-pane"></a>Změna velikosti podokna akce  
 Nelze přímo změnit velikost <xref:Microsoft.Office.Tools.ActionsPane> protože <xref:Microsoft.Office.Tools.ActionsPane> vložené v podokně úloh. Však můžete programově změnit šířku do podokna úloh nastavením <xref:Microsoft.Office.Core.CommandBar.Width%2A> vlastnost <xref:Microsoft.Office.Core.CommandBar> představující do podokna úloh. Výška do podokna úloh můžete změnit, pokud jej ukotven vodorovně nebo je číslo s plovoucí čárkou.  

 Prostřednictvím kódu programu změnu velikosti podokna úloh obecně nedoporučuje, protože uživatel by měl být moci vybrat velikost podokna úloh, který nejlépe vyhovuje potřebám své. Ale pokud musíte změnit velikost šířku do podokna úloh, můžete použít následující kód k dosažení této úlohy.  

 [!code-csharp[Trin_VstcoreActionsPaneWord#102](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#102)]
 [!code-vb[Trin_VstcoreActionsPaneWord#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#102)]  

## <a name="repositioning-the-actions-pane"></a>Přemístění podokna akce  
 Nelze změnit umístění přímo <xref:Microsoft.Office.Tools.ActionsPane> vzhledem k tomu, že je integrovaný v podokně úloh. Však můžete programově přesunout do podokna úloh nastavením <xref:Microsoft.Office.Core.CommandBar.Position%2A> vlastnost <xref:Microsoft.Office.Core.CommandBar> představující do podokna úloh.  

 Prostřednictvím kódu programu přemístění do podokna úloh obecně nedoporučuje, protože by mohli vybrat pozici podokně úloh na obrazovce, která nejlépe vyhovuje potřebám své uživatele. Ale pokud je nutné přesunout do podokna úloh na konkrétní pozici, můžete použít následující kód k dosažení této úlohy.  

 [!code-csharp[Trin_VstcoreActionsPaneWord#100](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#100)]
 [!code-vb[Trin_VstcoreActionsPaneWord#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#100)]  

> [!NOTE]  
>  Koncoví uživatelé můžete ručně změnit umístění do podokna úloh kdykoli. Neexistuje žádný způsob, jak zajistit, že v podokně úloh zůstane ukotveného na pozici, která jste prostřednictvím kódu programu. Můžete však zjišťovat změny orientaci a ujistěte se, že ovládací prvky v podokně Akce přibývají správným směrem. Další informace najdete v tématu [postupy: Správa rozložení ovládacích prvků v podoknech akcí](../vsto/how-to-manage-control-layout-on-actions-panes.md).  

 Nastavení <xref:Microsoft.Office.Tools.ActionsPane.Top%2A> a <xref:Microsoft.Office.Tools.ActionsPane.Left%2A> vlastnosti <xref:Microsoft.Office.Tools.ActionsPane> nezmění jeho pozice, protože <xref:Microsoft.Office.Tools.ActionsPane> objekt vložený v podokně úloh.  

 Pokud není ukotven do podokna úloh, můžete nastavit <xref:Microsoft.Office.Core.CommandBar.Top%2A> a <xref:Microsoft.Office.Core.CommandBar.Left%2A> vlastnosti <xref:Microsoft.Office.Core.CommandBar> představující do podokna úloh. Následující kód podokna odpojenou úloh přesune do levého horního rohu dokumentu.  

 [!code-csharp[Trin_VstcoreActionsPaneWord#101](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#101)]
 [!code-vb[Trin_VstcoreActionsPaneWord#101](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#101)]  

## <a name="see-also"></a>Viz také  
 [Použití ovládacích prvků grafického subsystému WPF v řešeních pro systém Office](../vsto/using-wpf-controls-in-office-solutions.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Návod: Vložení textu do dokumentu z podokna akcí](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [Návod: Svázání dat s ovládacími prvky v podokně akcí aplikace Word](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)   
 [Návod: Svázání dat s ovládacími prvky v podokně akcí aplikace Excel](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md)   
 [Postupy: Správa rozložení ovládacích prvků v podoknech akcí](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Návod: Vložení textu do dokumentu z podokna akcí](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
