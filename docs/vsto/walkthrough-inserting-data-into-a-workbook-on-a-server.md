---
title: 'Návod: Vložení dat do sešitu na serveru | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- datasets [Office development in Visual Studio], accessing on server
- server-side data access [Office development in Visual Studio]
- data [Office development in Visual Studio], accessing on server
- documents [Office development in Visual Studio], server-side data access
- workbooks [Office development in Visual Studio], inserting data
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7257094aa0fb29c1b03878f5ac39c3d4f4864022
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-inserting-data-into-a-workbook-on-a-server"></a>Návod: Vložení dat do sešitu na serveru
  Tento návod ukazuje, jak pro vložení dat do datovou sadu, která se uloží do mezipaměti v sešitu aplikace Microsoft Office Excel bez spuštění aplikace Excel pomocí <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Definování datovou sadu, která obsahuje data z databáze AdventureWorksLT.  
  
-   Vytváření instancí datové sady v projektu sešitu aplikace Excel a projekt konzolové aplikace.  
  
-   Vytváření <xref:Microsoft.Office.Tools.Excel.ListObject> , je vázána na datovou sadu v sešitu.  
  
-   Přidání datovou sadu v sešitu do datové mezipaměti.  
  
-   Vložení dat do datové sady v mezipaměti spuštěním kódu v konzolové aplikaci, bez spuštění aplikace Excel.  
  
 I když tento návod předpokládá, že používáte kód ve svém vývojovém počítači, kód ukázán podle tohoto návodu jde použít na serveru, který nemá nainstalovanou aplikaci Excel.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Přístup k spuštěnou instanci Microsoft SQL Server nebo Microsoft SQL Server Express, která obsahuje ukázkové databáze AdventureWorksLT k němu připojen. Si můžete stáhnout z databáze AdventureWorksLT [webu CodePlex](http://go.microsoft.com/fwlink/?linkid=87843). Další informace o připojení databáze najdete v následujících tématech:  
  
    -   Připojení databáze pomocí SQL Server Management Studio nebo SQL Server Management Studio Express, najdete v části [postupy: připojení databáze (SQL Server Management Studio)](http://msdn.microsoft.com/en-us/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa).  
  
    -   Připojení databáze pomocí příkazového řádku, najdete v části [postupy: připojení souboru databáze k systému SQL Server Express](http://msdn.microsoft.com/en-us/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68).  
  
## <a name="creating-a-class-library-project-that-defines-a-dataset"></a>Vytvoření projektu knihovny tříd, který definuje datové sady  
 Pokud chcete používat se stejnou datovou v projektu sešitu aplikace Excel a konzolovou aplikaci, je nutné zadat datovou sadu v samostatném sestavení, který je odkazován obě tyto projekty. V tomto návodu definování datové sady v projektu knihovny tříd.  
  
#### <a name="to-create-the-class-library-project"></a>Vytvoření projektu knihovny tříd  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom klikněte na **Windows**.  
  
4.  V seznamu šablon projektu, vyberte **knihovny tříd**.  
  
5.  V **název** zadejte **AdventureWorksDataSet**.  
  
6.  Klikněte na tlačítko **Procházet**, přejděte do %UserProfile%\My dokumenty (pro Windows XP a starší) nebo složku %UserProfile%\Documents (pro systém Windows Vista) a pak klikněte na tlačítko **vyberte složku**.  
  
7.  V **nový projekt** dialogové okno pole, ujistěte se, že **vytvořit adresář pro řešení** není zaškrtnuté políčko.  
  
8.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **AdventureWorksDataSet** projektu do **Průzkumníku řešení** a otevře **Class1.cs** nebo **Class1.vb** souboru kódu.  
  
9. V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Class1.cs** nebo **Class1.vb**a potom klikněte na **odstranit**. Tento soubor není nutné v tomto návodu.  
  
## <a name="defining-a-dataset-in-the-class-library-project"></a>Definování datové sady v projektu knihovny tříd  
 Definujte typové datové sady, který obsahuje data z databáze AdventureWorksLT pro SQL Server 2005. Dále v tomto návodu budete tuto datovou sadu odkazovat z projektu sešitu aplikace Excel a projekt konzolové aplikace.  
  
 Je datová sada *typové datové sady* představující data v tabulce produktu databáze AdventureWorksLT. Další informace o typové datové sady, najdete v části [datové sady nástrojů v sadě Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
#### <a name="to-define-a-typed-dataset-in-the-class-library-project"></a>Chcete-li definovat typové datové sady v projektu knihovny tříd  
  
1.  V **Průzkumníku řešení**, klikněte **AdventureWorksDataSet** projektu.  
  
2.  Pokud **zdroje dat** okno není viditelný, zobrazit, na řádku nabídky, výběr **zobrazení**, **ostatní okna**, **zdroje dat**.  
  
3.  Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
4.  Klikněte na tlačítko **databáze**a potom klikněte na **Další**.  
  
5.  Pokud máte existující připojení k databázi AdventureWorksLT, vyberte toto připojení a klikněte na **Další**.  
  
     Jinak, klikněte na tlačítko **nové připojení**a použít **přidat připojení** dialogové okno vytvořit nové připojení. Další informace najdete v tématu [postupy: připojování k datům v databázi](../vsto/walkthrough-inserting-data-into-a-workbook-on-a-server.md).  
  
6.  V **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.  
  
7.  V **zvolte si databázové objekty** rozbalte **tabulky** a vyberte **produkt (SalesLT)**.  
  
8.  Klikněte na tlačítko **Dokončit**.  
  
     Soubor AdventureWorksLTDataSet.xsd je přidán do **AdventureWorksDataSet** projektu. Tento soubor definuje následující položky:  
  
    -   Typové datové sady s názvem `AdventureWorksLTDataSet`. Tato datová sada představuje obsah produktu tabulky databáze AdventureWorksLT.  
  
    -   TableAdapter s názvem `ProductTableAdapter`. Tato TableAdapter lze číst a zapisovat data v `AdventureWorksLTDataSet`. Další informace najdete v tématu [TableAdapter – přehled](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
     Obě tyto objekty použijete později v tomto návodu.  
  
9. V **Průzkumníku řešení**, klikněte pravým tlačítkem na **AdventureWorksDataSet** a klikněte na tlačítko **sestavení**.  
  
     Ověřte, že sestavení projektu bez chyb.  
  
## <a name="creating-an-excel-workbook-project"></a>Vytvoření projektu sešitu aplikace Excel  
 Vytvoření projektu sešitu aplikace Excel pro rozhraní k datům. Dále v tomto návodu vytvoříte <xref:Microsoft.Office.Tools.Excel.ListObject> , zobrazí data a přidáte instanci datové sady do mezipaměti data v sešitu.  
  
#### <a name="to-create-the-excel-workbook-project"></a>Vytvoření projektu sešitu aplikace Excel  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksDataSet** řešení, přejděte na příkaz **přidat**a potom klikněte na **nový projekt**.  
  
2.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
3.  V části sada rozšířeného **Office/SharePoint** uzlu, vyberte **Office Add in** uzlu.  
  
4.  V seznamu šablon projektu, vyberte **sešitu aplikace Excel 2010** nebo **sešitu aplikace Excel 2013** projektu.  
  
5.  V **název** zadejte **AdventureWorksReport**. Neměňte umístění.  
  
6.  Click **OK**.  
  
     **Visual Studio Tools for Office – Průvodce projektem** otevře.  
  
7.  Ujistěte se, že **vytvoříte nový textový dokument** je vybrána a klikněte na tlačítko **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře se **AdventureWorksReport** sešitu v návrháři a přidá **AdventureWorksReport** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-the-dataset-to-data-sources-in-the-excel-workbook-project"></a>Přidání datovou sadu do zdroje dat v projektu sešitu aplikace Excel  
 Než budete moci zobrazit datovou sadu v sešitu aplikace Excel, je nejprve nutno přidat datovou sadu ke zdrojům dat v projektu sešitu aplikace Excel.  
  
#### <a name="to-add-the-dataset-to-the-data-sources-in-the-excel-workbook-project"></a>Chcete-li přidat datovou sadu zdrojů dat v projektu sešitu aplikace Excel  
  
1.  V **Průzkumníku řešení**, dvakrát klikněte na **Sheet1.cs** nebo **Sheet1.vb** pod **AdventureWorksReport** projektu.  
  
     Otevře se sešit v návrháři.  
  
2.  Na **Data** nabídky, klikněte na tlačítko **přidat nový zdroj dat**.  
  
     **Průvodce konfigurací zdroje dat** otevře.  
  
3.  Klikněte na tlačítko **objekt**a potom klikněte na **Další**.  
  
4.  V **vyberte objekt chcete vytvořit vazbu** stránky, klikněte na **přidat odkaz na**.  
  
5.  Na **projekty** , klikněte na **AdventureWorksDataSet** a pak klikněte na **OK**.  
  
6.  V části **AdventureWorksDataSet** obor názvů **AdventureWorksDataSet** sestavení, klikněte na tlačítko **AdventureWorksLTDataSet** a pak klikněte na tlačítko **dokončit** .  
  
     **Zdroje dat** otevře okno a **AdventureWorksLTDataSet** je přidán do seznamu datových zdrojů.  
  
## <a name="creating-a-listobject-that-is-bound-to-an-instance-of-the-dataset"></a>Vytvoření ListObject, která je vázána na instanci datové sady  
 Chcete-li zobrazit datovou sadu v sešitu, vytvořte <xref:Microsoft.Office.Tools.Excel.ListObject> která je vázaná na instanci datovou sadu. Další informace o připojení ovládacích prvků k datům najdete v tématu [vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
#### <a name="to-create-a-listobject-that-is-bound-to-an-instance-of-the-dataset"></a>Chcete-li vytvořit ListObject, který je vázaný na instanci datové sady  
  
1.  V **zdroje dat** okno, rozbalte **AdventureWorksLTDataSet** pod uzlem **AdventureWorksDataSet**.  
  
2.  Vyberte **produktu** uzel, klikněte na šipku rozevíracího seznamu, který se zobrazí a vyberte **ListObject** v rozevíracím seznamu.  
  
     Pokud na šipku rozevíracího seznamu nezobrazí, zkontrolujte, zda sešit otevřít v návrháři.  
  
3.  Přetáhněte **produktu** tabulky do buňky A1.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek s názvem `productListObject` je vytvořen v listu, od buňky A1. Současně, objekt datovou sadu s názvem `adventureWorksLTDataSet` a <xref:System.Windows.Forms.BindingSource> s názvem `productBindingSource` jsou přidány do projektu. <xref:Microsoft.Office.Tools.Excel.ListObject> Je vázána <xref:System.Windows.Forms.BindingSource>, který je pak vázaná na objekt datové sady.  
  
## <a name="adding-the-dataset-to-the-data-cache"></a>Přidávání datové sady do mezipaměti dat  
 Chcete-li kód mimo projekt sešitu aplikace Excel, který má přístup k datové sadě v sešitu, je nutné přidat datovou sadu do mezipaměti data. Další informace o mezipaměti dat najdete v tématu [Data do mezipaměti v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md) a [ukládání dat do mezipaměti](../vsto/caching-data.md).  
  
#### <a name="to-add-the-dataset-to-the-data-cache"></a>Chcete-li přidat datové sady do mezipaměti dat  
  
1.  V návrháři, klikněte na tlačítko **adventureWorksLTDataSet**.  
  
2.  V **vlastnosti** nastavte **modifikátory** vlastnost **veřejné**.  
  
3.  Nastavte **CacheInDocument** vlastnost **True**.  
  
## <a name="checkpoint"></a>Kontrolní bod  
 Sestavte a spusťte projekt sešitu aplikace Excel, který má zajistit, aby zkompiluje a spustí bez chyb.  
  
#### <a name="to-build-and-run-the-project"></a>Sestavení a spuštění projektu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksReport** projektu, zvolte **ladění**a potom klikněte na **spustit novou instanci**.  
  
     Sestavení projektu a otevře se sešit v aplikaci Excel. <xref:Microsoft.Office.Tools.Excel.ListObject> v **Sheet1** je prázdná, protože `adventureWorksLTDataSet` objektu v datové mezipaměti ještě neobsahuje žádná data. V další části, bude používat k naplnění konzolové aplikace `adventureWorksLTDataSet` objektu s daty.  
  
2.  Zavření Excelu. Neukládat změny.  
  
## <a name="creating-a-console-application-project"></a>Vytvoření projektu konzolové aplikace  
 Vytvoření projektu konzolové aplikace sloužící k vkládání dat v datové sady v mezipaměti v sešitu.  
  
#### <a name="to-create-the-console-application-project"></a>Chcete-li vytvořit projekt konzolové aplikace  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **AdventureWorksDataSet** řešení, přejděte na příkaz **přidat**a potom klikněte na **nový projekt**.  
  
2.  V **typy projektů** podokně rozbalte **Visual C#** nebo **jazyka Visual Basic**a potom klikněte na **Windows**.  
  
3.  V **šablony** podokně, vyberte **konzolové aplikace**.  
  
4.  V **název** zadejte **DataWriter**. Neměňte umístění.  
  
5.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Přidá **DataWriter** projektu do **Průzkumníku řešení** a otevře **Program.cs** nebo **Module1.vb** souboru kódu.  
  
## <a name="adding-data-to-the-cached-dataset-by-using-the-console-application"></a>Přidání dat do datové sady v mezipaměti pomocí konzolové aplikace  
 Použití <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> – třída v konzolové aplikaci k naplnění datové sady v mezipaměti v sešitu s daty.  
  
#### <a name="to-add-data-to-the-cached-dataset"></a>Přidání dat do datové sady v mezipaměti  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DataWriter** projektu a klikněte na tlačítko **přidat odkaz na**.  
  
2.  Na **.NET** vyberte **Microsoft.VisualStudio.Tools.Applications.ServerDocument**.  
  
3.  Click **OK**.  
  
4.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DataWriter** projektu a klikněte na tlačítko **přidat odkaz na**.  
  
5.  Na **projekty** vyberte **AdventureWorksDataSet**a klikněte na tlačítko **OK**.  
  
6.  Otevřete soubor Program.cs nebo Module1.vb v editoru kódu.  
  
7.  Přidejte následující **pomocí** (pro jazyk C#) nebo **importy** (pro Visual Basic) příkaz na začátek souboru kódu.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#1)]
     [!code-vb[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#1)]  
  
8.  Přidejte následující kód, který `Main` metoda. Tento kód deklaruje následující objekty:  
  
    -   Instance `AdventureWorksLTDataSet` a `ProductTableAdapter` typy, které jsou definovány v **AdventureWorksDataSet** projektu.  
  
    -   Cesta k sešitu AdventureWorksReport ve složce sestavení **AdventureWorksReport** projektu.  
  
    -   A <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> objekt, který chcete použít pro přístup do mezipaměti data v sešitu.  
  
        > [!NOTE]  
        >  Následující kód předpokládá, že používáte sešit, který má příponu souboru XLSX. Pokud sešit v projektu má jinou příponu souboru, změňte cestu podle potřeby.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#3](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#3)]
     [!code-vb[Trin_CachedDataWalkthroughs#3](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#3)]  
  
9. Přidejte následující kód, který `Main` metoda po kódu přidaném v předchozím kroku. Tento kód provede následující:  
  
    -   Typové datové sady objektu zaplňování pomocí adaptéru tabulky.  
  
    -   Použije <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> vlastnost <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy pro přístup k datové sady v mezipaměti v sešitu.  
  
    -   Použije <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> metoda k naplnění datové sady v mezipaměti s daty z místní typové datové sady.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#4](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#4)]
     [!code-vb[Trin_CachedDataWalkthroughs#4](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#4)]  
  
10. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **DataWriter** projektu, přejděte na **ladění**a potom klikněte na **spustit novou instanci**.  
  
     Sestavení projektu a konzolové aplikace zobrazí několik stavové zprávy, když místní datové sady, naplní a když aplikace uloží data do datové sady v mezipaměti v sešitu. Stisknutím klávesy ENTER zavřete aplikaci.  
  
## <a name="testing-the-workbook"></a>Testování sešitu  
 Při otevření sešitu, <xref:Microsoft.Office.Tools.Excel.ListObject> teď zobrazuje data, která byla přidána do datové sady v mezipaměti pomocí konzolové aplikace.  
  
#### <a name="to-test-the-workbook"></a>K testování sešitu  
  
1.  Zavřete sešit AdventureWorksReport v návrháři Visual Studio, pokud je stále otevřen.  
  
2.  V Průzkumníku souborů, otevřete sešit AdventureWorksReport, který je ve složce sestavení **AdventureWorksReport** projektu. Ve výchozím nastavení složku sestavení je v jednom z následujících umístění:  
  
    -   %USERPROFILE%\My Documents\AdventureWorksReport\bin\Debug (pro Windows XP a starší)  
  
    -   %USERPROFILE%\Documents\AdventureWorksReport\bin\Debug (pro systém Windows Vista)  
  
3.  Ověřte, zda <xref:Microsoft.Office.Tools.Excel.ListObject> naplněný daty po otevření sešitu.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o práci s data uložená v mezipaměti z těchto témat:  
  
-   Změna dat v datové sady v mezipaměti bez spuštění aplikace Excel. Další informace najdete v tématu [návod: Změna dat do mezipaměti v sešitu na serveru](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Změna Data uložená v mezipaměti v sešitu na serveru](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md)   
 [Připojování k datům v aplikacích Windows Forms](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)  
  
  