---
title: 'Návod: Svázání dat s ovládacími prvky v podokně akcí aplikace Excel'
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
ms.openlocfilehash: 9d450a9c52ae8558167bf4cb581ce2e36f44f4e9
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767907"
---
# <a name="walkthrough-bind-data-to-controls-on-an-excel-actions-pane"></a>Návod: Svázání dat s ovládacími prvky v podokně akcí aplikace Excel
  Tento návod ukazuje vazba dat s ovládacími prvky v podokně akcí aplikace v aplikaci Microsoft Office Excel. Ovládací prvky ukazují hlavní a podrobný vztah mezi tabulkami v databázi systému SQL Server.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Přidání ovládacích prvků na list.  
  
-   Vytvoření ovládacího prvku podokno akcí.  
  
-   Přidání ovládacích prvků Windows Forms vázané na data do ovládacího prvku podokno akcí.  
  
-   Když se otevře aplikace, zobrazuje v podokně Akce.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Přístup na server s ukázková databáze Northwind SQL Server.  
  
-   Oprávnění ke čtení z a zapisovat do databáze SQL serveru.  
  
## <a name="create-the-project"></a>Vytvoření projektu  
 Prvním krokem je vytvoření projektu sešitu aplikace Excel.  
  
### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **Moje podokně akcí aplikace Excel**. V průvodci vyberte **vytvoříte nový textový dokument**. Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **Moje podokně akcí aplikace Excel** projektu do **Průzkumníku řešení**.  
  
## <a name="add-a-new-data-source-to-the-project"></a>Přidat nový zdroj dat do projektu  
  
### <a name="to-add-a-new-data-source-to-the-project"></a>Chcete-li přidat nový zdroj dat do projektu  
  
1.  Pokud **zdroje dat** okno nejsou viditelná, zobrazit, na řádku nabídky, výběr **zobrazení** > **ostatní okna**  >   **Zdroje dat**.  
  
2.  Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
3.  Vyberte **databáze** a pak klikněte na **Další**.  
  
4.  Vyberte datové připojení k systému SQL Server ukázková databáze Northwind, nebo přidejte nové připojení pomocí **nové připojení** tlačítko.  
  
5.  Klikněte na tlačítko **Další**.  
  
6.  Zrušte možnost uložit připojení, pokud je zaškrtnuto a pak klikněte na **Další**.  
  
7.  Rozbalte položku **tabulky** uzlu **databázové objekty** okno.  
  
8.  Zaškrtněte políčko vedle položky **Dodavatelé** tabulky.  
  
9. Rozbalte **produkty** tabulky a vyberte **ProductName**, **KódDodavatele**, **QuantityPerUnit**, a **UnitPrice**.  
  
10. Klikněte na tlačítko **Dokončit**.  
  
 Průvodce přidá **Dodavatelé** tabulky a **produkty** a **zdroje dat** okno. Také přidá typové datové sady do projektu, který se zobrazí na **Průzkumníku řešení**.  
  
## <a name="add-controls-to-the-worksheet"></a>Přidání ovládacích prvků do listu  
 Dál přidejte <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení a <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku do první listu.  
  
### <a name="to-add-a-namedrange-control-and-a-listobject-control"></a>Přidání ovládacího prvku NamedRange a ovládacího prvku ListObject  
  
1.  Ověřte, zda **Moje Pane.xlsx akcí aplikace Excel** je sešit otevřít v návrháři Visual Studio s `Sheet1` zobrazí.  
  
2.  V **zdroje dat** okno, rozbalte **Dodavatelé** tabulky.  
  
3.  Klikněte na šipku rozevíracího seznamu na **název společnosti** uzel a pak klikněte na **NamedRange**.  
  
4.  Přetáhněte **název společnosti** z **zdroje dat** okna buňky **A2** v `Sheet1`.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `CompanyNameNamedRange` je vytvořen a text \<NázevSpolečnosti > se zobrazí v buňce **A2**. Ve stejnou dobu <xref:System.Windows.Forms.BindingSource> s názvem `suppliersBindingSource`, adaptérem tabulky a <xref:System.Data.DataSet> jsou přidány do projektu. Ovládací prvek vázán <xref:System.Windows.Forms.BindingSource>, který naopak je vázána <xref:System.Data.DataSet> instance.  
  
5.  V **zdroje dat** projděte dolů po sloupce, které jsou v okně **Dodavatelé** tabulky. V dolní části seznamu je **produkty** tabulky; je zde, protože je podřízená **Dodavatelé** tabulky. Tuto možnost vyberte, **produkty** tabulky, není ten, který je na stejné úrovni jako **Dodavatelé** tabulky a potom klikněte na šipku rozevíracího seznamu, který se zobrazí.  
  
6.  Klikněte na tlačítko **ListObject** v rozevíracím seznamu a pak přetáhněte **produkty** tabulky do buňky **A6** v `Sheet1`.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek s názvem `ProductNameListObject` je vytvořen v buňce **A6**. Ve stejnou dobu <xref:System.Windows.Forms.BindingSource> s názvem `productsBindingSource` a adaptér tabulky jsou přidány do projektu. Ovládací prvek vázán <xref:System.Windows.Forms.BindingSource>, který naopak je vázána <xref:System.Data.DataSet> instance.  
  
7.  Pro jazyk C# pouze, vyberte **suppliersBindingSource** na komponent a změňte **modifikátory** vlastnost **interní** v **vlastnosti** okno.  
  
## <a name="add-controls-to-the-actions-pane"></a>Přidání ovládacích prvků do podokna akce  
 Dále musíte prvek podokna akce, který má pole se seznamem.  
  
### <a name="to-add-an-actions-pane-control"></a>Přidání ovládacího prvku podokno akcí  
  
1.  Vyberte **Moje podokně akcí aplikace Excel** projektu v **Průzkumníku řešení**.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogové okno, vyberte **ovládací prvek podokna akce**, pojmenujte ji **ActionsControl**a klikněte na tlačítko **přidat**.  
  
### <a name="to-add-data-bound-windows-forms-controls-to-an-actions-pane-control"></a>K přidávání ovládacích prvků Windows Forms vázané na data na ovládací prvek podokna akce  
  
1.  Z **běžné ovládací prvky** kartách **sada nástrojů**, přetáhněte ji <xref:System.Windows.Forms.ComboBox> ovládacího prvku do ovládacího prvku podokno akcí.  
  
2.  Změna **velikost** vlastnost **171, 21**.  
  
3.  Změnit velikost uživatelského ovládacího prvku podle pole se seznamem.  
  
## <a name="bind-the-control-on-the-actions-pane-to-data"></a>Vytvoření vazby ovládacího prvku v podokně Akce k datům  
 V této části budete nastavit zdroj dat <xref:System.Windows.Forms.ComboBox> na stejném zdroji dat, jako <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek v listu.  
  
### <a name="to-set-data-binding-properties-of-the-control"></a>Chcete-li nastavit vlastnosti datové vazby ovládacího prvku  
  
1.  Klikněte pravým tlačítkem na ovládací prvek podokna akce a potom klikněte na **kód zobrazení**.  
  
2.  Přidejte následující kód, který <xref:System.Windows.Forms.UserControl.Load> události ovládacího prvku podokno akcí.  
  
     [!code-vb[Trin_VstcoreActionsPaneExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ActionsControl.vb#1)]
     [!code-csharp[Trin_VstcoreActionsPaneExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ActionsControl.cs#1)]  
  
3.  V jazyce C#, musíte vytvořit obslužnou rutinu události pro `ActionsControl`. Tento kód můžete umístit `ActionsControl` konstruktor. Další informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytváření obslužných rutin událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ActionsControl.cs#2)]  
  
## <a name="show-the-actions-pane"></a>Zobrazit v podokně Akce  
 V podokně Akce nejsou viditelná, dokud nepřidáte ovládacího prvku za běhu.  
  
#### <a name="to-show-the-actions-pane"></a>Chcete-li zobrazit v podokně Akce  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na *ThisWorkbook.vb* nebo *ThisWorkbook.cs*a potom klikněte na **kód zobrazení**.  
  
2.  Vytvořit novou instanci ovládacího prvku uživatele `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#3)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#3)]  
  
3.  V <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> obslužné rutiny události z `ThisWorkbook`, přidání ovládacího prvku do podokna akce.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#4)]  
  
## <a name="test-the-application"></a>Testování aplikace  
 Nyní můžete otestovat dokumentu ověřit, že při otevření dokumentu se otevře v podokně Akce a že ovládacích prvků mají hlavní a podrobný vztah.  
  
### <a name="to-test-your-document"></a>K testování dokumentu  
  
1.  Stiskněte klávesu **F5** ke spuštění projektu.  
  
2.  Potvrďte, že je zobrazen v podokně Akce.  
  
3.  V rozevíracím seznamu vyberte společnosti. Ověřte, zda název společnosti je uveden v <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení a že jsou uvedeny podrobnosti o produktu v <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku.  
  
4.  Vyberte různé společnosti ověřit název společnosti, a podle potřeby změnit podrobnosti o produktu.  
  
## <a name="next-steps"></a>Další kroky  
 Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Vazba dat s ovládacími prvky v aplikaci Word. Další informace najdete v tématu [návod: svázání dat s ovládacími prvky v podokně akcí aplikace Word](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md).  
  
-   Nasazení projektu. Další informace najdete v tématu [nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
## <a name="see-also"></a>Viz také:  
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Postupy: Správa rozložení ovládacích prvků v podoknech akcí](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  