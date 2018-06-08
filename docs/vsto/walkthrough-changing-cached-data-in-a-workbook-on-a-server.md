---
title: 'Návod: Změna data uložená v mezipaměti v sešitu na serveru'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks [Office development in Visual Studio], changing server data
- datasets [Office development in Visual Studio], accessing on server
- server-side data access [Office development in Visual Studio]
- data [Office development in Visual Studio], accessing on server
- documents [Office development in Visual Studio], server-side data access
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6c46d0eeedfbfa1a9e25d3a89fdade3c923dac7a
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845662"
---
# <a name="walkthrough-change-cached-data-in-a-workbook-on-a-server"></a>Návod: Změna data uložená v mezipaměti v sešitu na serveru
  Tento návod ukazuje, jak upravit datovou sadu, která se uloží do mezipaměti v sešitu aplikace Microsoft Office Excel bez spuštění aplikace Excel pomocí <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Definování datovou sadu, která obsahuje data z databáze AdventureWorksLT.  
  
-   Vytváření instancí datové sady v projektu sešitu aplikace Excel a projekt konzolové aplikace.  
  
-   Vytváření <xref:Microsoft.Office.Tools.Excel.ListObject> která je vázaná na datovou sadu v sešitu a naplnění <xref:Microsoft.Office.Tools.Excel.ListObject> s daty při otevření sešitu.  
  
-   Přidání datovou sadu v sešitu do datové mezipaměti.  
  
-   Úprava sloupce dat v datové sady v mezipaměti spuštěním kódu v konzolové aplikaci, bez spuštění aplikace Excel.  
  
 I když tento návod předpokládá, že používáte kód ve svém vývojovém počítači, kód ukázán podle tohoto návodu jde použít na serveru, který nemá nainstalovanou aplikaci Excel.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Přístup k spuštěnou instanci Microsoft SQL Server nebo Microsoft SQL Server Express, která obsahuje ukázkové databáze AdventureWorksLT k němu připojen. Si můžete stáhnout z databáze AdventureWorksLT [webu CodePlex](http://go.microsoft.com/fwlink/?linkid=87843). Další informace o připojení databáze najdete v následujících tématech:  
  
    -   Připojení databáze pomocí SQL Server Management Studio nebo SQL Server Management Studio Express, najdete v části [postupy: připojení databáze (SQL Server Management Studio)](http://msdn.microsoft.com/en-us/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa).  
  
    -   Připojení databáze pomocí příkazového řádku, najdete v části [postupy: připojení souboru databáze k systému SQL Server Express](http://msdn.microsoft.com/en-us/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68).  
  
## <a name="create-a-class-library-project-that-defines-a-dataset"></a>Vytvoření projektu knihovny tříd, která definuje datové sady  
 Pokud chcete používat se stejnou datovou v projektu sešitu aplikace Excel a konzolovou aplikaci, je nutné zadat datovou sadu v samostatném sestavení, který je odkazován obě tyto projekty. V tomto návodu definování datové sady v projektu knihovny tříd.  
  
### <a name="to-create-the-class-library-project"></a>Vytvoření projektu knihovny tříd  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom klikněte na **Windows**.  
  
4.  V seznamu šablon projektu, vyberte **knihovny tříd**.  
  
5.  V **název** zadejte **AdventureWorksDataSet**.  
  
6.  Klikněte na tlačítko **Procházet**, přejděte na vaše *%UserProfile%\My dokumenty* (pro Windows XP a starší) nebo *%UserProfile%\Documents* (pro systém Windows Vista) složku a pak klikněte na **Vyberte složku**.  
  
7.  V **nový projekt** dialogové okno pole, ujistěte se, že **vytvořit adresář pro řešení** není zaškrtnuté políčko.  
  
8.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **AdventureWorksDataSet** projektu do **Průzkumníku řešení** a otevře **Class1.cs** nebo **Class1.vb** souboru kódu.  
  
9. V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Class1.cs** nebo **Class1.vb**a potom klikněte na **odstranit**. Tento soubor není nutné v tomto návodu.  
  
## <a name="define-a-dataset-in-the-class-library-project"></a>Definování datové sady v projektu knihovny tříd  
 Definujte typové datové sady, který obsahuje data z databáze AdventureWorksLT pro SQL Server 2005. Dále v tomto návodu budete tuto datovou sadu odkazovat z projektu sešitu aplikace Excel a projekt konzolové aplikace.  
  
 Je datová sada *typové datové sady* představující data v tabulce produktu databáze AdventureWorksLT. Další informace o typové datové sady, najdete v části [datové sady nástrojů v sadě Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
### <a name="to-define-a-typed-dataset-in-the-class-library-project"></a>Chcete-li definovat typové datové sady v projektu knihovny tříd  
  
1.  V **Průzkumníku řešení**, klikněte **AdventureWorksDataSet** projektu.  
  
2.  Pokud **zdroje dat** okno není viditelný, zobrazit, na řádku nabídky, výběr **zobrazení** > **ostatní okna**  >   **Zdroje dat**.  
  
3.  Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
4.  Klikněte na tlačítko **databáze**a potom klikněte na **Další**.  
  
5.  Pokud máte existující připojení k databázi AdventureWorksLT, vyberte toto připojení a klikněte na **Další**.  
  
     Jinak, klikněte na tlačítko **nové připojení**a použít **přidat připojení** dialogové okno vytvořit nové připojení. Další informace najdete v tématu [přidat nová připojení](../data-tools/add-new-connections.md).  
  
6.  V **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.  
  
7.  V **zvolte si databázové objekty** rozbalte **tabulky** a vyberte **produkt (SalesLT)**.  
  
8.  Klikněte na tlačítko **Dokončit**.  
  
     *AdventureWorksLTDataSet.xsd* se přidá soubor **AdventureWorksDataSet** projektu. Tento soubor definuje následující položky:  
  
    -   Typové datové sady s názvem `AdventureWorksLTDataSet`. Tato datová sada představuje obsah produktu tabulky databáze AdventureWorksLT.  
  
    -   TableAdapter s názvem `ProductTableAdapter`. Tato TableAdapter lze číst a zapisovat data v `AdventureWorksLTDataSet`. Další informace najdete v tématu [TableAdapter – přehled](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
     Obě tyto objekty použijete později v tomto návodu.  
  
9. V **Průzkumníku řešení**, klikněte pravým tlačítkem na **AdventureWorksDataSet** a klikněte na tlačítko **sestavení**.  
  
     Ověřte, že sestavení projektu bez chyb.  
  
## <a name="create-an-excel-workbook-project"></a>Vytvoření projektu sešitu aplikace Excel  
 Vytvoření projektu sešitu aplikace Excel pro rozhraní k datům. Dále v tomto návodu vytvoříte <xref:Microsoft.Office.Tools.Excel.ListObject> , zobrazí data a přidáte instanci datové sady do mezipaměti data v sešitu.  
  
### <a name="to-create-the-excel-workbook-project"></a>Vytvoření projektu sešitu aplikace Excel  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksDataSet** řešení, přejděte na příkaz **přidat**a potom klikněte na **nový projekt**.  
  
2.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office**.  
  
3.  V části sada rozšířeného **Office** uzlu, vyberte **2010** uzlu.  
  
4.  V seznamu šablon projektu vyberte projekt sešitu aplikace Excel.  
  
5.  V **název** zadejte **AdventureWorksReport**. Neměňte umístění.  
  
6.  Click **OK**.  
  
     **Visual Studio Tools for Office – Průvodce projektem** otevře.  
  
7.  Ujistěte se, že **vytvoříte nový textový dokument** je vybrána a klikněte na tlačítko **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře se **AdventureWorksReport** sešitu v návrháři a přidá **AdventureWorksReport** projektu do **Průzkumníku řešení**.  
  
## <a name="add-the-dataset-to-data-sources-in-the-excel-workbook-project"></a>Přidejte datovou sadu do zdroje dat v projektu sešitu aplikace Excel  
 Než budete moci zobrazit datovou sadu v sešitu aplikace Excel, je nejprve nutno přidat datovou sadu ke zdrojům dat v projektu sešitu aplikace Excel.  
  
### <a name="to-add-the-dataset-to-the-data-sources-in-the-excel-workbook-project"></a>Chcete-li přidat datovou sadu zdrojů dat v projektu sešitu aplikace Excel  
  
1.  V **Průzkumníku řešení**, dvakrát klikněte na **Sheet1.cs** nebo **Sheet1.vb** pod **AdventureWorksReport** projektu.  
  
     Otevře se sešit v návrháři.  
  
2.  Na **Data** nabídky, klikněte na tlačítko **přidat nový zdroj dat**.  
  
     **Průvodce konfigurací zdroje dat** otevře.  
  
3.  Klikněte na tlačítko **objekt**a potom klikněte na **Další**.  
  
4.  V **vyberte objekt chcete vytvořit vazbu k** klikněte na tlačítko **přidat odkaz na**.  
  
5.  Na **projekty** , klikněte na **AdventureWorksDataSet** a pak klikněte na **OK**.  
  
6.  V části **AdventureWorksDataSet** obor názvů **AdventureWorksDataSet** sestavení, klikněte na tlačítko **AdventureWorksLTDataSet** a pak klikněte na tlačítko **dokončit** .  
  
     **Zdroje dat** otevře okno a **AdventureWorksLTDataSet** je přidán do seznamu datových zdrojů.  
  
## <a name="create-a-listobject-that-is-bound-to-an-instance-of-the-dataset"></a>Vytvoření ListObject, který je vázaný na instanci datové sady  
 Chcete-li zobrazit datovou sadu v sešitu, vytvořte <xref:Microsoft.Office.Tools.Excel.ListObject> která je vázaná na instanci datovou sadu. Další informace o připojení ovládacích prvků k datům najdete v tématu [vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
### <a name="to-create-a-listobject-that-is-bound-to-an-instance-of-the-dataset"></a>Chcete-li vytvořit ListObject, který je vázaný na instanci datové sady  
  
1.  V **zdroje dat** okno, rozbalte **AdventureWorksLTDataSet** pod uzlem **AdventureWorksDataSet**.  
  
2.  Vyberte **produktu** uzel, klikněte na šipku rozevíracího seznamu, který se zobrazí a vyberte **ListObject** v rozevíracím seznamu.  
  
     Pokud na šipku rozevíracího seznamu nezobrazí, zkontrolujte, zda sešit otevřít v návrháři.  
  
3.  Přetáhněte **produktu** tabulky do buňky A1.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek s názvem `productListObject` je vytvořen v listu, od buňky A1. Současně, objekt datovou sadu s názvem `adventureWorksLTDataSet` a <xref:System.Windows.Forms.BindingSource> s názvem `productBindingSource` jsou přidány do projektu. <xref:Microsoft.Office.Tools.Excel.ListObject> Je vázána <xref:System.Windows.Forms.BindingSource>, který je pak vázaná na objekt datové sady.  
  
## <a name="add-the-dataset-to-the-data-cache"></a>Přidání datové sady do mezipaměti dat  
 Chcete-li kód mimo projekt sešitu aplikace Excel, který má přístup k datové sadě v sešitu, je nutné přidat datovou sadu do mezipaměti data. Další informace o mezipaměti dat najdete v tématu [mezipaměti data v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md) a [ukládat data do mezipaměti](../vsto/caching-data.md).  
  
### <a name="to-add-the-dataset-to-the-data-cache"></a>Chcete-li přidat datové sady do mezipaměti dat  
  
1.  V návrháři, klikněte na tlačítko **adventureWorksLTDataSet**.  
  
2.  V **vlastnosti** nastavte **modifikátory** vlastnost **veřejné**.  
  
3.  Nastavte **CacheInDocument** vlastnost **True**.  
  
## <a name="initialize-the-dataset-in-the-workbook"></a>Inicializace datovou sadu v sešitu  
 Chcete-li načíst data z datové sady v mezipaměti pomocí konzolové aplikace, musí nejprve naplnit daty datové sady v mezipaměti.  
  
### <a name="to-initialize-the-dataset-in-the-workbook"></a>K chybě při inicializaci datovou sadu v sešitu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **Sheet1.cs** nebo **Sheet1.vb** souboru a klikněte na tlačítko **kód zobrazení**.  
  
2.  Nahraďte `Sheet1_Startup` obslužné rutiny události s následujícím kódem. Tento kód používá instanci `ProductTableAdapter` třídu, která je definována v **AdventureWorksDataSet** projektu k vyplnění datové sady v mezipaměti s daty, pokud je aktuálně prázdná.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#8](../vsto/codesnippet/CSharp/AdventureWorksDataSet/AdventureWorksReport/Sheet1.cs#8)]
     [!code-vb[Trin_CachedDataWalkthroughs#8](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/AdventureWorksReport/Sheet1.vb#8)]  
  
## <a name="checkpoint"></a>Kontrolní bod  
 Sestavte a spusťte projekt sešitu aplikace Excel, který má zajistit, aby zkompiluje a spustí bez chyb. Tato operace také vyplní celé datové sady v mezipaměti a uloží data v sešitu.  
  
### <a name="to-build-and-run-the-project"></a>Sestavení a spuštění projektu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksReport** projektu, zvolte **ladění**a potom klikněte na **spustit novou instanci**.  
  
     Sestavení projektu a otevře se sešit v aplikaci Excel. Ověřte následující:  
  
    -   <xref:Microsoft.Office.Tools.Excel.ListObject> Doplní s daty.  
  
    -   Hodnota v **ListPrice** sloupec pro první řádek <xref:Microsoft.Office.Tools.Excel.ListObject> je 1431.5. Dále v tomto návodu budete používat aplikace konzoly změnit hodnoty v **ListPrice** sloupce.  
  
2.  Sešit uložte. Neměňte název souboru nebo umístění do sešitu.  
  
3.  Zavření Excelu.  
  
## <a name="create-a-console-application-project"></a>Vytvoření projektu konzolové aplikace  
 Vytvoření projektu konzolové aplikace použitý pro změny dat v datové sady v mezipaměti v sešitu.  
  
### <a name="to-create-the-console-application-project"></a>Chcete-li vytvořit projekt konzolové aplikace  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksDataSet** řešení, přejděte na příkaz **přidat**a potom klikněte na **nový projekt**.  
  
2.  V **typy projektů** podokně rozbalte **Visual C#** nebo **jazyka Visual Basic**a potom klikněte na **Windows**.  
  
3.  V **šablony** podokně, vyberte **konzolové aplikace**.  
  
4.  V **název** zadejte **DataWriter**. Neměňte umístění.  
  
5.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **DataWriter** projektu do **Průzkumníku řešení** a otevře **Program.cs** nebo **Module1.vb** souboru kódu.  
  
## <a name="change-data-in-the-cached-dataset-by-using-the-console-application"></a>Změna dat v datové sady v mezipaměti pomocí konzolové aplikace  
 Použití <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> – třída v konzolové aplikaci k načtení dat do místní `AdventureWorksLTDataSet` objektu, úpravě tato data a ukládat ho zpátky do datové sady v mezipaměti.  
  
### <a name="to-change-data-in-the-cached-dataset"></a>Chcete-li změnit data v datové sady v mezipaměti  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DataWriter** projektu a klikněte na tlačítko **přidat odkaz na**.  
  
2.  Na **.NET** vyberte **Microsoft.VisualStudio.Tools.Applications**.  
  
3.  Click **OK**.  
  
4.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DataWriter** projektu a klikněte na tlačítko **přidat odkaz na**.  
  
5.  Na **projekty** vyberte **AdventureWorksDataSet**a klikněte na tlačítko **OK**.  
  
6.  Otevřete *Program.cs* nebo *Module1.vb* souboru v editoru kódu.  
  
7.  Přidejte následující **pomocí** (pro jazyk C#) nebo **importy** (pro Visual Basic) příkaz na začátek souboru kódu.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#1)]
     [!code-vb[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#1)]  
  
8.  Přidejte následující kód, který `Main` metoda. Tento kód deklaruje následující objekty:  
  
    -   Instance `AdventureWorksLTDataSet` typ, který je definován v **AdventureWorksDataSet** projektu.  
  
    -   Cesta k sešitu AdventureWorksReport ve složce sestavení **AdventureWorksReport** projektu.  
  
    -   A <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> objekt, který chcete použít pro přístup do mezipaměti data v sešitu.  
  
        > [!NOTE]  
        >  Následující kód předpokládá, že používáte sešit, který má *XLSX* příponu souboru. Pokud sešit v projektu má jinou příponu souboru, změňte cestu podle potřeby.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#6](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#6)]
     [!code-vb[Trin_CachedDataWalkthroughs#6](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#6)]  
  
9. Přidejte následující kód, který `Main` metoda po kódu přidaném v předchozím kroku. Tento kód provede následující:  
  
    -   Použije <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> vlastnost <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy pro přístup k datové sady v mezipaměti v sešitu.  
  
    -   Čte data z datové sady v mezipaměti do místní datové sady.  
  
    -   Změní `ListPrice` hodnota jednotlivých produktů v tabulce produktu datové sady.  
  
    -   Uloží změny provedené v sešitu datové sady v mezipaměti.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#7](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#7)]
     [!code-vb[Trin_CachedDataWalkthroughs#7](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#7)]  
  
10. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DataWriter** projektu, přejděte na **ladění**a potom klikněte na **spustit novou instanci**.  
  
     Konzolové aplikace zobrazí zprávy při čtení datové sady v mezipaměti do místní datové sady, upraví ceny produktů v místní datové sady a uloží nové hodnoty do datové sady v mezipaměti. Stiskněte klávesu **Enter** aplikace se zavře.  
  
## <a name="test-the-workbook"></a>Testování sešitu  
 Při otevření sešitu, <xref:Microsoft.Office.Tools.Excel.ListObject> teď zobrazuje změny provedené `ListPrice` sloupec dat v datové sady v mezipaměti.  
  
### <a name="to-test-the-workbook"></a>K testování sešitu  
  
1.  Zavřete sešit AdventureWorksReport v návrháři Visual Studio, pokud je stále otevřen.  
  
2.  Otevřete sešit AdventureWorksReport, který je ve složce sestavení **AdventureWorksReport** projektu. Ve výchozím nastavení složku sestavení je v jednom z následujících umístění:  
  
    -   *%USERPROFILE%\My Documents\AdventureWorksReport\bin\Debug* (pro Windows XP a starší)  
  
    -   *%USERPROFILE%\Documents\AdventureWorksReport\bin\Debug* (pro systém Windows Vista)  
  
3.  Ověřte, zda je hodnota v **ListPrice** sloupec pro první řádek <xref:Microsoft.Office.Tools.Excel.ListObject> je nyní 1574.65.  
  
4.  Zavřete.  
  
## <a name="see-also"></a>Viz také:  
 [Návod: Vložení dat do sešitu na serveru](../vsto/walkthrough-inserting-data-into-a-workbook-on-a-server.md)   
 [Připojte se k datům v aplikacích Windows Forms](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)  
  
  