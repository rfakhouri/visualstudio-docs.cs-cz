---
title: 'Návod: Vytváření místních nabídek pro záložky | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context menus, Word
- Bookmark control, events
- shortcut menus, Word
- menus, creating in Office applications
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6d54d23330c6d5fab836f168a291b15b90379117
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-shortcut-menus-for-bookmarks"></a>Návod: Vytváření místních nabídek pro záložky
  Tento návod ukazuje, jak vytvořit místní nabídky pro <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacích prvků v přizpůsobení na úrovni dokumentu ve Wordu. Když uživatel klikne pravým tlačítkem myši textu v záložku, místní nabídky se zobrazí a poskytuje možnosti uživatele pro formátování textu.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   [Vytvoření projektu](#BKMK_CreateProject).  
  
-   [Přidávání textu a záložky v dokumentu](#BKMK_addtextandbookmarks).  
  
-   [Přidání příkazů na místní nabídku](#BKMK_AddCmndsShortMenu).  
  
-   [Formátování textu v záložkách](#BKMK_formattextbkmk).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] Nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
##  <a name="BKMK_CreateProject"></a> Vytvoření projektu  
 Prvním krokem je vytvoření projektu dokumentu aplikace Word v sadě Visual Studio.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
-   Vytvoření projektu dokumentu aplikace Word, který má název **Moje záložku místní nabídky**. V průvodci vyberte **vytvoříte nový textový dokument**. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nový dokument aplikace Word v návrháři a přidá **Moje záložku místní nabídky** projektu do **Průzkumníku řešení**.  
  
##  <a name="BKMK_addtextandbookmarks"></a> Přidávání textu a záložky do dokumentu  
 Přidat do dokumentu nějaký text a pak přidejte dva překrývající se záložky.  
  
#### <a name="to-add-text-to-your-document"></a>Chcete-li přidat text do dokumentu  
  
-   V dokumentu, který se zobrazí v Návrháři projektu zadejte následující text.  
  
     **Toto je příklad vytvoření místní nabídky, když kliknete pravým tlačítkem na text v záložky.**  
  
#### <a name="to-add-a-bookmark-control-to-your-document"></a>Přidání ovládacího prvku záložek do dokumentu  
  
1.  V **sada nástrojů**, z **ovládací prvky aplikace Word** kartě, přetáhněte ji <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku do dokumentu.  
  
     **Přidání ovládacího prvku záložek** zobrazí se dialogové okno.  
  
2.  Vyberte slova "Vytvoření místní nabídky, když kliknete pravým tlačítkem na text" a potom klikněte na **OK**.  
  
     `bookmark1` se přidá do dokumentu.  
  
3.  Přidejte další <xref:Microsoft.Office.Tools.Word.Bookmark> řídit k slova "klikněte pravým tlačítkem na text v záložku".  
  
     `bookmark2` se přidá do dokumentu.  
  
    > [!NOTE]  
    >  Slova "klikněte pravým tlačítkem na text" jsou v obou `bookmark1` a `bookmark2`.  
  
 Když přidáte záložku na dokument v době návrhu <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek je vytvořen. Můžete ovládat několik událostí záložky. Můžete napsat kód ve <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick> událostí záložky tak, aby při kliknutí pravým tlačítkem textu v záložku, zobrazí místní nabídka.  
  
##  <a name="BKMK_AddCmndsShortMenu"></a> Přidání příkazů na místní nabídky  
 Přidání tlačítka do místní nabídky, která se zobrazí, když kliknete pravým tlačítkem na dokument.  
  
#### <a name="to-add-commands-to-a-shortcut-menu"></a>Přidání příkazů do místní nabídky  
  
1.  Přidat **XML karet** položku do projektu. Další informace najdete v tématu [postupy: získání spuštění přizpůsobení pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
2.  V **Průzkumníku řešení**, vyberte **ThisDocument.cs** nebo **ThisDocument.vb**.  
  
3.  Na řádku nabídek zvolte **zobrazení**, **kód**.  
  
     **ThisDocument** třída soubor se otevře v editoru kódu.  
  
4.  Přidejte následující kód, který **ThisDocument** třídy. Tento kód přepíše metodu CreateRibbonExtensibilityObject a vrátí třídy XML pásu karet do aplikace Office.  
  
     [!code-csharp[Trin_Word_Document_Menus#1](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#1)]
     [!code-vb[Trin_Word_Document_Menus#1](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#1)]  
  
5.  V **Průzkumníku**, vyberte soubor XML pásu karet. Ve výchozím nastavení je soubor XML karet s názvem Ribbon1.xml.  
  
6.  Na řádku nabídek zvolte **zobrazení**, **kód**.  
  
     Soubor xml pásu karet se otevře v editoru kódu.  
  
7.  V editoru kódu nahraďte obsah souboru XML karet s následujícím kódem.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?>  
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui" onLoad="Ribbon_Load">  
      <contextMenus>  
        <contextMenu idMso="ContextMenuText">  
          <button id="BoldButton" label="Bold" onAction="ButtonClick"          
               getVisible="GetVisible" />  
          <button id="ItalicButton" label="Italic" onAction="ButtonClick"   
              getVisible="GetVisible"/>  
        </contextMenu>  
      </contextMenus>  
    </customUI>  
    ```  
  
     Tento kód přidá dvě tlačítka do místní nabídky, která se zobrazí, když kliknete pravým tlačítkem na dokument.  
  
8.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na `ThisDocument`a potom klikněte na **kód zobrazení**.  
  
9. Deklarujte následující proměnné a proměnná záložku na úrovni třídy.  
  
     [!code-csharp[Trin_Word_Document_Menus#2](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#2)]
     [!code-vb[Trin_Word_Document_Menus#2](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#2)]  
  
10. V **Průzkumníku**, vyberte soubor kódu pásu karet. Ve výchozím nastavení, má název souboru kódu pásu karet **Ribbon1.cs** nebo **Ribbon1.vb**.  
  
11. Na řádku nabídek zvolte **zobrazení**, **kód**.  
  
     Pás karet kód soubor se otevře v editoru kódu.  
  
12. V souboru kódu pásu karet přidejte následující metodu. Toto je metoda zpětného volání pro dvě tlačítka, které jste přidali do místní nabídky dokumentu. Tato metoda určuje, zda tato tlačítka se zobrazují v místní nabídce. Tlačítka tučné písmo a kurzíva zobrazí pouze v případě, že kliknete pravým tlačítkem na text v rámci záložky.  
  
     [!code-csharp[Trin_Word_Document_Menus#5](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/ribbon1.cs#5)]
     [!code-vb[Trin_Word_Document_Menus#5](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/ribbon1.vb#5)]  
  
##  <a name="BKMK_formattextbkmk"></a> Formátování textu v záložkách  
  
#### <a name="to-format-the-text-in-the-bookmark"></a>K formátování textu v záložkách  
  
1.  V souboru kódu pásu karet, přidejte `ButtonClick` obslužné rutiny události pro použití formátování na záložku.  
  
     [!code-csharp[Trin_Word_Document_Menus#6](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/ribbon1.cs#6)]
     [!code-vb[Trin_Word_Document_Menus#6](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/ribbon1.vb#6)]  
  
2.  **Průzkumník řešení**, vyberte **ThisDocument.cs** nebo **ThisDocument.vb**.  
  
3.  Na řádku nabídek zvolte **zobrazení**, **kód**.  
  
     **ThisDocument** třída soubor se otevře v editoru kódu.  
  
4.  Přidejte následující kód, který **ThisDocument** třídy.  
  
     [!code-csharp[Trin_Word_Document_Menus#3](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#3)]
     [!code-vb[Trin_Word_Document_Menus#3](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#3)]  
  
    > [!NOTE]  
    >  Musíte napsat kód pro zpracování případu, kdy záložky překrývat. Pokud ho použít nechcete, ve výchozím nastavení, bude zavolána kód pro všechny záložky ve výběru.  
  
5.  V jazyce C#, je nutné přidat obslužné rutiny události pro ovládací prvky záložku <xref:Microsoft.Office.Tools.Word.Document.Startup> událostí. Informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_Word_Document_Menus#4](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#4)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Otestujte dokumentu pro ověření, že položky nabídky tučné písmo a kurzíva se objeví v místní nabídce, když kliknete pravým tlačítkem na text v záložku a že text je ve správném formátu.  
  
#### <a name="to-test-your-document"></a>K testování dokumentu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Klikněte pravým tlačítkem na první záložku a pak klikněte na **Bold**.  
  
3.  Ověřte, že veškerý text v `bookmark1` je naformátován jako tučně.  
  
4.  Klikněte pravým tlačítkem na text, kde záložky překrývají, a potom klikněte na **Kurzíva**.  
  
5.  Ověřte, že veškerý text v `bookmark2` kurzíva, a to jenom část textu v `bookmark1` která se překrývá `bookmark2` je kurzíva.  
  
## <a name="next-steps"></a>Další kroky  
 Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Napište kód pro reakce na události hostitelské ovládací prvky v aplikaci Excel. Další informace najdete v tématu [návod: programování proti události ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md).  
  
-   Chcete-li změnit formátování v záložku použijte zaškrtávací políčko. Další informace najdete v tématu [návod: Změna dokumentu formátování pomocí ovládacích prvků CheckBox](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Viz také  
 [Návody pro práci s aplikací Word](../vsto/walkthroughs-using-word.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [BOOKMARK – ovládací prvek](../vsto/bookmark-control.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  