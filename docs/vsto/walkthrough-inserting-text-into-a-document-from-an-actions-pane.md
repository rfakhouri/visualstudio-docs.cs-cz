---
title: "Návod: Vložení textu do dokumentu z podokna akcí | Microsoft Docs"
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
- smart documents [Office development in Visual Studio], creating in Word
- smart documents [Office development in Visual Studio], adding controls
- actions panes [Office development in Visual Studio], creating in Word
- actions panes [Office development in Visual Studio], adding controls
ms.assetid: fd14c896-5737-4a20-94f7-6064b67112c5
caps.latest.revision: "70"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5ca062823968153d7c8979cb13c0e3d403237be1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-inserting-text-into-a-document-from-an-actions-pane"></a>Návod: Vložení textu do dokumentu z podokna akcí
  Tento návod ukazuje, jak vytvořit podokna akcí v dokumentu aplikace Microsoft Office Word. V podokně Akce obsahuje dvou ovládacích prvků, které shromažďovat vstup a pak odeslat text v dokumentu.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Návrh rozhraní pomocí Windows Forms – ovládací prvky v podokně ovládacího prvku akce.  
  
-   Když se otevře aplikace se zobrazuje v podokně Akce.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
 Prvním krokem je vytvoření projektu dokument aplikace Word.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu dokument aplikace Word s názvem **Moje základní podokna akce**. V průvodci vyberte **vytvoříte nový textový dokument**. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nový dokument aplikace Word v návrháři a přidá **Moje základní podokna akce** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-text-and-bookmarks-to-the-document"></a>Přidávání textu a záložky do dokumentu  
 V podokně akce odešle textu záložek v dokumentu. K návrhu dokumentu, zadejte text pro vytvoření základní formulář.  
  
#### <a name="to-add-text-to-your-document"></a>Chcete-li přidat text do dokumentu  
  
1.  Zadejte následující text do dokumentu aplikace Word:  
  
     **21. března 2008**  
  
     **Jméno**  
  
     **Adresa**  
  
     **Toto je příklad podokna základní akce v aplikaci Word.**  
  
 Můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku do dokumentu přetažením z **sada nástrojů** v sadě Visual Studio nebo pomocí **záložku** dialogové okno v aplikaci Word.  
  
#### <a name="to-add-a-bookmark-control-to-your-document"></a>Přidání ovládacího prvku záložek do dokumentu  
  
1.  Z **ovládací prvky aplikace Word** kartě **sada nástrojů**, přetáhněte ji <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku do dokumentu.  
  
     **Přidání ovládacího prvku záložek** zobrazí se dialogové okno.  
  
2.  Vyberte slovo **název**, bez vyberete značku odstavce a klikněte na tlačítko **OK**.  
  
    > [!NOTE]  
    >  Značku odstavce by měla být mimo záložky. Pokud značek odstavů nejsou viditelné v dokumentu, klikněte na tlačítko **nástroje** nabídky, přejděte na příkaz **nástroje sady Microsoft Office Word** a pak klikněte na **možnosti**. Klikněte na tlačítko **zobrazení** a vyberte **vců** zaškrtávací políčko **značky formátování** části **možnosti** dialogové okno.  
  
3.  V **vlastnosti** změňte **název** vlastnost **Bookmark1** k **showName**.  
  
4.  Vyberte slovo **adresu**, aniž byste vybrali značku odstavce.  
  
5.  Na **vložit** karty na pásu karet v **odkazy** klikněte na možnost **záložku**.  
  
6.  V **záložku** dialogové okno, typ **showAddress** v **název záložky** pole a klikněte na tlačítko **přidat**.  
  
## <a name="adding-controls-to-the-actions-pane"></a>Přidání ovládacích prvků do podokna akce  
 K návrhu rozhraní podokna akce, do projektu přidejte prvek podokna akce a poté přidejte ovládací prvky Windows Forms do ovládacího prvku podokno akcí.  
  
#### <a name="to-add-an-actions-pane-control"></a>Přidání ovládacího prvku podokno akcí  
  
1.  Vyberte **Moje základní podokna akce** projektu v **Průzkumníku řešení**.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogové okno, klikněte na tlačítko **ovládací prvek podokna akce**, název ovládacího prvku **InsertTextControl,** a klikněte na tlačítko **přidat**.  
  
#### <a name="to-add-windows-form-controls-to-the-actions-pane-control"></a>Přidání ovládacích prvků ve formuláři Windows do ovládacího prvku podokno akcí  
  
1.  Pokud není zobrazená v návrháři ovládacího prvku podokno akce, klikněte dvakrát na **InsertTextControl**.  
  
2.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte ji **popisek** ovládacího prvku do ovládacího prvku podokno akce.  
  
3.  Změna **Text** vlastnosti do ovládacího prvku popisek **název**.  
  
4.  Přidat **Textbox** řízení do ovládacího prvku podokno akcí a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**getName –**|  
    |**Velikost**|**130, 20**|  
  
5.  Přidejte druhý **popisek** řízení do ovládacího prvku podokno akcí a změnit **Text** vlastnost **adresu**.  
  
6.  Přidejte druhý **Textbox** řízení do ovládacího prvku podokno akcí a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**getaddress –**|  
    |**Přijímá vrátit**|**Hodnota TRUE**|  
    |**Víceřádkového výrazu**|**Hodnota TRUE**|  
    |**Velikost**|**130, 40**|  
  
7.  Přidat **tlačítko** řízení do ovládacího prvku podokno akcí a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**addText**|  
    |**Text**|**Vložení**|  
  
## <a name="adding-code-to-insert-text-into-the-document"></a>Přidání kódu vložení textu do dokumentu  
 V podokně Akce napsat kód, který se vloží text ze do textových polí do příslušné <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky v dokumentu. Můžete použít `Globals` třída pro přístup k ovládacím prvkům v dokumentu z ovládacích prvků v podokně Akce. Další informace najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
#### <a name="to-insert-text-from-the-actions-pane-in-a-bookmark-in-the-document"></a>Chcete-li vložit text z podokna akcí v záložky v dokumentu  
  
1.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužnou rutinu události **addText** tlačítko.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#8](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/InsertTextControl.cs#8)]
     [!code-vb[Trin_VstcoreActionsPaneWord#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/InsertTextControl.vb#8)]  
  
2.  V jazyce C# je nutné přidat obslužné rutiny události pro klikněte na tlačítko. Tento kód můžete umístit `InsertTextControl` konstruktor po volání `IntializeComponent`. Informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#9](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/InsertTextControl.cs#9)]  
  
## <a name="adding-code-to-show-the-actions-pane"></a>Přidání kódu zobrazit v podokně Akce  
 Pokud chcete zobrazit v podokně Akce, přidejte do ovládacího prvku kolekce ovládací prvek, který jste vytvořili.  
  
#### <a name="to-show-the-actions-pane"></a>Chcete-li zobrazit v podokně Akce  
  
1.  Vytvořit novou instanci ovládacího prvku podokno akcí `ThisDocument` třídy.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#10](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#10)]
     [!code-vb[Trin_VstcoreActionsPaneWord#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#10)]  
  
2.  Přidejte následující kód, který <xref:Microsoft.Office.Tools.Word.Document.Startup> obslužné rutiny události z `ThisDocument`.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#11](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#11)]
     [!code-vb[Trin_VstcoreActionsPaneWord#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#11)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Otestujte svůj dokument k ověření, že při otevření dokumentu a jestli zadali text do textových polí je vložen do záložky při kliknutí na tlačítko se otevře v podokně Akce.  
  
#### <a name="to-test-your-document"></a>K testování dokumentu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Potvrďte, že je zobrazen v podokně Akce.  
  
3.  Zadejte název a adresu do textových polí v podokně Akce a klikněte na **vložit**.  
  
## <a name="next-steps"></a>Další kroky  
 Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Vytváření podokna akcí v aplikaci Excel. Další informace najdete v tématu [postupy: Přidání podokna akcí do sešitů aplikace Excel](http://msdn.microsoft.com/en-us/62abfce6-e44f-419d-85d8-26bf59f33872).  
  
-   Vazba dat s ovládacími prvky v podokně akcí aplikace. Další informace najdete v tématu [návod: vytvoření vazby dat s ovládacími prvky v podokně akcí aplikace Word](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Postupy: Přidání podokna akcí do sešitů aplikace Excel](http://msdn.microsoft.com/en-us/62abfce6-e44f-419d-85d8-26bf59f33872)   
 [Postupy: Správa rozložení ovládacích prvků v podoknech akcí](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [BOOKMARK – ovládací prvek](../vsto/bookmark-control.md)  
  
  