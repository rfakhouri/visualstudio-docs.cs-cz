---
title: 'Návod: Svázání dat s ovládacími prvky v podokně akcí aplikace Word'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], data binding
- actions panes [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], smart documents
- data binding [Office development in Visual Studio], actions panes
- actions panes [Office development in Visual Studio], binding controls
- smart documents [Office development in Visual Studio], data binding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e4202b14fce4c914737989e4a408cd74040c4d0a
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845103"
---
# <a name="walkthrough-bind-data-to-controls-on-a-word-actions-pane"></a>Návod: Svázání dat s ovládacími prvky v podokně akcí aplikace Word
  Tento návod ukazuje vazba dat s ovládacími prvky v podokně akcí aplikace Word. Ovládací prvky ukazují hlavní a podrobný vztah mezi tabulkami v databázi systému SQL Server.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Podokna akcí vytvoření s ovládacími prvky Windows Forms, které jsou vázané na data.  
  
-   Pomocí vztahu seznam podrobnosti k zobrazení dat v ovládacích prvcích.  
  
-   Zobrazte v podokně Akce po otevření aplikace.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
-   Přístup na server s ukázková databáze Northwind SQL Server.  
  
-   Oprávnění ke čtení z a zapisovat do databáze SQL serveru.  
  
## <a name="create-the-project"></a>Vytvoření projektu  
 Prvním krokem je vytvoření projektu dokument aplikace Word.  
  
### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu dokument aplikace Word s názvem **Moje podokně akcí aplikace Word**. V průvodci vyberte **vytvoříte nový textový dokument**.  
  
     Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nový dokument aplikace Word v návrháři a přidá **Moje podokně akcí aplikace Word** projektu do **Průzkumníku řešení**.  
  
## <a name="add-controls-to-the-actions-pane"></a>Přidání ovládacích prvků do podokna akce  
 V tomto návodu musíte prvek podokna akce, který obsahuje ovládací prvky Windows Forms vázané na data. Přidání zdroje dat do projektu a poté přetáhněte ovládací prvky z **zdroje dat** okna pro ovládací prvek podokna akce.  
  
### <a name="to-add-an-actions-pane-control"></a>Přidání ovládacího prvku podokno akcí  
  
1.  Vyberte **Moje podokně akcí aplikace Word** projektu v **Průzkumníku řešení**.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogové okno, vyberte **ovládací prvek podokna akce**, pojmenujte ji **ActionsControl**a potom klikněte na **přidat**.  
  
### <a name="to-add-a-data-source-to-the-project"></a>Chcete-li přidat zdroje dat do projektu  
  
1.  Pokud **zdroje dat** okno není viditelný, zobrazit, na řádku nabídky, výběr **zobrazení** > **ostatní okna**  >   **Zdroje dat**.  
  
    > [!NOTE]  
    >  Pokud **zobrazit zdroje dat** není k dispozici, klikněte na dokument aplikace Word a znovu zkontrolujte.  
  
2.  Klikněte na tlačítko **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
3.  Vyberte **databáze** a pak klikněte na **Další**.  
  
4.  Vyberte datové připojení k systému SQL Server ukázková databáze Northwind, nebo přidejte nové připojení pomocí **nové připojení** tlačítko.  
  
5.  Klikněte na tlačítko **Další**.  
  
6.  Zrušte možnost uložit připojení, pokud je zaškrtnuto a pak klikněte na **Další**.  
  
7.  Rozbalte položku **tabulky** uzlu **databázové objekty** okno.  
  
8.  Zaškrtněte políčko vedle položky **Dodavatelé** a **produkty** tabulky.  
  
9. Klikněte na tlačítko **Dokončit**.  
  
 Průvodce přidá **Dodavatelé** tabulky a **produkty** a **zdroje dat** okno. Také přidá typové datové sady do projektu, který se zobrazí na **Průzkumníku řešení**.  
  
### <a name="to-add-data-bound-windows-forms-controls-to-an-actions-pane-control"></a>K přidávání ovládacích prvků Windows Forms vázané na data na ovládací prvek podokna akce  
  
1.  V **zdroje dat** okno, rozbalte **Dodavatelé** tabulky.  
  
2.  Klikněte na šipku rozevíracího seznamu na **název společnosti** uzel a vyberte možnost **ComboBox**.  
  
3.  Přetáhněte **#companyname** z **zdroje dat** okna pro ovládací prvek podokna akce.  
  
     A <xref:System.Windows.Forms.ComboBox> ovládací prvek je vytvořen na ovládací prvek podokna akce. Ve stejnou dobu <xref:System.Windows.Forms.BindingSource> s názvem `SuppliersBindingSource`, adaptérem tabulky a <xref:System.Data.DataSet> jsou přidány do projektu na hlavním panelu součásti.  
  
4.  Vyberte `SuppliersBindingNavigator` v **součást** panelu a stiskněte klávesu **odstranit**. Nebudete používat `SuppliersBindingNavigator` v tomto návodu.  
  
    > [!NOTE]  
    >  Odstraňování `SuppliersBindingNavigator` neodebere všechny kód, který byl vygenerován pro ni. Tento kód můžete odebrat.  
  
5.  Přesunout pole se seznamem tak, aby se v rámci popisku a změny **velikost** vlastnost **171, 21**.  
  
6.  V **zdroje dat** okno, rozbalte **produkty** tabulka, která je podřízená **Dodavatelé** tabulky.  
  
7.  Klikněte na šipku rozevíracího seznamu na **ProductName** uzel a vyberte možnost **ListBox**.  
  
8.  Přetáhněte **ProductName** do ovládacího prvku podokno akcí.  
  
     A <xref:System.Windows.Forms.ListBox> ovládací prvek je vytvořen na ovládací prvek podokna akce. Ve stejnou dobu <xref:System.Windows.Forms.BindingSource> s názvem `ProductBindingSource` a adaptér tabulky jsou přidány do projektu na hlavním panelu součásti.  
  
9. Přesunout pole se seznamem tak, aby se v rámci popisku a změny **velikost** vlastnost **171,95**.  
  
10. Přetáhněte <xref:System.Windows.Forms.Button> z **sada nástrojů** do podokna akce řízení a umístěte jej pod pole se seznamem.  
  
11. Klikněte pravým tlačítkem myši <xref:System.Windows.Forms.Button>, klikněte na tlačítko **vlastnosti** v místní nabídce a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**Vložení**|  
    |**Text**|**Vložení**|  
  
12. Změnit velikost uživatelského ovládacího prvku podle ovládacích prvků.  
  
## <a name="set-up-the-data-source"></a>Nastavení zdroje dat  
 Nastavení zdroje dat, přidejte kód, který <xref:System.Windows.Forms.UserControl.Load> události ovládacího prvku podokno akce k vyplnění ovládacího prvku s daty z <xref:System.Data.DataTable>a nastavte <xref:System.Windows.Forms.Binding.DataSource%2A> a <xref:System.Windows.Forms.BindingSource.DataMember%2A> vlastnosti pro každý ovládací prvek.  
  
### <a name="to-load-the-control-with-data"></a>Načtení ovládacího prvku s daty  
  
1.  V <xref:System.Windows.Forms.UserControl.Load> obslužnou rutinu události `ActionsControl` třídy, přidejte následující kód.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#1)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#1)]  
  
2.  V jazyce C#, je nutné připojit obslužná rutina události <xref:System.Windows.Forms.UserControl.Load> událostí. Tento kód můžete umístit `ActionsControl` konstruktor po volání `InitializeComponent`. Další informace o tom, jak vytváření obslužných rutin událostí najdete v tématu [postupy: vytváření obslužných rutin událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#33](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#33)]  
  
### <a name="to-set-data-binding-properties-of-the-controls"></a>Chcete-li nastavit vlastnosti datové vazby ovládacích prvků  
  
1.  Vyberte `CompanyNameComboBox` ovládacího prvku.  
  
2.  V **vlastnosti** okně klikněte na tlačítko napravo od **DataSource** vlastnost a vyberte **suppliersBindingSource**.  
  
3.  Klikněte na tlačítko napravo **DisplayMember** vlastnost a vyberte **#companyname**.  
  
4.  Rozbalte **datové vazby** vlastnosti, klikněte na tlačítko napravo od **Text** vlastnost a vyberte **žádné**.  
  
5.  Vyberte `ProductNameListBox` ovládacího prvku.  
  
6.  V **vlastnosti** okně klikněte na tlačítko napravo od **DataSource** vlastnost a vyberte **productsBindingSource**.  
  
7.  Klikněte na tlačítko napravo **DisplayMember** vlastnost a vyberte **ProductName**.  
  
8.  Rozbalte **datové vazby** vlastnosti, klikněte na tlačítko napravo od **SelectedValue** vlastnost a vyberte **žádné**.  
  
## <a name="add-a-method-to-insert-data-into-a-table"></a>Přidejte metodu k vložení dat do tabulky  
 Dalším krokem je ke čtení dat z vázané ovládací prvky a vyplnění tabulky v dokumentu aplikace Word. Nejprve vytvořit proceduru k formátování záhlaví tabulky a poté přidejte `AddData` metoda a vytvořte a naformátujte tabulky aplikace Word.  
  
### <a name="to-format-the-table-headings"></a>K formátování záhlaví tabulky  
  
1.  V `ActionsControl` třídy, vytvoření metody k formátování záhlaví tabulky.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#2)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#2)]  
  
### <a name="to-create-the-table"></a>Chcete-li vytvořit v tabulce  
  
1.  V `ActionsControl` třídy, napíše metoda, která vytvoří tabulku, pokud jeden není již existují a přidat do tabulky data z podokna akcí.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#3)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#3](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#3)]  
  
### <a name="to-insert-text-into-a-word-table"></a>Vložení textu do tabulky aplikace Word  
  
1.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužnou rutinu události **vložit** tlačítko.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#4)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#4](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#4)]  
  
2.  V jazyce C#, musíte vytvořit obslužnou rutinu události pro <xref:System.Windows.Forms.Control.Click> události tlačítka.  Tento kód můžete umístit <xref:System.Windows.Forms.UserControl.Load> obslužnou rutinu události `ActionsControl` – třída.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#5](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#5)]  
  
## <a name="show-the-actions-pane"></a>Zobrazit v podokně Akce  
 V podokně Akce se zobrazí po ovládací prvky jsou přidány do ní.  
  
### <a name="to-show-the-actions-pane"></a>Chcete-li zobrazit v podokně Akce  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **ThisDocument.vb** nebo **ThisDocument.cs**a potom klikněte na **kód zobrazení** v místní nabídce.  
  
2.  Vytvořit novou instanci ovládacího prvku v horní části `ThisDocument` třídy tak, aby vypadal jako v následujícím příkladu.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#6](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#6)]
     [!code-vb[Trin_VstcoreActionsPaneWord#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#6)]  
  
3.  Přidejte kód, který <xref:Microsoft.Office.Tools.Word.Document.Startup> obslužné rutiny události z `ThisDocument` tak, aby vypadal jako v následujícím příkladu.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#7)]
     [!code-vb[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#7)]  
  
## <a name="test-the-application"></a>Testování aplikace  
 Nyní můžete otestovat dokument k ověření, že při otevření dokumentu se zobrazí v podokně Akce. Testování pro vztahu seznam podrobnosti v ovládacích prvcích v podokně Akce a ujistěte se, že je v slovo zadána data tabulky, kdy **vložit** po kliknutí na tlačítko.  
  
### <a name="to-test-your-document"></a>K testování dokumentu  
  
1.  Stiskněte klávesu **F5** ke spuštění projektu.  
  
2.  Potvrďte, že je zobrazen v podokně Akce.  
  
3.  Vyberte společnosti do pole se seznamem a ověřte, že položky v **produkty** seznam změn pole.  
  
4.  Vyberte produkt, klikněte na **vložit** v podokně Akce a ověřte, zda jsou podrobnosti o produktu přidán do tabulky v aplikaci Word.  
  
5.  Vložte další produkty od různých společností.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základní informace o vytvoření vazby dat s ovládacími prvky v podokně akcí aplikace Word. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Vazba dat s ovládacími prvky v aplikaci Excel. Další informace najdete v tématu [návod: svázání dat s ovládacími prvky v podokně akcí aplikace Excel](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md).  
  
-   Nasazení projektu. Další informace najdete v tématu [nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
## <a name="see-also"></a>Viz také:  
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  