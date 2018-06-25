---
title: 'Návod: Rozšířené datové vazby v projektu doplňku VSTO'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding [Office development in Visual Studio], Excel
- data [Office development in Visual Studio], binding data
- complex data [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fd034f4802679daa442f04b469a37f04d580ea94
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758968"
---
# <a name="walkthrough-complex-data-binding-in-vsto-add-in-project"></a>Návod: Rozšířené datové vazby v projektu doplňku VSTO
  Data můžete vázat na hostiteli a ovládacích prvků Windows Forms v projekty doplňku VSTO. Tento návod ukazuje, jak přidání ovládacích prvků do listu aplikace Microsoft Office Excel a vytvoření vazby ovládacích prvků k datům v době běhu.

 [!INCLUDE[appliesto_xlallapp](../vsto/includes/appliesto-xlallapp-md.md)]

 Tento návod znázorňuje následující úlohy:

-   Přidání <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku na list za běhu.

-   Vytváření <xref:System.Windows.Forms.BindingSource> ovládacího prvku, připojí k instanci datové sady.

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Požadavky
 K dokončení tohoto návodu budete potřebovat následující komponenty:

-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].

-   Přístup k spuštěnou instanci systému SQL Server 2005 nebo SQL Server 2005 Express, která má `AdventureWorksLT` ukázkové databáze, které jsou k němu připojen. Si můžete stáhnout `AdventureWorksLT` databáze z [webu CodePlex](http://go.microsoft.com/fwlink/?LinkId=115611). Další informace o připojení databáze najdete v následujících tématech:

    -   Připojení databáze pomocí SQL Server Management Studio nebo SQL Server Management Studio Express, najdete v části [postupy: připojení databáze (SQL Server Management Studio)](http://msdn.microsoft.com/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa).

    -   Připojení databáze pomocí příkazového řádku, najdete v části [postupy: připojení souboru databáze k systému SQL Server Express](http://msdn.microsoft.com/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68).

## <a name="create-a-new-project"></a>Vytvoření nového projektu
 Prvním krokem je vytvoření projektu doplňku VSTO v Excelu.

### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt

1.  Vytvoření projektu doplňku VSTO pro Excel s názvem **naplnění listů z databáze**, pomocí Visual Basic a C#.

     Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).

     Otevře se Visual Studio `ThisAddIn.vb` nebo `ThisAddIn.cs` souboru a přidá **naplnění listů z databáze** projektu do **Průzkumníku řešení**.

## <a name="create-a-data-source"></a>Vytvořte zdroj dat.
 Použití **zdroje dat** okno pro přidání typové datové sady do projektu.

### <a name="to-add-a-typed-dataset-to-the-project"></a>Chcete-li přidat typové datové sady do projektu

1.  Pokud **zdroje dat** okno není viditelný, zobrazit, na řádku nabídky, výběr **zobrazení** > **ostatní okna**  >   **Zdroje dat**.

2.  Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.

3.  Klikněte na tlačítko **databáze**a potom klikněte na **Další**.

4.  Pokud máte stávající připojení k `AdventureWorksLT` databázi, vyberte toto připojení a klikněte na tlačítko **Další**.

     Jinak, klikněte na tlačítko **nové připojení**a použít **přidat připojení** dialogové okno vytvořit nové připojení. Další informace najdete v tématu [přidat nová připojení](../data-tools/add-new-connections.md).

5.  V **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.

6.  V **zvolte si databázové objekty** rozbalte **tabulky** a vyberte **adresu (SalesLT)**.

7.  Klikněte na tlačítko **Dokončit**.

     *AdventureWorksLTDataSet.xsd* se přidá soubor **Průzkumníku řešení**. Tento soubor definuje následující položky:

    -   Typové datové sady s názvem `AdventureWorksLTDataSet`. Tato datová sada představuje obsah **adresu (SalesLT)** tabulky v databázi AdventureWorksLT.

    -   TableAdapter s názvem `AddressTableAdapter`. Tato TableAdapter lze číst a zapisovat data v `AdventureWorksLTDataSet`. Další informace najdete v tématu [TableAdapter – přehled](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).

     Obě tyto objekty použijete později v tomto návodu.

## <a name="create-controls-and-bind-controls-to-data"></a>Vytvořit ovládací prvky a vytvoření vazby ovládacích prvků k datům
 V tomto návodu <xref:Microsoft.Office.Tools.Excel.ListObject> zobrazí všechna data v tabulce, které jste vybrali při otevření sešitu. Používá objekt seznamu <xref:System.Windows.Forms.BindingSource> pro ovládací prvek připojení k databázi.

 Další informace o připojení ovládacích prvků k datům najdete v tématu [vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).

### <a name="to-add-the-list-object-dataset-and-table-adapter"></a>Přidání objektu seznamu, datové sady a adaptér tabulky

1.  V `ThisAddIn` třídy, deklarovat následující ovládacích prvků pro zobrazení `Address` tabulky `AdventureWorksLTDataSet` datovou sadu.

     [!code-csharp[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#1)]

2.  V `ThisAddIn_Startup` metoda, přidejte následující kód k inicializaci datovou sadu a vyplnění datové sady s informacemi z `AdventureWorksLTDataSet` datovou sadu.

     [!code-csharp[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#2)]
     [!code-vb[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#2)]

3.  Přidejte následující kód, který `ThisAddIn_Startup` metoda. Tím se vygeneruje položku hostitele, který rozšiřuje listu. Další informace najdete v tématu [dokumentů rozšířit aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

     [!code-csharp[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#3)]
     [!code-vb[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#3)]

4.  Vytvořte oblast a přidejte <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku.

     [!code-csharp[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#4)]
     [!code-vb[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#4)]

5.  Seznam objekt, který chcete vytvořit vazbu `AdventureWorksLTDataSet` pomocí <xref:System.Windows.Forms.BindingSource>. Předejte názvy sloupců, které chcete vytvořit vazbu na objekt seznamu.

     [!code-csharp[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#5)]
     [!code-vb[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#5)]

## <a name="test-the-add-in"></a>Testování v aplikaci
 Při otevření aplikace Excel, <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek zobrazí data z `Address` tabulky `AdventureWorksLTDataSet` datovou sadu.

### <a name="to-test-the-vsto-add-in"></a>K testování doplňku VSTO

-   Stiskněte klávesu **F5**.

     A <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek s názvem `addressListObject` je vytvořen v listu. Současně, objekt datovou sadu s názvem `adventureWorksLTDataSet` a <xref:System.Windows.Forms.BindingSource> s názvem `addressBindingSource` jsou přidány do projektu. <xref:Microsoft.Office.Tools.Excel.ListObject> Je vázána <xref:System.Windows.Forms.BindingSource>, který je pak vázaná na objekt datové sady.

## <a name="see-also"></a>Viz také:

- [Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)
- [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Postupy: naplnění listů daty z databáze](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)
- [Postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [Postupy: naplnění dokumentů daty ze služeb](../vsto/how-to-populate-documents-with-data-from-services.md)
- [Postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [Postupy: procházení databázových záznamů na listu](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)
- [Postupy: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Návod: Jednoduché datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)
- [Návod: Rozšířené datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)
- [Použití místních souborů databáze v přehled řešení pro systém Office](../vsto/using-local-database-files-in-office-solutions-overview.md)
- [Přidat nové zdroje dat](../data-tools/add-new-data-sources.md)
- [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Použití místních souborů databáze v přehled řešení pro systém Office](../vsto/using-local-database-files-in-office-solutions-overview.md)
- [BindingSource – přehled komponenty](/dotnet/framework/winforms/controls/bindingsource-component-overview)