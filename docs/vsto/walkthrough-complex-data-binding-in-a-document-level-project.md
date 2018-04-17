---
title: 'Návod: Rozšířené datové vazby v projektech na úrovni dokumentu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], binding data
- complex data [Office development in Visual Studio]
- multiple column data binding [Office development in Visual Studio]
- data binding [Office development in Visual Studio], multiple columns
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a46a0f30fe3ab0cfc44a4cdb9121c4f39f3c417f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-complex-data-binding-in-a-document-level-project"></a>Návod: Rozšířené datové vazby v projektech na úrovni dokumentu
  Tento návod ukazuje základy rozšířené datové vazby v projektech na úrovni dokumentu. Více buněk v listu aplikace Microsoft Office Excel můžete vázat na pole v databázi Northwind SQL serveru.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Přidání zdroje dat do projektu sešitu.  
  
-   Přidání ovládacích prvků vázané na data na listu.  
  
-   Ukládají se změny data zpět do databáze.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Přístup na server s ukázková databáze Northwind SQL Server.  
  
-   Oprávnění ke čtení z a zapisovat do databáze SQL serveru.  
  
## <a name="creating-a-new-project"></a>Vytvoření nového projektu  
 Prvním krokem je vytvoření projektu sešitu aplikace Excel.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **Moje komplexní datové vazby**. V průvodci vyberte **vytvoříte nový textový dokument**.  
  
     Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **Moje komplexní datové vazby** projektu do **Průzkumníku řešení**.  
  
## <a name="creating-the-data-source"></a>Vytvoření zdroje dat  
 Použití **zdroje dat** okno pro přidání typové datové sady do projektu.  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Pokud **zdroje dat** okno není viditelný, zobrazit, na řádku nabídky, výběr **zobrazení**, **ostatní okna**, **zdroje dat**.  
  
2.  Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
3.  Vyberte **databáze** a pak klikněte na **Další**.  
  
4.  Vyberte datové připojení k systému SQL Server ukázková databáze Northwind, nebo přidejte nové připojení pomocí **nové připojení** tlačítko.  
  
5.  Po připojení byla vybrána nebo vytvořili, klikněte na tlačítko **Další**.  
  
6.  Zrušte možnost uložit připojení, pokud je zaškrtnuto a pak klikněte na **Další**.  
  
7.  Rozbalte položku **tabulky** uzlu **databázové objekty** okno.  
  
8.  Zaškrtněte políčko vedle položky **zaměstnanci** tabulky.  
  
9. Klikněte na tlačítko **Dokončit**.  
  
 Průvodce přidá **zaměstnanci** a **zdroje dat** okno. Také přidá typové datové sady do projektu, který se zobrazí na **Průzkumníku řešení**.  
  
## <a name="adding-controls-to-the-worksheet"></a>Přidání ovládacích prvků na list  
 List se zobrazí **zaměstnanci** tabulky při otevření sešitu. Budou uživatelé moci měnit data a pak kliknutím na tlačítko Uložit tyto změny zpět do databáze.  
  
 Chcete-li vytvořit vazbu na listu do tabulky automaticky, můžete přidat <xref:Microsoft.Office.Tools.Excel.ListObject> řízení listu z **zdroje dat** okno. Udělit uživatele můžete uložit změny, přidat <xref:System.Windows.Forms.Button> řídit z **sada nástrojů**.  
  
#### <a name="to-add-a-list-object"></a>Chcete-li přidat objekt seznamu  
  
1.  Ověřte, zda **Moje komplexní Data Binding.xlsx** je sešit otevřít v návrháři Visual Studio s **Sheet1** zobrazí.  
  
2.  Otevřete **zdroje dat** okno a vybrat **zaměstnanci** uzlu.  
  
3.  Klikněte na šipku rozevíracího seznamu, který se zobrazí.  
  
4.  Vyberte **ListObject** v rozevíracím seznamu.  
  
5.  Přetáhněte **zaměstnanci** tabulky do buňky **A6**.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek s názvem `EmployeesListObject` je vytvořen v buňce **A6**. Ve stejnou dobu <xref:System.Windows.Forms.BindingSource> s názvem `EmployeesBindingSource`, adaptérem tabulky a <xref:System.Data.DataSet> instance jsou přidány do projektu. Ovládací prvek vázán <xref:System.Windows.Forms.BindingSource>, který naopak je vázána <xref:System.Data.DataSet> instance.  
  
#### <a name="to-add-a-button"></a>Přidání tlačítka  
  
1.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přidejte <xref:System.Windows.Forms.Button> ovládacího prvku do buňky **A4** listu.  
  
 Dalším krokem je přidání text pro tlačítko po otevření sešitu.  
  
## <a name="initializing-the-control"></a>Inicializace ovládacího prvku  
 Přidat text pro tlačítko v <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> obslužné rutiny události.  
  
#### <a name="to-initialize-the-control"></a>K chybě při inicializaci ovládacího prvku  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Sheet1.vb** nebo **Sheet1.cs**a potom klikněte na **kód zobrazení** v místní nabídce.  
  
2.  Přidejte následující kód, který `Sheet1_Startup` metodu a nastavit text pro b`utton`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#8)]
     [!code-vb[Trin_VstcoreDataExcel#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet3.vb#8)]  
  
3.  Pro jazyk C# pouze, přidejte obslužnou rutinu události pro <xref:System.Windows.Forms.Control.Click> událost, která má `Sheet1_Startup` metoda.  
  
     [!code-csharp[Trin_VstcoreDataExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#9)]  
  
 Teď přidejte kód pro zpracování <xref:System.Windows.Forms.Control.Click> události tlačítka.  
  
## <a name="saving-changes-to-the-database"></a>Ukládání změn do databáze  
 Byly provedeny změny dat existovat jenom v místní datové sady, dokud se explicitně uložena zpět do databáze.  
  
#### <a name="to-save-changes-to-the-database"></a>Uložení změn do databáze  
  
1.  Přidání obslužné rutiny události pro <xref:System.Windows.Forms.Control.Click> událostí b`utton`a přidejte následující kód k potvrzení všechny změny provedené v datové sadě zpět do databáze.  
  
     [!code-csharp[Trin_VstcoreDataExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#10)]
     [!code-vb[Trin_VstcoreDataExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet3.vb#10)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat sešit ověřit, že se data zobrazí podle očekávání a data v seznamu objektů můžete pracovat s.  
  
#### <a name="to-test-the-data-binding"></a>K testování datová vazba  
  
-   Stiskněte klávesu F5.  
  
     Ověřte, že po otevření sešitu list objekt, naplní se data z **zaměstnanci** tabulky.  
  
#### <a name="to-modify-data"></a>Úprava dat  
  
1.  Klikněte na buňku **B7**, který by měl obsahovat název **nich pak**.  
  
2.  Zadejte název **Anderson**, a stiskněte klávesu ENTER.  
  
#### <a name="to-modify-a-column-header"></a>Změnit záhlaví sloupce  
  
1.  Klikněte na buňku, která obsahuje záhlaví sloupce **LastName**.  
  
2.  Typ **příjmení**, včetně mezeru mezi slova a stiskněte klávesu ENTER.  
  
#### <a name="to-save-data"></a>Při ukládání dat  
  
1.  Klikněte na tlačítko **Uložit** na listu.  
  
2.  Ukončete aplikaci Excel. Klikněte na tlačítko **ne** při zobrazení výzvy k uložit provedené změny.  
  
3.  Stisknutím klávesy F5 spusťte projekt znovu.  
  
     Objekt seznamu je vyplněn daty z **zaměstnanci** tabulky.  
  
4.  Všimněte si, že název v buňce **B7** stále **Anderson**, které jsou data změnit provedené a uložena zpět do databáze. Záhlaví sloupce **LastName** došlo ke změně zpět na původní podobě bez mezery, protože databáze není vázán na záhlaví sloupce a změny provedené na listu nebyla uložena.  
  
#### <a name="to-add-new-rows"></a>Chcete-li přidat nové řádky  
  
1.  Vyberte buňku v seznamu objektu.  
  
     V dolní části seznamu, s hvězdičkou se zobrazí nový řádek (**\***) v první buňky pro nový řádek.  
  
2.  Přidejte následující informace v prázdný řádek.  
  
    |Číslo zaměstnance|Příjmení|FirstName|Název|  
    |----------------|--------------|---------------|-----------|  
    |10|Ito|Šu|Vedoucí prodeje|  
  
#### <a name="to-delete-rows"></a>Odstranění řádků  
  
-   Klikněte pravým tlačítkem na číslo 16 (řádek 16) na levé listu a pak klikněte na **odstranit**.  
  
#### <a name="to-sort-the-rows-in-the-list"></a>Řazení řádků v seznamu  
  
1.  Vyberte buňku v seznamu.  
  
     Tlačítek se zobrazí v záhlaví sloupce.  
  
2.  Klikněte na tlačítko se šipkou v **příjmení** záhlaví sloupce.  
  
3.  Klikněte na tlačítko **seřadit vzestupně**.  
  
     Řádky jsou seřazené podle abecedy podle příjmení.  
  
#### <a name="to-filter-information"></a>Pro filtrování informací  
  
1.  Vyberte buňku v seznamu.  
  
2.  Klikněte na tlačítko se šipkou v **název** záhlaví sloupce.  
  
3.  Klikněte na tlačítko **obchodním zástupcem**.  
  
     V seznamu jsou uvedeny pouze řádky, které mají **prodej reprezentativní** v **název** sloupce.  
  
4.  Klikněte na tlačítko se šipkou v **název** znovu záhlaví sloupce.  
  
5.  Klikněte na tlačítko **(vše)**.  
  
     Filtrování je odebrána a zobrazit všechny řádky.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základy vazby tabulky v databázi na objekt seznamu. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Data v mezipaměti, aby se může použít do offline režimu. Další informace najdete v tématu [postup: Data do mezipaměti pro použití v režimu Offline nebo na serveru](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   Nasazení řešení. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
-   Vytvořte hlavní a podrobný vztah mezi pole a tabulku. Další informace najdete v tématu [návod: vytváření s použitím vztah hlavní podrobností datové sady do mezipaměti](../vsto/walkthrough-creating-a-master-detail-relation-using-a-cached-dataset.md).  
  
## <a name="see-also"></a>Viz také  
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)   
 [Návod: Jednoduché datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)  
  
  