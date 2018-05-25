---
title: 'Postupy: Přidání obsahu ovládacích prvků do dokumentů aplikace Word'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- DropDownListContentControl, adding to documents
- BuildingBlockGalleryContentControl, adding to documents
- partial document protection [Office development in Visual Studio]
- RichTextContentControl, adding to documents
- Word [Office development in Visual Studio], partial document protection
- content controls [Office development in Visual Studio], protecting
- PictureContentControl, adding to documents
- GroupContentControl, adding to documents
- document protection [Office development in Visual Studio]
- PlainTextContentControl, adding to documents
- content controls [Office development in Visual Studio], adding
- ComboBoxContentControl, adding to documents
- DatePickerContentControl, adding to documents
- Word [Office development in Visual Studio], restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9ac9fbb7528559189dc74d1bf5c1d9645e47f261
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-add-content-controls-to-word-documents"></a>Postupy: Přidání obsahu ovládacích prvků do dokumentů aplikace Word
  V aplikaci Word projekty na úrovni dokumentu můžete přidat ovládací prvky obsahu v dokumentu ve vašem projektu, v době návrhu nebo za běhu. V projektu doplňku VSTO pro Word můžete přidat ovládací prvky obsahu pro všechny otevřené dokumenty za běhu.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Toto téma popisuje následující úlohy:  
  
-   [Přidání ovládacích prvků obsahu v době návrhu](#designtime)  
  
-   [Přidání ovládacích prvků obsahu za běhu v projektech na úrovni dokumentu](#runtimedoclevel)  
  
-   [Přidání ovládacích prvků obsahu za běhu v projektu doplňku VSTO](#runtimeaddin)  
  
 Informace o ovládacích prvcích obsahu najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md).  
  
##  <a name="designtime"></a> Přidání obsahu ovládací prvky v době návrhu  
 Přidání ovládacích prvků obsahu v dokumentu v projektech na úrovni dokumentu v době návrhu několika způsoby:  
  
-   Přidání obsahu ovládacího prvku z **ovládací prvky aplikace Word** kartě **sada nástrojů**.  
  
-   Přidání obsahu ovládacího prvku do dokumentu stejným způsobem by přidání nativní obsahu ovládacího prvku v aplikaci Word.  
  
-   Přetáhněte ovládací prvek obsahu do dokumentu z **zdroje dat** okno. To je užitečné, pokud chcete vytvořit vazbu ovládacího prvku na data, při vytvoření ovládacího prvku. Další informace najdete v tématu [postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md) a [postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-content-control-to-a-document-by-using-the-toolbox"></a>Přidání obsahu ovládacího prvku do dokumentu pomocí sady nástrojů  
  
1.  V dokumentu, který je hostován v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, umístěte kurzor na místo, kde chcete přidat obsahu ovládací prvek, nebo vyberte text, který má obsah ovládacího prvku nahradit.  
  
2.  Otevřete **sada nástrojů** a klikněte na tlačítko **ovládací prvky aplikace Word** kartě.  
  
3.  Přidání ovládacího prvku, jednu z následujících způsobů:  
  
    -   Dvakrát klikněte na ovládací prvek v obsahu **sada nástrojů**.  
  
         or  
  
    -   Klikněte na ovládací prvek obsahu v **sada nástrojů** a potom stiskněte klávesu **Enter** klíč.  
  
         or  
  
    -   Přetáhněte ovládací prvek obsahu z **sada nástrojů** k dokumentu. Obsahu ovládací prvek přidán na aktuální výběr v dokumentu, není v umístění ukazatele myši.  
  
> [!NOTE]  
>  Nelze přidat <xref:Microsoft.Office.Tools.Word.GroupContentControl> pomocí **sada nástrojů**. Můžete přidat pouze <xref:Microsoft.Office.Tools.Word.GroupContentControl> v aplikaci Word nebo za běhu.  
  
> [!NOTE]  
>  Visual Studio neposkytuje ovládací prvek zaškrtávací políčko obsahu v panelu nástrojů. Chcete-li přidat obsahu ovládací prvek zaškrtávací políčko k dokumentu, musíte vytvořit <xref:Microsoft.Office.Tools.Word.ContentControl> objektu prostřednictvím kódu programu. Další informace najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md).  
  
#### <a name="to-add-a-content-control-to-a-document-in-word"></a>Přidání obsahu ovládacího prvku na dokument v aplikaci Word  
  
1.  V dokumentu, který je hostován v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, umístěte kurzor na místo, kde chcete přidat obsahu ovládací prvek, nebo vyberte text, který má obsah ovládacího prvku nahradit.  
  
2.  Na pásu karet klikněte na **vývojáře** kartě.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný, musíte ji nejdříve zobrazit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
3.  V **ovládací prvky** skupiny, klepněte na ikonu pro ovládací prvek obsahu, který chcete přidat.  
  
##  <a name="runtimedoclevel"></a> Přidání ovládacích prvků obsahu za běhu v projektech na úrovni dokumentu  
 Přidáním ovládací prvky obsahu prostřednictvím kódu programu do dokumentu za běhu pomocí metody <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> vlastnost `ThisDocument` třídy ve vašem projektu. Každá z metod má tři přetížení, které můžete použít k přidání obsahu ovládacího prvku následujícím způsobem:  
  
-   Přidání ovládacího prvku v aktuálním výběru.  
  
-   Přidání ovládacího prvku v zadaném rozsahu.  
  
-   Přidání ovládacího prvku, který je založen na nativní obsahu ovládacího prvku v dokumentu.  
  
 Dynamicky vytvoří obsahu, které nejsou trvalé ovládací prvky v dokumentu, při zavření dokumentu. Nativní obsahu ovládacího prvku však zůstane v dokumentu. Ovládací prvek obsahu, která je založená na nativní obsahu ovládacího prvku při příštím otevření dokumentu můžete znovu vytvořit. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
> [!NOTE]  
>  Chcete-li přidat obsahu ovládací prvek zaškrtávací políčko k dokumentu ve Wordu 2010 projektu, musíte vytvořit <xref:Microsoft.Office.Tools.Word.ContentControl> objektu. Další informace najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md).  
  
### <a name="to-add-a-content-control-at-the-current-selection"></a>Přidání obsahu ovládacího prvku na aktuální výběr  
  
1.  Použití <xref:Microsoft.Office.Tools.Word.ControlCollection> metoda, která má název `Add` \< *třídu ovládacího prvku*> (kde *třídu ovládacího prvku* je název třídy obsahu ovládacího prvku, který chcete přidat, jako je například <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), a který má jeden parametr pro název nového ovládacího prvku.  
  
     Následující příklad kódu používá <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> metoda pro přidání nové <xref:Microsoft.Office.Tools.Word.RichTextContentControl> na začátek dokumentu. Pokud chcete spustit tento kód, přidejte kód, který `ThisDocument` třídy v projektu a volání `AddRichTextControlAtSelection` metoda z `ThisDocument_Startup` obslužné rutiny události.  
  
     [!code-csharp[Trin_ContentControlReference#700](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#700)]
     [!code-vb[Trin_ContentControlReference#700](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#700)]  
  
### <a name="to-add-a-content-control-at-a-specified-range"></a>Přidání obsahu ovládacího prvku v zadaném rozsahu  
  
1.  Použití <xref:Microsoft.Office.Tools.Word.ControlCollection> metoda, která má název `Add` \< *třídu ovládacího prvku*> (kde *třídu ovládacího prvku* je název třídy obsahu ovládacího prvku, který chcete přidat, jako je například <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), a který má <xref:Microsoft.Office.Interop.Word.Range> parametr.  
  
     Následující příklad kódu používá <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> metoda pro přidání nové <xref:Microsoft.Office.Tools.Word.RichTextContentControl> na začátek dokumentu. Pokud chcete spustit tento kód, přidejte kód, který `ThisDocument` třídy v projektu a volání `AddRichTextControlAtRange` metoda z `ThisDocument_Startup` obslužné rutiny události.  
  
     [!code-csharp[Trin_ContentControlReference#701](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#701)]
     [!code-vb[Trin_ContentControlReference#701](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#701)]  
  
### <a name="to-add-a-content-control-that-is-based-on-a-native-content-control"></a>Chcete-li přidat ovládací prvek obsahu, který je založen na nativní obsahu ovládacího prvku  
  
1.  Použití <xref:Microsoft.Office.Tools.Word.ControlCollection> metoda, která má název `Add` \< *třídu ovládacího prvku*> (kde *třídu ovládacího prvku* je název třídy obsahu ovládacího prvku, který chcete přidat, jako je například <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), a který má `Microsoft.Office.Interop.Word.ContentControl` parametr.  
  
     Následující příklad kódu používá <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> metodu pro vytvoření nové <xref:Microsoft.Office.Tools.Word.RichTextContentControl> každých nativní RTF ovládacího prvku, který je v dokumentu. Pokud chcete spustit tento kód, přidejte kód, který `ThisDocument` třídy v projektu a volání `CreateRichTextControlsFromNativeControls` metoda z `ThisDocument_Startup` obslužné rutiny události.  
  
     [!code-csharp[Trin_ContentControlReference#702](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#702)]
     [!code-vb[Trin_ContentControlReference#702](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#702)]  
  
##  <a name="runtimeaddin"></a> Přidání ovládacích prvků obsahu za běhu v projektu doplňku VSTO  
 Ovládací prvky obsahu můžete přidat prostřednictvím kódu programu otevřete dokumentu za běhu pomocí doplňku VSTO. Chcete-li to provést, vygenerovat <xref:Microsoft.Office.Tools.Word.Document> hostitelem položku, která je založená na dokument otevřít a potom pomocí metody <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> vlastnosti této položky hostitele. Každá z metod má tři přetížení, které můžete použít k přidání obsahu ovládacího prvku následujícím způsobem:  
  
-   Přidání ovládacího prvku v aktuálním výběru.  
  
-   Přidání ovládacího prvku v zadaném rozsahu.  
  
-   Přidání ovládacího prvku, který je založen na nativní obsahu ovládacího prvku v dokumentu.  
  
 Dynamicky vytvoří obsahu, které nejsou trvalé ovládací prvky v dokumentu, při zavření dokumentu. Nativní obsahu ovládacího prvku však zůstane v dokumentu. Ovládací prvek obsahu, která je založená na nativní obsahu ovládacího prvku při příštím otevření dokumentu můžete znovu vytvořit. Další informace najdete v tématu [uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
 Další informace o generování hostitelských položkách v projekty doplňku VSTO v tématu [dokumentů rozšířit aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
> [!NOTE]  
>  Chcete-li přidat obsahu ovládací prvek zaškrtávací políčko k dokumentu, musíte vytvořit <xref:Microsoft.Office.Tools.Word.ContentControl> objektu. Další informace najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md).  
  
### <a name="to-add-a-content-control-at-the-current-selection"></a>Přidání obsahu ovládacího prvku na aktuální výběr  
  
1.  Použití <xref:Microsoft.Office.Tools.Word.ControlCollection> metoda, která má název `Add` \< *třídu ovládacího prvku*> (kde *třídu ovládacího prvku* je název třídy obsahu ovládacího prvku, který chcete přidat, jako je například <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), a který má jeden parametr pro název nového ovládacího prvku.  
  
     Následující příklad kódu používá <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> metoda pro přidání nové <xref:Microsoft.Office.Tools.Word.RichTextContentControl> na začátek aktivní dokument. Pokud chcete spustit tento kód, přidejte kód, který `ThisAddIn` třídy v projektu a volání `AddRichTextControlAtSelection` metoda z `ThisAddIn_Startup` obslužné rutiny události.  
  
     [!code-vb[Trin_WordAddInDynamicControls#1](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInDynamicControls#1](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#1)]  
  
### <a name="to-add-a-content-control-at-a-specified-range"></a>Přidání obsahu ovládacího prvku v zadaném rozsahu  
  
1.  Použití <xref:Microsoft.Office.Tools.Word.ControlCollection> metoda, která má název `Add` \< *třídu ovládacího prvku*> (kde *třídu ovládacího prvku* je název třídy obsahu ovládacího prvku, který chcete přidat, jako je například <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), a který má <xref:Microsoft.Office.Interop.Word.Range> parametr.  
  
     Následující příklad kódu používá <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> metoda pro přidání nové <xref:Microsoft.Office.Tools.Word.RichTextContentControl> na začátek aktivní dokument. Pokud chcete spustit tento kód, přidejte kód, který `ThisAddIn` třídy v projektu a volání `AddRichTextControlAtRange` metoda z `ThisAddIn_Startup` obslužné rutiny události.  
  
     [!code-vb[Trin_WordAddInDynamicControls#2](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#2)]
     [!code-csharp[Trin_WordAddInDynamicControls#2](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#2)]  
  
#### <a name="to-add-a-content-control-that-is-based-on-a-native-content-control"></a>Chcete-li přidat ovládací prvek obsahu, který je založen na nativní obsahu ovládacího prvku  
  
1.  Použití <xref:Microsoft.Office.Tools.Word.ControlCollection> metoda, která má název `Add` \< *třídu ovládacího prvku*> (kde *třídu ovládacího prvku* je název třídy obsahu ovládacího prvku, který chcete přidat, jako je například <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), a který má `Microsoft.Office.Interop.Word.ContentControl` parametr.  
  
     Následující příklad kódu používá <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> metodu pro vytvoření nové <xref:Microsoft.Office.Tools.Word.RichTextContentControl> každých nativní RTF ovládacího prvku, který je v dokumentu, po otevření dokumentu. Pokud chcete spustit tento kód, přidejte kód, který `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_WordAddInDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#3)]
     [!code-csharp[Trin_WordAddInDynamicControls#3](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#3)]  
  
     Pro jazyk C#, musíte připojit `Application_DocumentOpen` obslužná rutina události <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> událostí.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#6](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#6)]  
  
## <a name="see-also"></a>Viz také  
 [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Úpravy na úrovni dokumentů programu](../vsto/programming-document-level-customizations.md)  
  