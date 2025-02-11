---
title: 'Návod: Načtení dat uložených v mezipaměti ze sešitu na serveru'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks [Office development in Visual Studio], retrieving data
- datasets [Office development in Visual Studio], accessing on server
- server-side data access [Office development in Visual Studio]
- data [Office development in Visual Studio], accessing on server
- documents [Office development in Visual Studio], server-side data access
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d0bcf3f299d1d2d10b3b043b772fca832a505278
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67826125"
---
# <a name="walkthrough-retrieve-cached-data-from-a-workbook-on-a-server"></a>Návod: Načtení dat uložených v mezipaměti ze sešitu na serveru
  Tento návod ukazuje, jak načíst data z datové sady, které se uloží do mezipaměti v sešitu aplikace Microsoft Office Excel bez spuštění pomocí aplikace Excel <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy.

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

 Tento návod znázorňuje následující úlohy:

- Definování datové sady, který obsahuje data z *AdventureWorksLT* databáze.

- Vytvoření instance datové sady v projektu sešitu aplikace Excel a projektu konzolové aplikace.

- Vytváření <xref:Microsoft.Office.Tools.Excel.ListObject> , která je vázaná k datové sadě v sešitu a naplnění <xref:Microsoft.Office.Tools.Excel.ListObject> s daty při otevření sešitu.

- Přidání datovou sadu do mezipaměti dat v sešitu.

- Čtení dat z datové sady v mezipaměti do datové sady v konzolové aplikaci, bez spuštění Excelu.

  I když Tento názorný průvodce předpokládá, že používáte kód ve svém vývojovém počítači, kód jsme vám ukázali v rámci tohoto návodu je možné na server, který nemá nainstalovanou aplikaci Excel.

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

## <a name="prerequisites"></a>Požadavky
 K dokončení tohoto návodu budete potřebovat následující komponenty:

- [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

- [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].

- Přístup ke spuštěné instanci serveru Microsoft SQL Server nebo Microsoft SQL Server Express, který má k němu připojené ukázkové databáze AdventureWorksLT. Můžete stáhnout z databáze AdventureWorksLT [webu CodePlex](http://go.microsoft.com/fwlink/?linkid=87843). Další informace o připojení databáze naleznete v následujících tématech:

  - Připojení databáze pomocí SQL Server Management Studio nebo SQL Server Management Studio Express, naleznete v tématu [jak: Připojení databáze (SQL Server Management Studio)](/sql/relational-databases/databases/attach-a-database).

  - Připojení databáze pomocí příkazového řádku, naleznete v tématu [jak: Připojit soubor databáze pro SQL Server Express](/previous-versions/sql/).

## <a name="create-a-class-library-project-that-defines-a-dataset"></a>Vytvořte projekt knihovny tříd, který definuje datovou sadu
 Pokud chcete použít stejné datové sady v projektu sešitu aplikace Excel a konzolové aplikace, musí definovat datové sady v samostatné sestavení, který je odkazován oba z těchto projektů. V tomto návodu definování datové sady v projektu knihovny tříd.

### <a name="create-the-class-library-project"></a>Vytvořte projekt knihovny tříd

1. Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].

2. Na **souboru** nabídky, přejděte k **nový**a potom klikněte na tlačítko **projektu**.

3. V podokně šablony rozbalte **Visual C#** nebo **jazyka Visual Basic**a potom klikněte na tlačítko **Windows**.

4. V seznamu šablon projektu vyberte **knihovny tříd**.

5. V **název** zadejte **AdventureWorksDataSet**.

6. Klikněte na tlačítko **Procházet**, přejděte k vaší *%UserProfile%\My dokumenty* (pro Windows XP a starší) nebo *%UserProfile%\Documents* (pro Windows Vista) složku a potom klikněte na **Vyberte složku**.

7. V **nový projekt** dialogového okna zkontrolujte, zda **vytvořit adresář pro řešení** není zaškrtnuté políčko.

8. Klikněte na **OK**.

     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **AdventureWorksDataSet** projektu **Průzkumníka řešení** a otevře *Class1.cs* nebo *Class1.vb* soubor kódu.

9. V **Průzkumníka řešení**, klikněte pravým tlačítkem na *Class1.cs* nebo *Class1.vb*a potom klikněte na tlačítko **odstranit**. Tento soubor není nutné v tomto návodu.

## <a name="define-a-dataset-in-the-class-library-project"></a>Definování datové sady v projektu knihovny tříd
 Definujte typové datové sady, který obsahuje data z databáze AdventureWorksLT pro SQL Server 2005. Později v tomto návodu bude odkazovat tento objekt dataset z projektu sešitu aplikace Excel a projektu konzolové aplikace.

 Tato datová sada je *zadaná datová sada* , která představuje data v tabulce Product databázi AdventureWorksLT. Další informace o definovaných datových sadách najdete v tématu [datovou sadu nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md).

### <a name="define-a-typed-dataset-in-the-class-library-project"></a>Typové datové sady definovat v projektu knihovny tříd

1. V **Průzkumníka řešení**, klikněte na tlačítko **AdventureWorksDataSet** projektu.

2. Pokud **zdroje dat** okno se nezobrazuje, zobrazit ho tím, na panelu nabídek, výběrem **zobrazení** > **ostatní Windows**  >   **Zdroje dat**.

3. Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.

4. Klikněte na tlačítko **databáze**a potom klikněte na tlačítko **Další**.

5. Pokud máte existující připojení k databázi AdventureWorksLT, vyberte toto připojení a klikněte na tlačítko **Další**.

    V opačném případě klikněte na tlačítko **nové připojení**a použít **přidat připojení** dialogové okno pro vytvoření nového připojení. Další informace najdete v tématu [přidat nové připojení](../data-tools/add-new-connections.md).

6. V **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na **Další**.

7. V **zvolte vaše databázové objekty** stránce, rozbalte **tabulky** a vyberte **produkt (SalesLT)** .

8. Klikněte na tlačítko **Dokončit**.

    *AdventureWorksLTDataSet.xsd* přidá soubor **AdventureWorksDataSet** projektu. Tento soubor definuje následující položky:

   - Typové datové sady s názvem `AdventureWorksLTDataSet`. Tato datová sada představuje obsah tabulky produktů v databázi AdventureWorksLT.

   - TableAdapter s názvem `ProductTableAdapter`. Této třídy TableAdapter lze číst a zapisovat data `AdventureWorksLTDataSet`. Další informace najdete v tématu [TableAdapter – přehled](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).

     Obě tyto objekty použijete později v tomto názorném postupu.

9. V **Průzkumníka řešení**, klikněte pravým tlačítkem na **AdventureWorksDataSet** a klikněte na tlačítko **sestavení**.

     Ověřte, že projekt se sestaví bez chyb.

## <a name="create-an-excel-workbook-project"></a>Vytvoření projektu sešitu aplikace Excel
 Vytvoření projektu sešitu aplikace Excel pro rozhraní pro data. Později v tomto návodu vytvoříte <xref:Microsoft.Office.Tools.Excel.ListObject> , která zobrazuje data, a přidáte instance datové sady do mezipaměti dat v sešitu.

### <a name="create-the-excel-workbook-project"></a>Vytvořte projekt sešitu aplikace Excel

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksDataSet** řešení, přejděte na **přidat**a potom klikněte na tlačítko **nový projekt**.

2. V podokně šablony rozbalte **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.

3. V rozbalených **Office/SharePoint** uzlu, vyberte **Office Add-ins** uzlu.

4. V seznamu šablon projektu vyberte **sešit aplikace Excel 2010** nebo **sešit aplikace Excel 2013** projektu.

5. V **název** zadejte **AdventureWorksReport**. Neprovádějte žádné změny umístění.

6. Klikněte na **OK**.

     **Visual Studio Tools for Office Project Wizard** otevře.

7. Ujistěte se, že **vytvoříte nový textový dokument** je vybraná a klikněte na tlačítko **OK**.

     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře **AdventureWorksReport** sešit v návrháři a přidá **AdventureWorksReport** projektu **Průzkumníka řešení**.

## <a name="add-the-dataset-to-data-sources-in-the-excel-workbook-project"></a>Přidat datovou sadu do zdroje dat v projektu sešitu aplikace Excel
 Než budete moci zobrazit datovou sadu v sešitu aplikace Excel, musíte nejprve přidat datové sady ke zdrojům dat v projektu sešitu aplikace Excel.

1. V **Průzkumníka řešení**, dvakrát klikněte na panel *Sheet1.cs* nebo *Sheet1.vb* pod **AdventureWorksReport** projektu.

     Sešit se otevře v návrháři.

2. Na **Data** nabídky, klikněte na tlačítko **přidat nový zdroj dat**.

     **Průvodce konfigurací zdroje dat** otevře.

3. Klikněte na tlačítko **objekt**a potom klikněte na tlačítko **Další**.

4. V **vyberte objektu vazby** stránky, klikněte na tlačítko **přidat odkaz**.

5. Na **projekty** klikněte na tlačítko **AdventureWorksDataSet** a potom klikněte na tlačítko **OK**.

6. V části **AdventureWorksDataSet** obor názvů **AdventureWorksDataSet** sestavení, klikněte na tlačítko **AdventureWorksLTDataSet** a potom klikněte na tlačítko **dokončit** .

     **Zdroje dat** otevře se okno, a **AdventureWorksLTDataSet** se přidá do seznamu datových zdrojů.

## <a name="create-a-listobject-that-is-bound-to-an-instance-of-the-dataset"></a>Vytvoření objektu ListObject, který je vázán k instanci datové sady
 Chcete-li zobrazit datovou sadu v sešitu, vytvořte <xref:Microsoft.Office.Tools.Excel.ListObject> , která je svázána s instancí datové sady. Další informace o vázání ovládacích prvků na data, najdete v části [vytvoření vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).

1. V **zdroje dat** okna, rozbalte **AdventureWorksLTDataSet** pod uzlem **AdventureWorksDataSet**.

2. Vyberte **produktu** uzel, klikněte na šipku rozevíracího seznamu, která se zobrazí a vyberte **ListObject** v rozevíracím seznamu.

     Pokud na šipku rozevíracího seznamu se nezobrazí, zkontrolujte, že sešit je v Návrháři otevřený.

3. Přetáhněte **produktu** tabulky do buňky A1.

     A <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek s názvem `productListObject` je vytvořen na listu, počínaje buňku A1. Současně, objekt datovou sadu s názvem `adventureWorksLTDataSet` a <xref:System.Windows.Forms.BindingSource> s názvem `productBindingSource` jsou přidány do projektu. <xref:Microsoft.Office.Tools.Excel.ListObject> Je vázán na <xref:System.Windows.Forms.BindingSource>, která je dále vázán na objektu dataset.

## <a name="add-the-dataset-to-the-data-cache"></a>Přidat datovou sadu do mezipaměti dat
 Pokud chcete povolit kód mimo projektu sešitu aplikace Excel přístup k datové sadě v sešitu, musíte přidat datovou sadu do datové mezipaměti. Další informace o mezipaměti dat najdete v tématu [data v přizpůsobeních na úrovni dokumentu v mezipaměti](../vsto/cached-data-in-document-level-customizations.md) a [ukládat data do mezipaměti](../vsto/caching-data.md).

1. V návrháři, klikněte na tlačítko **adventureWorksLTDataSet**.

2. V **vlastnosti** okno, nastaveno **modifikátory** vlastnost **veřejné**.

3. Nastavte **CacheInDocument** vlastnost **True**.

## <a name="initialize-the-dataset-in-the-workbook"></a>Inicializovat datové sady v sešitu
 Předtím, než můžete načíst data z datové sady v mezipaměti pomocí konzolové aplikace, musíte nejprve naplnění datové sady v mezipaměti s daty.

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem myši *Sheet1.cs* nebo *Sheet1.vb* souboru a klikněte na tlačítko **zobrazit kód**.

2. Nahradit `Sheet1_Startup` obslužné rutiny události s následujícím kódem. Tento kód používá instanci `ProductTableAdapter` třídu, která je definována v **AdventureWorksDataSet** projekt tak, aby vyplnil datové sady v mezipaměti s daty, pokud je aktuálně prázdný.

     [!code-csharp[Trin_CachedDataWalkthroughs#8](../vsto/codesnippet/CSharp/AdventureWorksDataSet/AdventureWorksReport/Sheet1.cs#8)]
     [!code-vb[Trin_CachedDataWalkthroughs#8](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/AdventureWorksReport/Sheet1.vb#8)]

## <a name="checkpoint"></a>CheckPoint
 Sestavení a spuštění projektu sešitu aplikace Excel k zajištění, že se zkompiluje a spustí bez chyb. Tato operace také vyplní celé datové sady v mezipaměti a ukládá data v sešitu.

### <a name="build-and-run-the-project"></a>Sestavení a spuštění projektu

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksReport** projektu, zvolte **ladění**a potom klikněte na **zahájit novou instanci**.

     Sestavení projektu a otevře sešit v Excelu. Ověřte následující:

    - <xref:Microsoft.Office.Tools.Excel.ListObject> Vyplní daty.

    - Hodnota v **ListPrice** sloupec prvního řádku <xref:Microsoft.Office.Tools.Excel.ListObject> je 1431.5. Dále v tomto názorném postupu použijete konzolovou aplikaci umožní úpravy hodnot v **ListPrice** sloupce.

2. Uložte sešit. Neprovádějte žádné změny názvu souboru nebo umístění v sešitu.

3. Zavřete aplikaci Excel.

## <a name="create-a-console-application-project"></a>Vytvořte projekt konzolové aplikace
 Vytvořte projekt konzolové aplikace, které chcete použít ke změně dat v datové sady v mezipaměti v sešitu.

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksDataSet** řešení, přejděte na **přidat**a potom klikněte na tlačítko **nový projekt**.

2. V **typy projektů** podokně rozbalte **Visual C#** nebo **jazyka Visual Basic**a potom klikněte na tlačítko **Windows**.

3. V **šablony** vyberte **konzolovou aplikaci**.

4. V **název** zadejte **DataReader**. Neprovádějte žádné změny umístění.

5. Klikněte na **OK**.

     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **DataReader** projektu **Průzkumníku řešení** a otevře *Program.cs* nebo *Module1.vb* soubor kódu.

## <a name="retrieve-data-from-the-cached-dataset-by-using-the-console-application"></a>Načtení dat z datové sady v mezipaměti pomocí konzolové aplikace
 Použití <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy v konzolové aplikaci k načtení dat do místního `AdventureWorksLTDataSet` objektu. Pokud chcete potvrdit, že místní datovou sadou byl inicializován s použitím dat z datové sady v mezipaměti, aplikace zobrazí počet řádků v místní datové sady.

### <a name="retrieve-data-from-the-cached-dataset"></a>Načtení dat z datové sady v mezipaměti

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DataReader** projektu a klikněte na tlačítko **přidat odkaz**.

2. Na **.NET** kartu, vyberte možnost **Microsoft.VisualStudio.Tools.Applications.ServerDocument**.

3. Klikněte na **OK**.

4. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DataReader** projektu a klikněte na tlačítko **přidat odkaz**.

5. Na **projekty** kartu, vyberte možnost **AdventureWorksDataSet**a klikněte na tlačítko **OK**.

6. Otevřít *Program.cs* nebo *Module1.vb* souboru v editoru kódu.

7. Přidejte následující **pomocí** (pro C#) nebo **importy** (pro jazyk Visual Basic) příkaz do horní části souboru kódu.

    [!code-csharp[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#1)]
    [!code-vb[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#1)]

8. Přidejte následující kód, který `Main` metody. Tento kód deklaruje následující objekty:

   - Instance `AdventureWorksLTDataSet` typ, který je definován v **AdventureWorksDataSet** projektu.

   - Cesta k sešitu AdventureWorksReport ve složce sestavení **AdventureWorksReport** projektu.

   - A <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> objektu, který chcete použít pro přístup k mezipaměti dat v sešitu.

     > [!NOTE]
     > Následující kód předpokládá, že sešit je uložen pod *.xlsx* rozšíření. Pokud sešit v projektu má jiné rozšíření, změňte cestu podle potřeby.

     [!code-csharp[Trin_CachedDataWalkthroughs#10](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#10)]
     [!code-vb[Trin_CachedDataWalkthroughs#10](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#10)]

9. Přidejte následující kód, který `Main` metoda po kódu přidaném v předchozím kroku. Tento kód provede následující:

   - Používá <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> vlastnost <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> pro přístup k datové sady v mezipaměti v sešitu.

   - Čte data z datové sady v mezipaměti do místní datové sady.

   - Zobrazí počet řádků v místní datové sady, potvrďte, že obsahuje data.

     [!code-csharp[Trin_CachedDataWalkthroughs#11](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#11)]
     [!code-vb[Trin_CachedDataWalkthroughs#11](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#11)]

10. Na **sestavení** nabídky, klikněte na tlačítko **sestavení DataReader**.

## <a name="test-the-project"></a>Testování projektu
 Když spustíte aplikaci konzoly, zobrazuje počet řádků v místní datové sady.

### <a name="test-the-workbook"></a>Sešit testování

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na **DataReader** projektu, přejděte na **ladění**a potom klikněte na tlačítko **zahájit novou instanci**.

     Ověřte, že aplikace zprávu, že místní datová sada obsahuje 295 řádků.

2. Stisknutím klávesy **Enter** zavřít aplikaci.

## <a name="next-steps"></a>Další postup
 Další informace o práci s data uložená v mezipaměti naleznete v těchto tématech:

- Změna dat v datové sady v mezipaměti bez spuštění Excelu. Další informace najdete v tématu [názorný postup: Změna dat uložených v mezipaměti ze sešitu na serveru](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md).

## <a name="see-also"></a>Viz také:

- [Návod: Vložení dat do sešitu na serveru](../vsto/walkthrough-inserting-data-into-a-workbook-on-a-server.md)
- [Návod: Změna dat uložených v mezipaměti ze sešitu na serveru](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md)
