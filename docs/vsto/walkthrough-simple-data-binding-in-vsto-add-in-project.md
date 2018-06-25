---
title: 'Návod: Jednoduché datové vazby v projektu doplňku VSTO'
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
- data binding [Office development in Visual Studio], Word
- data [Office development in Visual Studio], simple binding data
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8903f18a578c9365b34ea420706b4e9f41fd2b1c
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758958"
---
# <a name="walkthrough-simple-data-binding-in-vsto-add-in-project"></a>Návod: Jednoduché datové vazby v projektu doplňku VSTO

Data můžete vázat na hostiteli a ovládacích prvků Windows Forms v projekty doplňku VSTO. Tento návod ukazuje, jak přidání ovládacích prvků do dokumentu aplikace Microsoft Office Word a vytvoření vazby ovládacích prvků k datům v době běhu.

[!INCLUDE[appliesto_wdallapp](../vsto/includes/appliesto-wdallapp-md.md)]

Tento návod znázorňuje následující úlohy:

-   Přidání <xref:Microsoft.Office.Tools.Word.ContentControl> do dokumentu za běhu.

-   Vytváření <xref:System.Windows.Forms.BindingSource> ovládacího prvku, připojí k instanci datové sady.

-   Povolení uživatelům procházet záznamů a jejich zobrazení v ovládacím prvku.

[!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Požadavky

K dokončení tohoto návodu budete potřebovat následující komponenty:

-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].

-   Přístup k spuštěnou instanci systému SQL Server 2005 nebo SQL Server 2005 Express, která má `AdventureWorksLT` ukázkové databáze, které jsou k němu připojen. Si můžete stáhnout `AdventureWorksLT` databáze z [webu CodePlex](http://go.microsoft.com/fwlink/?LinkId=115611). Další informace o připojení databáze najdete v následujících tématech:

    -   Připojení databáze pomocí SQL Server Management Studio nebo SQL Server Management Studio Express, najdete v části [postupy: připojení databáze (SQL Server Management Studio)](http://msdn.microsoft.com/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa).

    -   Připojení databáze pomocí příkazového řádku, najdete v části [postupy: připojení souboru databáze k systému SQL Server Express](http://msdn.microsoft.com/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68).

## <a name="create-a-new-project"></a>Vytvoření nového projektu

Prvním krokem je vytvoření projektu doplňku VSTO pro Word.

### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt

1.  Vytvoření projektu doplňku VSTO pro Word s názvem **naplnění dokumenty z databáze**, pomocí Visual Basic a C#.

     Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).

     Otevře se Visual Studio *ThisAddIn.vb* nebo *ThisAddIn.cs* souboru a přidá **naplnění dokumenty z databáze** projektu do **Průzkumníku řešení** .

2.  Pokud vaše cíle projektu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], přidejte odkaz na *Microsoft.Office.Tools.Word.v4.0.Utilities.dll* sestavení. Tento odkaz je potřeba přidávání ovládacích prvků Windows Forms v dokumentu dále v tomto návodu prostřednictvím kódu programu.

## <a name="create-a-data-source"></a>Vytvořte zdroj dat.

Použití **zdroje dat** okno pro přidání typové datové sady do projektu.

### <a name="to-add-a-typed-dataset-to-the-project"></a>Chcete-li přidat typové datové sady do projektu

1.  Pokud **zdroje dat** okno není viditelný, zobrazit, na řádku nabídky, výběr **zobrazení** > **ostatní okna**  >   **Zdroje dat**.

2.  Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.

3.  Klikněte na tlačítko **databáze**a potom klikněte na **Další**.

4.  Pokud máte stávající připojení k `AdventureWorksLT` databázi, vyberte toto připojení a klikněte na tlačítko **Další**.

     Jinak, klikněte na tlačítko **nové připojení**a použít **přidat připojení** dialogové okno vytvořit nové připojení. Další informace najdete v tématu [přidat nová připojení](../data-tools/add-new-connections.md).

5.  V **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.

6.  V **zvolte si databázové objekty** rozbalte **tabulky** a vyberte **zákazníků (SalesLT)**.

7.  Klikněte na tlačítko **Dokončit**.

     *AdventureWorksLTDataSet.xsd* se přidá soubor **Průzkumníku řešení**. Tento soubor definuje následující položky:

    -   Typové datové sady s názvem `AdventureWorksLTDataSet`. Tato datová sada představuje obsah **zákazníků (SalesLT)** tabulky v databázi AdventureWorksLT.

    -   TableAdapter s názvem `CustomerTableAdapter`. Tato TableAdapter lze číst a zapisovat data v `AdventureWorksLTDataSet`. Další informace najdete v tématu [TableAdapter – přehled](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).

     Obě tyto objekty použijete později v tomto návodu.

## <a name="create-controls-and-binding-controls-to-data"></a>Vytvoření a vazby ovládacích prvků k datům

Rozhraní pro zobrazení záznamů databáze v tomto návodu je základní a je vytvořen vpravo uvnitř dokumentu. Jeden <xref:Microsoft.Office.Tools.Word.ContentControl> zobrazí záznam jedné databáze na čas a dvě <xref:Microsoft.Office.Tools.Word.Controls.Button> ovládací prvky umožňují procházet záznamů a zpět. Používá obsahu ovládacího prvku <xref:System.Windows.Forms.BindingSource> pro připojení k databázi.

Další informace o připojení ovládacích prvků k datům najdete v tématu [vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).

### <a name="to-create-the-interface-in-the-document"></a>Chcete-li vytvořit rozhraní v dokumentu

1.  V `ThisAddIn` třídy, deklarovat následující ovládací prvky zobrazení a posuňte `Customer` tabulky `AdventureWorksLTDataSet` databáze.

     [!code-vb[Trin_WordAddInDatabase#1](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInDatabase#1](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#1)]

2.  V `ThisAddIn_Startup` metoda, přidejte následující kód k inicializaci datovou sadu, vyplnění datové sady s informacemi z `AdventureWorksLTDataSet` databáze.

     [!code-vb[Trin_WordAddInDatabase#2](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#2)]
     [!code-csharp[Trin_WordAddInDatabase#2](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#2)]

3.  Přidejte následující kód, který `ThisAddIn_Startup` metoda. Tím se vygeneruje položku hostitele, který rozšiřuje dokumentu. Další informace najdete v tématu [dokumentů rozšířit aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

     [!code-vb[Trin_WordAddInDatabase#3](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#3)]
     [!code-csharp[Trin_WordAddInDatabase#3](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#3)]

4.  Definujte několik rozsahů na začátku dokumentu. Tyto rozsahy určete, kam chcete vložit text a umístěte ovládací prvky.

     [!code-vb[Trin_WordAddInDatabase#4](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#4)]
     [!code-csharp[Trin_WordAddInDatabase#4](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#4)]

5.  Přidání ovládacích prvků rozhraní na dříve definované oblasti.

     [!code-vb[Trin_WordAddInDatabase#5](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#5)]
     [!code-csharp[Trin_WordAddInDatabase#5](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#5)]

6.  Vytvoření vazby ovládacího prvku obsahu k `AdventureWorksLTDataSet` pomocí <xref:System.Windows.Forms.BindingSource>. Pro C# vývojáře, přidejte pro dvě obslužné rutiny událostí <xref:Microsoft.Office.Tools.Word.Controls.Button> ovládací prvky.

     [!code-vb[Trin_WordAddInDatabase#6](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#6)]
     [!code-csharp[Trin_WordAddInDatabase#6](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#6)]

7.  Přidejte následující kód procházet záznamů databáze.

     [!code-vb[Trin_WordAddInDatabase#7](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#7)]
     [!code-csharp[Trin_WordAddInDatabase#7](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#7)]

## <a name="test-the-add-in"></a>Testování v aplikaci

Při otevření aplikace Word obsahu ovládací prvek zobrazí data z `AdventureWorksLTDataSet` datovou sadu. Procházení databázových záznamů kliknutím **Další** a **předchozí** tlačítka.

### <a name="to-test-the-vsto-add-in"></a>K testování doplňku VSTO

1.  Stiskněte klávesu **F5**.

     Ovládací prvek obsahu s názvem `customerContentControl` se vytvoří a naplněný daty. Současně, objekt datovou sadu s názvem `adventureWorksLTDataSet` a <xref:System.Windows.Forms.BindingSource> s názvem `customerBindingSource` jsou přidány do projektu. <xref:Microsoft.Office.Tools.Word.ContentControl> Je vázána <xref:System.Windows.Forms.BindingSource>, který je pak vázaná na objekt datové sady.

2.  Klikněte **Další** a **předchozí** na tlačítka posouvání záznamů databáze.

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
- [Postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [Postupy: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Použití místních souborů databáze v přehled řešení pro systém Office](../vsto/using-local-database-files-in-office-solutions-overview.md)
- [BindingSource – přehled komponenty](/dotnet/framework/winforms/controls/bindingsource-component-overview)