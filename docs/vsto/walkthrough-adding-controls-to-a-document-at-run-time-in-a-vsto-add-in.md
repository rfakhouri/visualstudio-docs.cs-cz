---
title: "Návod: Přidání ovládacích prvků do dokumentu za běhu v doplňku VSTO | Microsoft Docs"
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
- add-ins [Office development in Visual Studio], adding controls
- application-level add-ins [Office development in Visual Studio], adding controls
- controls [Office development in Visual Studio], adding to documents at run time
- documents [Office development in Visual Studio], adding controls at run time
ms.assetid: ab6dff40-9964-468a-938c-a71a3ac23718
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 28ed2ff2d68dc5a23cfceeb5d5f0eab6dea35eb9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-adding-controls-to-a-document-at-run-time-in-a-vsto-add-in"></a>Návod: Přidání ovládacích prvků do dokumentu za běhu v doplňku VSTO
  Ovládací prvky můžete přidat všechny otevřené dokumentu aplikace Microsoft Office Word pomocí doplňku VSTO. Tento návod ukazuje, jak používat na pásu karet k umožnění uživatelům přidat <xref:Microsoft.Office.Tools.Word.Controls.Button> nebo <xref:Microsoft.Office.Tools.Word.RichTextContentControl> do dokumentu.  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty doplňku VSTO pro Word 2010. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření nového projektu doplňku VSTO pro Word.  
  
-   Poskytuje uživatelské rozhraní (UI) a přidání ovládacích prvků v dokumentu.  
  
-   Přidání ovládacích prvků do dokumentu za běhu.  
  
-   Odebrání ovládacích prvků z dokumentu.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-a-new-word-add-in-project"></a>Vytvoření nové aplikace Word přidejte v projektu  
 Začněte vytvořením projektu doplňku VSTO pro Word.  
  
#### <a name="to-create-a-new-word-vsto-add-in-project"></a>K vytvoření nového projektu doplňku VSTO pro Word  
  
1.  Vytvoření projektu doplňku VSTO pro Word s názvem **WordDynamicControls**. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Přidat odkaz na **Microsoft.Office.Tools.Word.v4.0.Utilities.dll** sestavení. Tento odkaz je potřeba prostřednictvím kódu programu Přidání ovládacího prvku Windows Forms v dokumentu dále v tomto návodu.  
  
## <a name="providing-a-ui-to-add-controls-to-a-document"></a>Poskytnutí uživatelského rozhraní k přidávání ovládacích prvků do dokumentu.  
 Přidáte vlastní karty na pásu karet v aplikaci Word. Uživatelé mohou vybrat zaškrtávací políčka na kartě k přidávání ovládacích prvků do dokumentu.  
  
#### <a name="to-provide-a-ui-to-add-controls-to-a-document"></a>K poskytování uživatelského rozhraní k přidávání ovládacích prvků do dokumentu.  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **pásu karet (vizuálního návrháře)**.  
  
3.  Změňte název nové pásu karet na **MyRibbon**a klikněte na tlačítko **přidat**.  
  
     **MyRibbon.cs** nebo **MyRibbon.vb** soubor se otevře v Návrháři pásu karet a zobrazí se výchozí kartě a skupiny.  
  
4.  V Návrháři pásu karet klikněte **group1** skupiny.  
  
5.  V **vlastnosti** změňte **popisek** vlastnost pro **group1** k **přidat ovládací prvky**.  
  
6.  Z **ovládacích prvků pásu karet Office** kartě **sada nástrojů**, přetáhněte **políčko** na ovládací prvek **group1**.  
  
7.  Klikněte na tlačítko **CheckBox1** ji vyberte.  
  
8.  V **vlastnosti** okně změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**addButtonCheckBox**|  
    |**Popisek**|**Tlačítko Přidat**|  
  
9. Přidat druhý zaškrtnutím políčka **group1**a poté změňte následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**addRichTextCheckBox**|  
    |**Popisek**|**Přidání ovládacího prvku formátovaného textu**|  
  
10. V Návrháři pásu karet klikněte dvakrát na **přidat tlačítko**.  
  
     <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> Obslužnou rutinu události **přidat tlačítko** políčko otevře v editoru kódu.  
  
11. Vrátíte do Návrháře pásu karet a dvakrát klikněte na **přidat ovládací prvek Text ve formátu RTF**.  
  
     <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> Obslužnou rutinu události **přidat ovládací prvek Text ve formátu RTF** políčko otevře v editoru kódu.  
  
 Dále v tomto návodu přidáte kód obslužné rutiny těchto událostí k přidání a odebrání ovládacích prvků na aktivní dokument.  
  
## <a name="adding-and-removing-controls-on-the-active-document"></a>Přidávání a odebírání ovládacích prvků v aktivním dokumentu.  
 V doplňku VSTO kódu, je nutné převést aktivní dokument do <xref:Microsoft.Office.Tools.Word.Document> *hostitelská položka* před přidáním ovládacího prvku. V řešení pro systém Office spravované ovládací prvky lze přidat pouze do hostitelské položky, které fungují jako kontejnery pro ovládací prvky. Projekty doplňku VSTO hostitelské položky vytvářet v době běhu pomocí getvstoobject – metoda.  
  
 Přidejte metody do `ThisAddIn` třídu, která lze volat pro přidání nebo odebrání <xref:Microsoft.Office.Tools.Word.Controls.Button> nebo <xref:Microsoft.Office.Tools.Word.RichTextContentControl> v aktivním dokumentu. Dále v tomto návodu budete volat z těchto metod <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> obslužné rutiny událostí zaškrtávacích políček na pásu karet.  
  
#### <a name="to-add-and-remove-controls-on-the-active-document"></a>K přidání a odebrání ovládacích prvků v aktivním dokumentu.  
  
1.  V **Průzkumníku**, dvakrát klikněte na ThisAddIn.cs nebo ThisAddIn.vb k otevření souboru v editoru kódu.  
  
2.  Přidejte následující kód, který `ThisAddIn` třídy. Tento kód deklaruje <xref:Microsoft.Office.Tools.Word.Controls.Button> a <xref:Microsoft.Office.Tools.Word.RichTextContentControl> objekty, které představují ovládací prvky, které budou přidány do dokumentu.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#1](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#1](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#1)]  
  
3.  Přidejte následující metodu do `ThisAddIn` třídy. Když uživatel klikne **přidat tlačítko** políčko na pásu karet, přidá tato metoda <xref:Microsoft.Office.Tools.Word.Controls.Button> na aktuálně vybrané položky v dokumentu, pokud je zaškrtnuto políčko nebo odebere <xref:Microsoft.Office.Tools.Word.Controls.Button> Pokud není políčko zaškrtnuto.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#2](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.vb#2)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#2](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#2)]  
  
4.  Přidejte následující metodu do `ThisAddIn` třídy. Když uživatel klikne **přidat ovládací prvek Text ve formátu RTF** přidá tuto metodu políčko na pásu karet, <xref:Microsoft.Office.Tools.Word.RichTextContentControl> na aktuálně vybrané položky v dokumentu, pokud je zaškrtnuto políčko nebo odebere <xref:Microsoft.Office.Tools.Word.RichTextContentControl> Pokud není políčko zaškrtnuto.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#3](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.vb#3)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#3](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#3)]  
  
## <a name="removing-the-button-control-when-the-document-is-saved"></a>Odebrání tlačítko řízení při dokumentu je uložen  
 Windows Forms – ovládací prvky nejsou trvalé, když je dokument uložit a potom uzavřen. Však ActiveX obálku pro každý ovládací prvek zůstane v dokumentu a ohraničení tuto obálku lze zobrazit koncoví uživatelé, když znovu otevřete dokument. Vyčištění dynamicky vytvořené ovládací prvky Windows Forms v doplňcích VSTO několika způsoby. V tomto návodu prostřednictvím kódu programu odeberete <xref:Microsoft.Office.Tools.Word.Controls.Button> řízení při ukládání dokumentu.  
  
#### <a name="to-remove-the-button-control-when-the-document-is-saved"></a>Při ukládání dokumentu odebrat ovládacího prvku tlačítko  
  
1.  V souboru kódu ThisAddIn.cs nebo ThisAddIn.vb, přidejte následující metodu do `ThisAddIn` třídy. Tato metoda je obslužné rutiny události pro <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> událostí. Pokud má uložený dokument <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka, která souvisí s ním, obslužné rutiny události získá položku hostitele a odebere <xref:Microsoft.Office.Tools.Word.Controls.Button> řízení, pokud existuje.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#4](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.vb#4)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#4](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#4)]  
  
2.  V jazyce C#, přidejte následující kód, který `ThisAddIn_Startup` obslužné rutiny události. Tento kód je vyžadován v jazyce C# pro připojení `Application_DocumentBeforeSave` obslužné rutiny události s <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> událostí.  
  
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#5](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#5)]  
  
## <a name="adding-and-removing-controls-when-the-user-clicks-the-check-boxes-on-the-ribbon"></a>Přidávání a odebírání ovládacích prvků, když uživatel klikne zaškrtávací políčka na pásu karet  
 Nakonec upravte <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> obslužné rutiny událostí zaškrtávacích políček, která jste přidali do pásu karet na přidání nebo odebrání ovládacích prvků na dokumentu.  
  
#### <a name="to-add-or-remove-controls-when-the-user-clicks-the-check-boxes-on-the-ribbon"></a>Přidat nebo odebrat prvky, když uživatel klikne na zaškrtávací políčka na pásu karet  
  
1.  V souboru kódu MyRibbon.cs nebo MyRibbon.vb, nahraďte vygenerovaného `addButtonCheckBox_Click` a `addRichTextCheckBox_Click` obslužné rutiny událostí s následujícím kódem. Tento kód definuje nové tyto obslužné rutiny událostí k volání `ToggleButtonOnDocument` a `ToggleRichTextControlOnDocument` metody, které jste přidali do `ThisAddIn` třída dříve v tomto návodu.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#6](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/MyRibbon.vb#6)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#6](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/MyRibbon.cs#6)]  
  
## <a name="testing-the-solution"></a>Testování řešení  
 Přidání ovládacích prvků do dokumentu tak, že je vyberete z vlastní karty na pásu karet. Při ukládání dokumentu, <xref:Microsoft.Office.Tools.Word.Controls.Button> řízení se odebere.  
  
#### <a name="to-test-the-solution"></a>Testovat řešení.  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  V aktivním dokumentu stiskněte ENTER několikrát přidat nové prázdné odstavce do dokumentu.  
  
3.  Vyberte prvním odstavci.  
  
4.  Klikněte **doplňky** kartě.  
  
5.  V **přidat ovládací prvky** klikněte na možnost **přidat tlačítko**.  
  
     Tlačítko se zobrazí v prvním odstavci.  
  
6.  Vyberte poslední odstavce.  
  
7.  V **přidat ovládací prvky** klikněte na možnost **přidat ovládací prvek Text ve formátu RTF**.  
  
     Ovládací prvek text ve formátu RTF obsahu se přidá na poslední odstavce.  
  
8.  Uložte dokument.  
  
     Tlačítko se odebere z dokumentu.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o ovládacích prvcích v doplňcích VSTO z těchto témat:  
  
-   Vzorku, který ukazuje, jak přidávat mnoho dalších typů ovládacích prvků do dokumentu za běhu a znovu vytvořte ovládacích prvků, když znovu otevřete dokument, naleznete v aplikaci Word Add-In dynamické ovládací prvky Sample v [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
-   Návod, které ukazuje, jak k přidávání ovládacích prvků na list pomocí doplňku VSTO pro Excel najdete v tématu [návod: Přidání ovládacích prvků na list za běhu VSTO doplňku projektu](../vsto/walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project.md).  
  
## <a name="see-also"></a>Viz také  
 [Řešení aplikace Word](../vsto/word-solutions.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md)   
 [Postupy: Přidání ovládacích prvků do dokumentů Office Windows Forms](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Rozšíření wordových dokumentů a excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)  
  
  