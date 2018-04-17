---
title: 'Návod: Vytvoření šablony s použitím ovládacích prvků obsahu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- building blocks [Office development in Visual Studio]
- Word [Office development in Visual Studio], creating documents
- content controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8c7f5026d4cbe8b7c38b8163ce00d893e1e406f2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-a-template-by-using-content-controls"></a>Návod: Vytvoření šablony s použitím ovládacích prvků obsahu
  Tento návod ukazuje, jak vytvořit přizpůsobení na úrovni dokumentu používá ovládací prvky obsahu k vytváření strukturovaných a opakovaně použitelný obsah do šablony aplikace Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word umožňuje vytvořit kolekci opakovaně použitelné dokumentu části s názvem *stavební bloky*. Tento návod ukazuje postup vytvoření dvou tabulek jako stavební bloky. Každá tabulka obsahuje několik obsahu ovládacích prvků, které mohou být uloženy různé typy obsahu, například prostý text nebo kalendářní data. Jedna z tabulek obsahuje informace o zaměstnanec a dalších tabulka obsahuje názory zákazníků.  
  
 Po vytvoření dokumentu ze šablony, můžete přidat buď tabulek v dokumentu s použitím několik <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> objekty, které budou zobrazovat dostupné stavebních bloků v šabloně.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytváření tabulek, které obsahují obsah aplikace Word řídí šablony v době návrhu.  
  
-   Prvek obsahu pole se seznamem a obsahu ovládacího prvku rozevíracího seznamu naplnění prostřednictvím kódu programu.  
  
-   Brání uživatelům v úpravy zadané tabulky.  
  
-   Přidání tabulky do kolekce stavebním blokem šablony.  
  
-   Vytvoření ovládacího prvku obsahu, který zobrazuje dostupné stavebních bloků v šabloně.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Aplikace Microsoft Word.  
  
## <a name="creating-a-new-word-template-project"></a>Vytvoření nového projektu šablony aplikace Word  
 Vytvoření šablony aplikace Word tak, aby uživatelé mohou snadno vytvářet své vlastní kopie.  
  
#### <a name="to-create-a-new-word-template-project"></a>K vytvoření nového projektu šablony aplikace Word  
  
1.  Vytvoření projektu šablony aplikace Word s názvem **MyBuildingBlockTemplate**. V průvodci vytvořte nový dokument v řešení. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře se nové šablony aplikace Word v návrháři a přidá **MyBuildingBlockTemplate** projektu do **Průzkumníku řešení**.  
  
## <a name="creating-the-employee-table"></a>Vytvoření tabulky zaměstnanců  
 Vytvořte tabulku, která obsahuje čtyři různé typy ovládacích prvků obsahu kde uživatele můžete zadat informace o zaměstnanec.  
  
#### <a name="to-create-the-employee-table"></a>K vytvoření tabulky zaměstnanců  
  
1.  V šabloně aplikace Word, jejímž hostitelem je [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer a na pásu karet klikněte na tlačítko **vložit** kartě.  
  
2.  V **tabulky** klikněte na možnost **tabulky**a vložte tabulku se sloupci 2 a 4 řádky.  
  
3.  Zadejte text z prvního sloupce tak, aby je podobná následující sloupce:  
  
    ||  
    |-|  
    |**Jméno zaměstnance**|  
    |**Datum přijetí**|  
    |**Název**|  
    |**Obrázek**|  
  
4.  Klikněte na první buňky v druhém sloupci (vedle **jméno zaměstnance**).  
  
5.  Na pásu karet klikněte na **vývojáře** kartě.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný, musíte ji nejdříve zobrazit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
6.  V **ovládací prvky** klikněte na možnost **Text** tlačítko ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") přidat <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>na první buňky.  
  
7.  Klikněte na druhé buňky v druhém sloupci (vedle **datum přijetí**).  
  
8.  V **ovládací prvky** klikněte na možnost **výběr data** tlačítko ![DatePickerContentControl](../vsto/media/datepicker.gif "DatePickerContentControl") přidat <xref:Microsoft.Office.Tools.Word.DatePickerContentControl> do druhé buňky.  
  
9. Klikněte na třetí buňky v druhém sloupci (vedle **název**).  
  
10. V **ovládací prvky** klikněte na možnost **– pole se seznamem** tlačítko ![ComboBoxContentControl](../vsto/media/combobox.gif "ComboBoxContentControl") přidat <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>do třetí buňky.  
  
11. Klikněte na poslední buňky v druhém sloupci (vedle **obrázek**).  
  
12. V **ovládací prvky** klikněte na možnost **obsahu ovládacího prvku obrázek** tlačítko ![PictureContentControl](../vsto/media/pictcontentcontrol.gif "PictureContentControl") přidat <xref:Microsoft.Office.Tools.Word.PictureContentControl> na poslední buňku.  
  
## <a name="creating-the-customer-feedback-table"></a>Vytvoření tabulky zpětné vazby zákazníka  
 Vytvořte tabulku, která obsahuje tři různé typy obsahu ovládacích prvků, kde může uživatel zadat údaje zpětné vazby zákazníka.  
  
#### <a name="to-create-the-customer-feedback-table"></a>K vytvoření tabulky zpětné vazby zákazníka  
  
1.  V šabloně aplikace Word klikněte v řádku po tabulky zaměstnanců, které jste přidali dříve a stiskněte klávesu ENTER, chcete-li přidat nový odstavec.  
  
2.  Na pásu karet klikněte na **vložit** kartě.  
  
3.  V **tabulky** klikněte na možnost **tabulky**a vložte tabulku se sloupci 2 a 3 řádky.  
  
4.  Zadejte text z prvního sloupce tak, aby je podobná následující sloupce:  
  
    ||  
    |-|  
    |**Jméno zákazníka**|  
    |**Spokojenost hodnocení**|  
    |**Komentáře**|  
  
5.  Klikněte na tlačítko v první buňky druhý sloupec (vedle **jméno zákazníka**).  
  
6.  Na pásu karet klikněte na **vývojáře** kartě.  
  
7.  V **ovládací prvky** klikněte na možnost **Text** tlačítko ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") přidat <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>na první buňky.  
  
8.  Klepněte na druhý buňku druhý sloupec (vedle **spokojenost hodnocení**).  
  
9. V **ovládací prvky** klikněte na možnost **rozevíracího seznamu** tlačítko ![DropDownListContentControl](../vsto/media/dropdownlist.gif "DropDownListContentControl") přidat <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> do druhé buňky.  
  
10. Klepněte na poslední buňku druhý sloupec (vedle **komentáře**).  
  
11. V **ovládací prvky** klikněte na možnost **formátovaného textu** tlačítko ![RichTextContentControl](../vsto/media/richtextcontrol.gif "RichTextContentControl") přidat <xref:Microsoft.Office.Tools.Word.RichTextContentControl>na poslední buňku.  
  
## <a name="populating-the-combo-box-and-drop-down-list-programmatically"></a>Vyplní se seznamem se pole a v rozevíracím seznamu prostřednictvím kódu programu  
 Ovládací prvky obsahu můžete inicializovat v době návrhu pomocí **vlastnosti** okno v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Je také možné inicializovat za běhu, která umožňuje nastavit jejich počáteční stav dynamicky. Pro účely tohoto postupu použít k naplnění položek v kódu <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> a <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> na běh tak, abyste viděli, jak fungují tyto objekty.  
  
#### <a name="to-modify-the-ui-of-the-content-controls-programmatically"></a>Chcete-li upravit uživatelské ovládací prvky obsahu prostřednictvím kódu programu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **ThisDocument.cs** nebo **ThisDocument.vb**a potom klikněte na **kód zobrazení**.  
  
2.  Přidejte následující kód, který `ThisDocument` třídy. Tento kód deklaruje několik objektů, které budete používat později v tomto návodu.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#1](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#1)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#1](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#1)]  
  
3.  Přidejte následující kód, který `ThisDocument_Startup` metodu `ThisDocument` třídy. Tento kód přidá položky k <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> a <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> v tabulkách a nastaví zástupný text, který se zobrazí v každé z těchto ovládacích prvků, než se uživatel upravuje je.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#2](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#2)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#2](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#2)]  
  
## <a name="preventing-users-from-editing-the-employee-table"></a>Brání uživatelům v úpravy tabulky zaměstnanců  
 Použití <xref:Microsoft.Office.Tools.Word.GroupContentControl> objektu, jestli deklaruje starší k ochraně tabulky zaměstnanců. Po nastavení ochrany v tabulce, uživatelé stále mohou upravovat ovládací prvky obsahu v tabulce. Nelze však upravit text ve sloupci první nebo úpravu tabulky jinými způsoby, například přidávání nebo odstraňování řádků a sloupců. Další informace o tom, jak používat <xref:Microsoft.Office.Tools.Word.GroupContentControl> chránit část dokumentu, najdete v části [ovládací prvky obsahu](../vsto/content-controls.md).  
  
#### <a name="to-prevent-users-from-editing-the-employee-table"></a>Chcete-li uživatelům zabránit v úpravách tabulky zaměstnanců  
  
1.  Přidejte následující kód, který `ThisDocument_Startup` metodu `ThisDocument` třída po kód, který jste přidali v předchozím kroku. Tento kód zabraňuje uživatelům v úpravy tabulky zaměstnanců vložením tabulka uvnitř <xref:Microsoft.Office.Tools.Word.GroupContentControl> objekt, který jste předtím deklarován.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#3](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#3)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#3](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#3)]  
  
## <a name="adding-the-tables-to-the-building-block-collection"></a>Přidání tabulky do kolekce stavební blok.  
 Přidání tabulky do kolekce stavební bloky dokumentu v šabloně tak, aby uživatelé můžete vložit do dokumentu tabulky, které jste vytvořili. Další informace o stavební bloky dokumentu najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md).  
  
#### <a name="to-add-the-tables-to-the-building-blocks-in-the-template"></a>Přidání tabulky do stavebních bloků v šabloně  
  
1.  Přidejte následující kód, který `ThisDocument_Startup` metodu `ThisDocument` třída po kód, který jste přidali v předchozím kroku. Tento kód přidá nové stavební bloky, které obsahují tabulky do kolekce Microsoft.Office.Interop.Word.BuildingBlockEntries, který obsahuje všechny opakovaně použitelné stavebních bloků v šabloně. Nové stavební bloky, které jsou definovány v novou kategorii s názvem **zaměstnance a informace o zákazníkovi** a jsou přiřazeny stavební blok typem Microsoft.Office.Interop.Word.WdBuildingBlockTypes.wdTypeCustom1.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#4](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#4)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#4](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#4)]  
  
2.  Přidejte následující kód, který `ThisDocument_Startup` metodu `ThisDocument` třída po kód, který jste přidali v předchozím kroku. Tento kód odstraní tabulky ze šablony. V tabulkách již nejsou potřebné, protože jste je přidali do Galerie opakovaně použitelné stavebních bloků v šabloně. Dokument kód nejprve umístí do režimu návrhu, aby tabulky chráněné zaměstnanců může odstranit.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#5](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#5)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#5](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#5)]  
  
## <a name="creating-a-content-control-that-displays-the-building-blocks"></a>Vytvoření ovládacího prvku obsahu, který zobrazí stavební bloky  
 Vytvoření ovládacího prvku obsahu, který poskytuje přístup k stavební bloky (tedy tabulky), které jste předtím vytvořili. Uživatelé kliknutím na tento ovládací prvek pro přidání tabulky do dokumentu.  
  
#### <a name="to-create-a-content-control-that-displays-the-building-blocks"></a>Vytvoření ovládacího prvku obsahu, která zobrazí stavební bloky  
  
1.  Přidejte následující kód, který `ThisDocument_Startup` metodu `ThisDocument` třída po kód, který jste přidali v předchozím kroku. Tento kód inicializuje <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> objekt, který jste předtím deklarován. <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> Zobrazí všechny stavební bloky, které jsou definovány v kategorii **zaměstnance a informace o zákazníkovi** a které mají typ stavebním blokem Microsoft.Office.Interop.Word.WdBuildingBlockTypes.wdTypeCustom1.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#6](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#6)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#6](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#6)]  
  
## <a name="testing-the-project"></a>Testování projektu  
 Ovládací prvky galerie stavebních bloků v dokumentu vložit do tabulky zaměstnanců nebo v tabulce zpětné vazby zákazníka mohou uživatelé kliknout. Uživatelé mohou zadejte nebo vyberte odpovědi v ovládacích prvků obsahu v obou tabulkách. Mohou uživatelé změnit dalších částí tabulky zpětné vazby zákazníků, ale jejich by neměl být možné měnit dalších částí tabulky zaměstnanců.  
  
#### <a name="to-test-the-employee-table"></a>K testování tabulky zaměstnanců  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Klikněte na tlačítko **zvolte první stavební blok** zobrazíte první prvek obsahu galerie stavebních bloků.  
  
3.  Klikněte na šipku rozevíracího seznamu vedle položky **vlastní galerie 1** záhlaví v ovládacím prvku a vyberte **tabulky zaměstnanců**.  
  
4.  Klikněte na buňku napravo **jméno zaměstnance** buňky a zadejte název.  
  
     Ověřte, že můžete přidat pouze text na tuto buňku. <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> Umožňuje uživatelům přidat pouze text, není jiné typy obsahu, jako je například obrázky nebo tabulky.  
  
5.  Klikněte na buňku napravo **datum přijetí** buňky a vyberte datum při výběru data.  
  
6.  Klikněte na buňku napravo **název** buňky a vyberte jednu z úlohy názvy v seznamu.  
  
     Volitelně zadejte název úlohy produktu, který se nenachází v seznamu. To je možné, protože <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> umožňuje uživatelům vybrat ze seznamu položek nebo zadejte vlastní položky.  
  
7.  Klikněte na ikonu v buňce napravo **obrázek** buňky a vyhledat obrázek, můžete ho zobrazit.  
  
8.  Zkuste přidat řádky nebo sloupce do tabulky a pokuste se odstranit řádky a sloupce z tabulky. Ověřte, že nelze změnit v tabulce. <xref:Microsoft.Office.Tools.Word.GroupContentControl> Nemůžete provádět žádné změny.  
  
#### <a name="to-test-the-customer-feedback-table"></a>K testování v tabulce zpětné vazby zákazníka  
  
1.  Klikněte na tlačítko **vyberte druhý stavební blok** zobrazíte prvku druhý stavebním blokem galerie.  
  
2.  Klikněte na šipku rozevíracího seznamu vedle položky **vlastní galerie 1** záhlaví v ovládacím prvku a vyberte **tabulky Zákazník**.  
  
3.  Klikněte na buňku napravo **jméno zákazníka** buňky a zadejte název.  
  
4.  Klikněte na buňku napravo **spokojenost hodnocení** buňky a vyberte jednu z dostupných možností.  
  
     Ověřte, že nelze zadat vlastní položku. <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> Umožňuje pouze vybrat ze seznamu položek.  
  
5.  Klikněte na buňku napravo **komentáře** buňky a zadejte některé komentáře.  
  
     Volitelně lze přidáte k některému obsahu než text, například obrázky nebo vložené tabulky. To je možné, protože <xref:Microsoft.Office.Tools.Word.RichTextContentControl> umožňuje uživatelům přidávat obsah než text.  
  
6.  Ověřte, že přidáte řádky nebo sloupce do tabulky a, můžete odstranit řádky a sloupce z tabulky. To je možné, protože nebyly chráněných tabulce umístěním <xref:Microsoft.Office.Tools.Word.GroupContentControl>.  
  
7.  Zavřete šablonu.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak používat ovládací prvky obsahu z tohoto tématu:  
  
-   Vytvoření vazby ovládacích prvků obsahu s částí XML, také s názvem vlastní části XML, které jsou vloženy do dokumentu. Další informace najdete v tématu [návod: vytvoření vazby ovládacích prvků obsahu s vlastní části XML](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
## <a name="see-also"></a>Viz také  
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Ovládací prvky obsahu](../vsto/content-controls.md)   
 [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Postupy: ochrana částí dokumentů pomocí ovládacích prvků obsahu](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  