---
title: "Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.Bookmark.Dialog
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Bookmark control, adding to documents
- Create Bookmark Control dialog box
- controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 2ebe8536887f2f60876b64407ffb96cdaf4618c9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-bookmark-controls-to-word-documents"></a>Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word
  Projekty na úrovni dokumentu, můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky v dokumentu ve vašem projektu v době návrhu nebo za běhu. Projekty doplňku VSTO, můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky pro všechny otevřené dokumenty v době běhu.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Toto téma popisuje následující úlohy:  
  
-   [Přidání ovládacích prvků záložek v době návrhu](#designtime)  
  
-   [Přidání ovládacích prvků záložek za běhu v projektech na úrovni dokumentu](#runtimedoclevel)  
  
-   [Přidání ovládacích prvků záložek za běhu v projektu doplňku VSTO](#runtimeaddin)  
  
 Další informace o <xref:Microsoft.Office.Tools.Word.Bookmark> najdete v části ovládací prvky, [ovládacího prvku záložek](../vsto/bookmark-control.md).  
  
##  <a name="designtime"></a>Přidání ovládacích prvků záložek v době návrhu  
 Existuje několik způsobů, jak přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky v dokumentu v projektech na úrovni dokumentu v době návrhu:  
  
-   Ze sady Visual Studio **sada nástrojů**.  
  
     Můžete přetáhnout <xref:Microsoft.Office.Tools.Word.Bookmark> řídit z **sada nástrojů** do dokumentu. Můžete chtít tímto způsobem vyberte, pokud už používáte **sada nástrojů** k přidávání ovládacích prvků Windows Forms do dokumentu.  
  
-   V rámci aplikace Word.  
  
     Můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> řízení chcete dokument stejným způsobem, měli byste přidat nativní záložky. Výhodou přidáním tímto způsobem je, že zadáte název vlastního ovládacího prvku v době, musíte ji vytvořit.  
  
-   Z **zdroje dat** okno.  
  
     Můžete přetáhnout <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku do dokumentu z **zdroje dat** okno. To je užitečné, pokud chcete vytvořit vazbu ovládacího prvku k datům ve stejnou dobu. Můžete přidat stejným způsobem, jako by přidání ovládacího prvku formuláře Windows z hostitelského ovládacího prvku **zdroje dat** okno. Další informace najdete v tématu [datové vazby a rozhraní Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-add-a-bookmark-control-to-a-document-from-the-toolbox"></a>Přidání ovládacího prvku záložek do dokumentu z panelu nástrojů  
  
1.  Otevřete **sada nástrojů** a klikněte na tlačítko **ovládací prvky aplikace Word** kartě.  
  
2.  Přetáhněte <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek v dokumentu.  
  
     **Přidat záložku** zobrazí se dialogové okno.  
  
3.  Vyberte text, nebo další položky, které chcete zahrnout do záložky.  
  
4.  Click **OK**.  
  
     Pokud nechcete, aby záložku výchozí název, můžete změnit název v **vlastnosti** okno.  
  
#### <a name="to-add-a-bookmark-control-to-a-document-in-word"></a>Přidání ovládacího prvku záložek do dokumentů aplikace Word  
  
1.  V dokumentu, který je hostován v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, umístěte kurzor na místo, kde chcete přidat záložku, nebo vyberte text, který má záložka uzavřete.  
  
2.  Na **vložit** karty na pásu karet v **odkazy** klikněte na možnost **záložku** tlačítko.  
  
3.  V **záložku** dialogové okno, zadejte název nové záložky a klikněte na tlačítko **přidat**.  
  
##  <a name="runtimedoclevel"></a>Přidání ovládacích prvků záložek za běhu v projektech na úrovni dokumentu  
 Můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> řídí prostřednictvím kódu programu do dokumentu za běhu pomocí metody <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> vlastnost `ThisDocument` třídy ve vašem projektu. Existují dvě přetížení metody, které můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> řízení následujícími způsoby:  
  
-   Přidat <xref:Microsoft.Office.Tools.Word.Bookmark> v zadaném rozsahu.  
  
-   Přidat <xref:Microsoft.Office.Tools.Word.Bookmark> založený na nativním záložky v dokumentu (to znamená, <xref:Microsoft.Office.Interop.Word.Bookmark>).  
  
 Dynamicky vytvořit <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky nejsou trvalé v dokumentu, při zavření v dokumentu. Však nativní <xref:Microsoft.Office.Interop.Word.Bookmark> zůstane v dokumentu. Můžete znovu vytvořit <xref:Microsoft.Office.Tools.Word.Bookmark> založený na nativním záložku při příštím otevření dokumentu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-bookmark-control-to-a-document-programmatically"></a>Přidání ovládacího prvku záložek do dokumentu prostřednictvím kódu programu  
  
1.  V `ThisDocument_Startup` obslužné rutiny událostí v projektu, vložte následující kód do přidat <xref:Microsoft.Office.Tools.Word.Bookmark> řízení prvním odstavci v dokumentu.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#1](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreHostControlsWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#1)]  
  
    > [!NOTE]  
    >  Pokud chcete vytvořit <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek z existující <xref:Microsoft.Office.Interop.Word.Bookmark>, použijte <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> metoda a předejte jí existující <xref:Microsoft.Office.Interop.Word.Bookmark>.  
  
##  <a name="runtimeaddin"></a>Přidání ovládacích prvků záložek za běhu v projektu doplňku VSTO  
 Můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky prostřednictvím kódu programu pro všechny otevřené dokumenty v době běhu pomocí doplňku VSTO. Chcete-li to provést, vygenerovat <xref:Microsoft.Office.Tools.Word.Document> hostitelem položku, která je založená na dokument otevřít a potom pomocí metody <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> vlastnosti této položky hostitele. Existují dvě přetížení metody, které můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> řízení následujícími způsoby:  
  
-   Přidat <xref:Microsoft.Office.Tools.Word.Bookmark> v zadaném rozsahu.  
  
-   Přidat <xref:Microsoft.Office.Tools.Word.Bookmark> založený na nativním záložky v dokumentu (to znamená, <xref:Microsoft.Office.Interop.Word.Bookmark>).  
  
 Dynamicky vytvořit <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky nejsou trvalé v dokumentu, při zavření v dokumentu. Však nativní <xref:Microsoft.Office.Interop.Word.Bookmark> zůstane v dokumentu. Můžete znovu vytvořit <xref:Microsoft.Office.Tools.Word.Bookmark> založený na nativním záložku při příštím otevření dokumentu. Další informace najdete v tématu [uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
 Další informace o generování hostitelských položkách v projekty doplňku VSTO v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
#### <a name="to-add-a-bookmark-control-at-a-specified-range"></a>Přidání ovládacího prvku záložek v zadaném rozsahu  
  
1.  Použití <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> metoda a předejte jí <xref:Microsoft.Office.Interop.Word.Range> ve které chcete přidat <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
     Následující příklad kódu přidá nový <xref:Microsoft.Office.Tools.Word.Bookmark> na začátek aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn_Startup` obslužné rutiny události v projektu doplňku VSTO pro Word.  
  
     [!code-vb[Trin_WordAddInDynamicControls#4](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#4)]
     [!code-csharp[Trin_WordAddInDynamicControls#4](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#4)]  
  
#### <a name="to-add-a-bookmark-control-that-is-based-on-a-native-bookmark-control"></a>Přidání ovládacího prvku záložek založený na nativním ovládacího prvku záložek  
  
1.  Použít <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> metoda a předejte jí existující <xref:Microsoft.Office.Interop.Word.Bookmark> , kterou chcete použít jako základ pro nové <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
     Následující příklad kódu vytvoří novou <xref:Microsoft.Office.Tools.Word.Bookmark> tedy podle první <xref:Microsoft.Office.Interop.Word.Bookmark> v aktivním dokumentu. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn_Startup` obslužné rutiny události v projektu doplňku VSTO pro Word.  
  
     [!code-vb[Trin_WordAddInDynamicControls#5](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#5)]
     [!code-csharp[Trin_WordAddInDynamicControls#5](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#5)]  
  
## <a name="see-also"></a>Viz také  
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Postupy: Změna velikosti ovládacích prvků záložek](../vsto/how-to-resize-bookmark-controls.md)  
  
  