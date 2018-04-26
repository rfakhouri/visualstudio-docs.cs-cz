---
title: 'Návod: Vytvoření víceúrovňové datové aplikace'
ms.date: 09/08/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, creating
- n-tier applications, walkthroughs
ms.assetid: d15e4d31-2839-48d9-9e0e-2e73404d82a2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 35733a737f10fccab7d9fd6cab350478182b2259
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-creating-an-n-tier-data-application"></a>Návod: Vytvoření víceúrovňové datové aplikace
*N-vrstvá* data aplikace jsou aplikace, které přístup k datům a jsou rozdělené do několika logických vrstev, nebo *vrstev*. Rozdělit součásti aplikace do diskrétní úrovní zvyšuje udržovatelnosti a škálovatelnost aplikace. Dělá to tím, že umožňuje snazší přijetí nové technologie, které mohou být použity k jedné vrstvě, aniž by bylo potřeba změnit návrh celého řešení. N-vrstvá architektura obsahuje prezentační vrstvy, střední vrstvy, a datové vrstvy. Střední vrstva obvykle zahrnuje vrstva přístupu k datům, vrstvy obchodní logiky a sdílené komponenty, například ověřování a ověřování. Datová vrstva obsahuje relační databáze. Vícevrstvé aplikace obvykle uložit citlivé informace vrstva přístupu k datům ze střední vrstvě udržovat izolace koncovým uživatelům, kteří přistupují k prezentační vrstvy. Další informace najdete v tématu [vícevrstvé datové aplikace přehled](../data-tools/n-tier-data-applications-overview.md).

Jedním ze způsobů k oddělení různých vrstev ve vícevrstvé aplikace je vytvoření diskrétní projekty pro každou vrstvu, kterou chcete zahrnout do vaší aplikace. Typové datové sady obsahují `DataSet Project` vlastnost který určuje, které projekty generované datové sady a `TableAdapter` kód by měl přejděte do.

Tento návod ukazuje, jak jednotlivé datové sady a `TableAdapter` kód do projektů knihovny tříd diskrétní pomocí **návrháře Dataset**. Po oddělíte datovou sadu a TableAdapter kódu, vytvoříte [služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) služby provést volání do úroveň přístupu data. Nakonec se vytvoří aplikace Windows Forms jako prezentační vrstvy. Tato úroveň přistupuje k datům ze služby data.

Během tohoto návodu budete provádět následující kroky:

-   Vytvořte nové řešení n vrstvá, která bude obsahovat více projektů.

-   Přidejte dva projektů knihovny tříd do vícevrstvé řešení.

-   Vytvoření typové datové sady pomocí **Průvodce konfigurací zdroje dat**.

-   Oddělení vygenerovaného [TableAdapters](create-and-configure-tableadapters.md) a kód datové sady do diskrétní projektů.

-   Vytvoření služby Windows Communication Foundation (WCF) provést volání do úroveň přístupu data.

-   Vytvoření funkce ve službě k načtení dat z úrovně přístupu data.

-   Vytvořte aplikaci Windows Forms sloužit jako prezentační vrstvy.

-   Ovládací prvky Windows Forms, které jsou vázány na zdroj dat vytvořte.

-   Napište kód pro naplnění dat tabulky.

![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") video verzi tohoto tématu naleznete v části [Video postupy: vytvoření datové aplikace s N-vrstvá](http://go.microsoft.com/fwlink/?LinkId=115188).

## <a name="prerequisites"></a>Požadavky
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.

1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [SQL Server Express stránky pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **vývoj aplikací .NET** zatížení, nebo jako jednotlivých součástí.

2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .

       Otevře se okno editoru dotazů.

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.

## <a name="creating-the-n-tier-solution-and-class-library-to-hold-the-dataset-dataentitytier"></a>Vytvoření N-vrstvého řešení a knihovny tříd pro objekt Dataset (DataEntityTier)
 Prvním krokem tohoto návodu je vytvoření řešení a dvou projektů knihovny tříd. První třídy knihovny bude obsahovat datovou sadu (vygenerovaného typovaných DataSet – třída a DataTables, který bude obsahovat data aplikace). Tento projekt se používá jako datová vrstva entity aplikace a se obvykle nachází ve střední vrstvě. Datasetis slouží k vytvoření počátečních datových sad a automaticky oddělení kód do knihovny dvou tříd.

> [!NOTE]
>  Ujistěte se, zda jste název projektu a řešení správně před kliknutím na **OK**. Díky tomu bude bylo snazší pro vás k dokončení tohoto postupu.

#### <a name="to-create-the-n-tier-solution-and-dataentitytier-class-library"></a>Vytvoření n-vrstvého řešení a knihovny tříd DataEntityTier

1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .

2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.

3. V prostředním podokně, vyberte **knihovny tříd** typ projektu.

4. Název projektu **DataEntityTier**.

5. Název řešení **NTierWalkthrough**a potom zvolte **OK**.

     Řešení s NTierWalkthrough obsahující projekt DataEntityTier je vytvořen a přidán do **Průzkumníku řešení**.

## <a name="creating-the-class-library-to-hold-the-tableadapters-dataaccesstier"></a>Vytvoření knihovny tříd pro objekty TableAdapter (DataAccessTier)
 Dalším krokem po vytvoření projektu DataEntityTier je vytvoření jiného projektu knihovny tříd. Tento projekt bude obsahovat vygenerovaného `TableAdapter`s a je volána *úroveň přístupu dat* aplikace. Úroveň přístupu dat obsahuje informace, které je požadované pro připojení k databázi a se obvykle nachází ve střední vrstvě.

#### <a name="to-create-a-separate-class-library-for-the-tableadapters"></a>Vytvoření samostatné třídy knihovny pro TableAdapters

1.  Klikněte pravým tlačítkem na řešení v Průzkumníku řešení a zvolte **přidat**, **nový projekt...** .

2.  V **nový projekt** dialogové okno, v prostředním podokně, vyberte **knihovny tříd**.

3.  Název projektu **DataAccessTier** a zvolte **OK**.

     Projekt DataAccessTier je vytvořen a přidán do NTierWalkthrough řešení.

## <a name="creating-the-dataset"></a>Vytvoření datové sady
 Dalším krokem je vytvoření typové datové sady. Typové datové sady jsou vytvořeny pomocí obou třídě datové sady (včetně třídy DataTables) a `TableAdapter` třídy v jednom projektu. (Všechny třídy jsou generovány, do jediného souboru.) Když oddělíte datovou sadu a `TableAdapter`s do různých projektů, je datová sada třídu, která je přesunut do jiného projektu, a `TableAdapter` třídy v původním projektu. Proto vytvořit datová sada v projektu, který bude obsahovat nakonec `TableAdapter`s (DataAccessTier projekt). Datová sada se vytvoří pomocí **Průvodce konfigurací zdroje dat**.

> [!NOTE]
>  Musíte mít přístup k ukázková databáze Northwind k vytvoření připojení. Informace o tom, jak nastavit ukázková databáze Northwind najdete v tématu [postupy: Instalace ukázkové databáze](../data-tools/installing-database-systems-tools-and-samples.md).

#### <a name="to-create-the-dataset"></a>Vytvoření datové sady

1.  Vyberte DataAccessTier v **Průzkumníku řešení**.

2.  Na **Data** nabídce vyberte možnost **zobrazit zdroje dat**.

3.  V **zdroje dat** vyberte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.

4.  Na **zvolte typ zdroje dat** vyberte **databáze** a pak vyberte **Další**.

5.  Na **vybrat datové připojení** proveďte některý z následujících akcí:

     Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.

     -nebo-

     Vyberte **nové připojení** otevřete **přidat připojení** dialogové okno.

6.  Pokud databáze vyžaduje heslo, vyberte možnost obsahují citlivá data a potom vyberte **Další**.

    > [!NOTE]
    >  Pokud jste vybrali místního databázového souboru (namísto připojení k systému SQL Server) může být žádost, pokud chcete soubor přidat do projektu. Zvolte **Ano** přidat databázový soubor do projektu.

7.  Vyberte **Další** na **uložit připojovací řetězec do konfiguračního souboru aplikace** stránky.

8.  Rozbalte **tabulky** uzlu **zvolte si databázové objekty** stránky.

9.  Zaškrtněte políčka u **zákazníci** a **objednávky** tabulky a potom vyberte **Dokončit**.

     NorthwindDataSet se přidá do projektu DataAccessTier a zobrazí se v **zdroje dat** okno.

## <a name="separating-the-tableadapters-from-the-dataset"></a>Oddělení objektů TableAdapter od objektu DataSet
 Po vytvoření datové sady, nezávislá na generovaného dataset – třída TableAdapters. To provedete nastavením **DataSet projekt** vlastnost na název projektu, do které chcete uložit oddělených na třídu datové sady.

#### <a name="to-separate-the-tableadapters-from-the-dataset"></a>Oddělení objektů TableAdapter od objektu DataSet

1.  Klikněte dvakrát na **NorthwindDataSet.xsd** v **Průzkumníku řešení** otevřete datovou sadu v **návrháře Dataset**.

2.  Vyberte na prázdnou oblast na návrháře.

3.  Vyhledejte **DataSet projekt** uzlu **vlastnosti** okno.

4.  V **DataSet projekt** seznamu, vyberte **DataEntityTier**.

5.  Na **sestavení** nabídce vyberte možnost **sestavit řešení**.

 Datové sady a TableAdapters jsou rozdělené do projektů knihovny dvou tříd. Projekt, který původně obsažené celou datovou sadu (DataAccessTier) teď obsahuje pouze TableAdapters. Projekt uvedených v **DataSet projekt** vlastnost (DataEntityTier) obsahuje typové datové sady: NorthwindDataSet.Dataset.Designer.vb (nebo NorthwindDataSet.Dataset.Designer.cs).

> [!NOTE]
>  Když oddělíte datových sad a TableAdapters (nastavením **DataSet projekt** vlastnost), nebude automaticky přesunout existující datovou sadu částečné třídy v projektu. Částečné třídy existující datovou sadu musí ručně přesunout do projektu datovou sadu.

## <a name="creating-a-new-service-application"></a>Vytvoření nové aplikace služby
Tento návod ukazuje, jak přístup úroveň přístupu dat pomocí služby WCF, takže umožňuje vytvořit novou aplikaci služby WCF.

#### <a name="to-create-a-new-wcf-service-application"></a>Vytvoření nové aplikace služby WCF

1.  Klikněte pravým tlačítkem na řešení v Průzkumníku řešení a zvolte **přidat**, **nový projekt...** .

2.  V **nový projekt** dialogové okno, v levém podokně vyberte **WCF**.  V prostředním podokně vyberte **knihovny služby WCF**.

3.  Název projektu **DataService** a vyberte **OK**.

     Projekt DataService je vytvořen a přidán do NTierWalkthrough řešení.

## <a name="creating-methods-in-the-data-access-tier-to-return-the-customers-and-orders-data"></a>Vytvoření metod, které vrací data zákazníků a objednávek, ve vrstvě přístupu k datům
 Služba data je volat dvě metody v datové vrstvě přístup: GetCustomers a GetOrders. Tyto metody vrátí tabulky zákazníků Northwind a objednávky. Vytvoření metody GetCustomers a GetOrders v DataAccessTier projektu.

#### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-customers-table"></a>Vytvoření metody, která vrací tabulku Customers, ve vrstvě přístupu k datům

1.  V **Průzkumníku**, dvakrát klikněte na NorthwindDataset.xsd otevřete datovou sadu.

2.  Klikněte pravým tlačítkem na CustomersTableAdapter a klikněte na tlačítko **přidat dotazu**.

3.  Na **zvolte typ příkazu** ponechte výchozí hodnotu **příkazy SQL pomocí** a klikněte na tlačítko **Další**.

4.  Na **vyberte typ dotazu** ponechte výchozí hodnotu **vyberte, které vrací řádky** a klikněte na tlačítko **Další**.

5.  Na **zadejte příkazu SQL SELECT** , ponechte výchozí dotaz a klikněte na tlačítko **Další**.

6.  Na **zvolte metody pro generování** zadejte **GetCustomers** pro **název metody** v **vrátit DataTable** části.

7.  Klikněte na tlačítko **Dokončit**.

#### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-orders-table"></a>Vytvoření metody, která vrací tabulku Orders, ve vrstvě přístupu k datům

1.  Klikněte pravým tlačítkem na OrdersTableAdapter a klikněte na tlačítko **přidat dotazu**.

2.  Na **zvolte typ příkazu** ponechte výchozí hodnotu **příkazy SQL pomocí** a klikněte na tlačítko **Další**.

3.  Na **vyberte typ dotazu** ponechte výchozí hodnotu **vyberte, které vrací řádky** a klikněte na tlačítko **Další**.

4.  Na **zadejte příkazu SQL SELECT** , ponechte výchozí dotaz a klikněte na tlačítko **Další**.

5.  Na **zvolte metody pro generování** zadejte **GetOrders** pro **název metody** v **vrátit DataTable** části.

6.  Klikněte na tlačítko **Dokončit**.

7.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.

## <a name="adding-a-reference-to-the-data-entity-and-data-access-tiers-to-the-data-service"></a>Přidání odkazu na vrstvu datové entity a vrstvu přístupu k datům do datové služby
 Protože služba dat vyžaduje informace ze sady dat a objektů TableAdapters, přidejte odkazy na projekty DataEntityTier a DataAccessTier.

#### <a name="to-add-references-to-the-data-service"></a>Přidání odkazů do datové služby

1.  Klikněte pravým tlačítkem na DataService v **Průzkumníku řešení** a klikněte na tlačítko **přidat odkaz na**.

2.  Klikněte na tlačítko **projekty** ve **přidat odkaz na** dialogové okno.

3.  Vyberte **DataAccessTier** a **DataEntityTier** projekty.

4.  Click **OK**.

## <a name="adding-functions-to-the-service-to-call-the-getcustomers-and-getorders-methods-in-the-data-access-tier"></a>Přidání funkcí do služby za účelem volání metod GetCustomers a GetOrders ve vrstvě přístupu k datům
 Teď, když datová vrstva obsahuje metody, které se vrátit data, vytvořte metody ve službě data k volání metody v datové vrstvě přístup.

> [!NOTE]
>  Pro projekty C#, musíte přidat odkaz na `System.Data.DataSetExtensions` sestavení pro následující kód zkompilovat.

#### <a name="to-create-the-getcustomers-and-getorders-functions-in-the-data-service"></a>Vytvoření funkcí GetCustomers a GetOrders v datové službě

1.  V **DataService** projektu, klikněte dvakrát na IService1.vb nebo IService1.cs.

2.  Přidejte následující kód pod **přidat operací služby zde** komentář:

    ```vb
    <OperationContract()> _
    Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable

    <OperationContract()> _
    Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable
    ```

    ```csharp
    [OperationContract]
    DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers();

    [OperationContract]
    DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders();
    ```

3.  V projektu DataService klikněte dvakrát na Service1.vb (nebo Service1.cs).

4.  Přidejte následující kód do třídy Service1:

    ```vb
    Public Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable Implements IService1.GetCustomers
        Dim CustomersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter
        Return CustomersTableAdapter1.GetCustomers()
    End Function

    Public Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable Implements IService1.GetOrders
        Dim OrdersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter
        Return OrdersTableAdapter1.GetOrders()
    End Function
    ```

    ```csharp
    public DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers()
    {
        DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter
             CustomersTableAdapter1
            = new DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter();
        return CustomersTableAdapter1.GetCustomers();
    }
    public DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders()
    {
        DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter
             OrdersTableAdapter1
            = new DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter();
        return OrdersTableAdapter1.GetOrders();
    }
    ```

5.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.

## <a name="creating-a-presentation-tier-to-display-data-from-the-data-service"></a>Vytvoření prezentační vrstvy zobrazující data z datové služby
 Teď, když řešení obsahuje služba dat, která obsahuje metody, které volají do úroveň přístupu data, vytvořte jiný projekt, který bude provádět volání do službu data a data k dispozici pro uživatele. V tomto návodu vytvořte aplikaci Windows Forms; Toto je prezentační vrstvou vícevrstvé aplikace.

#### <a name="to-create-the-presentation-tier-project"></a>Vytvoření projektu prezentační vrstvy

1.  Klikněte pravým tlačítkem na řešení v Průzkumníku řešení a zvolte **přidat**, **nový projekt...** .

2.  V **nový projekt** dialogové okno, v levém podokně vyberte **Windows Classic Desktop**. V prostředním podokně vyberte **aplikace pro Windows Forms**.

3.  Název projektu **PresentationTier** a klikněte na tlačítko **OK**.

    Projekt PresentationTier je vytvořen a přidán do NTierWalkthrough řešení.

## <a name="setting-the-presentationtier-project-as-the-startup-project"></a>Nastavení projektu PresentationTier jako spouštěného projektu
Vytvoříme PresentationTier projekt, který má být projekt po spuštění pro řešení, protože je skutečný klientské aplikace, která se používají k zobrazení a interakci s daty.

#### <a name="to-set-the-new-presentation-tier-project-as-the-startup-project"></a>Nastavení nového projektu prezentační vrstvy jako spouštěného projektu

-   V **Průzkumníku řešení**, klikněte pravým tlačítkem na **PresentationTier** a klikněte na tlačítko **nastavit jako spouštěný projekt**.

## <a name="adding-references-to-the-presentation-tier"></a>Přidání odkazů do prezentační vrstvy
 Klientská aplikace PresentationTier vyžaduje odkaz na službu ve službě data přístup metody ve službě. Odkaz na datovou sadu se kromě toho je potřeba povolit sdílení službou WCF typu. Dokud nepovolíte sdílení dat pomocí služby typu kódu přidat ke třídě částečné datovou sadu, nebudou k dispozici na prezentační vrstvy. Vzhledem k tomu obvykle přidáte kód, jako je například ověřování do řádků a sloupců Změna události tabulky dat, je pravděpodobné, že budete chtít přístup tento kód z klienta.

#### <a name="to-add-a-reference-to-the-presentation-tier"></a>Přidání odkazu do prezentační vrstvy

1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na PresentationTier a vyberte **přidat odkaz na**.

2.  V **přidat odkaz na** dialogové okno, vyberte **projekty** kartě.

3.  Vyberte **DataEntityTier** a zvolte **OK**.

#### <a name="to-add-a-service-reference-to-the-presentation-tier"></a>Přidání odkazu na službu do prezentační vrstvy

1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na PresentationTier a vyberte **přidat odkaz na službu**.

2.  V **přidat odkaz na službu** dialogové okno, vyberte **Discover**.

3.  Vyberte **Service1** a zvolte **OK**.

    > [!NOTE]
    >  Pokud máte více služeb v počítači, vyberte službu, kterou jste vytvořili dříve v tomto návodu (služba, která obsahuje metody GetCustomers a GetOrders).

## <a name="adding-datagridviews-to-the-form-to-display-the-data-returned-by-the-data-service"></a>Přidání ovládacích prvků DataGridView do formuláře a zobrazení dat vrácených datovou službou
 Po přidání odkazu služby pro službu data **zdroje dat** okno se automaticky zadá data, která je vrácena službou.

#### <a name="to-add-two-data-bound-datagridviews-to-the-form"></a>Přidání dvou ovládacích prvků DataGridView vázaných na data do formuláře

1.  V **Průzkumníku**, vyberte PresentationTier projekt.

2.  V **zdroje dat** okně rozbalte **NorthwindDataSet** a najděte **zákazníci** uzlu.

3.  Přetáhněte **zákazníci** uzlu na Form1.

4.  V **zdroje dat** okno, rozbalte **zákazníci** uzlu a vyhledejte související **objednávky** uzlu ( **objednávky** uzlu vnořených v  **Zákazníci** uzlu).

5.  Přetáhněte související **objednávky** uzlu na Form1.

6.  Vytvoření `Form1_Load` obslužné rutiny události dvojitým kliknutím na prázdnou oblast formuláře.

7.  Přidejte následující kód, který `Form1_Load` obslužné rutiny události.

    ```vb
    Dim DataSvc As New ServiceReference1.Service1Client
    NorthwindDataSet.Customers.Merge(DataSvc.GetCustomers)
    NorthwindDataSet.Orders.Merge(DataSvc.GetOrders)
    ```

    ```csharp
    ServiceReference1.Service1Client DataSvc =
        new ServiceReference1.Service1Client();
    northwindDataSet.Customers.Merge(DataSvc.GetCustomers());
    northwindDataSet.Orders.Merge(DataSvc.GetOrders());
    ```

## <a name="increasing-the-maximum-message-size-allowed-by-the-service"></a>Zvětšení maximální velikosti zprávy povolené službou
Výchozí hodnota pro maxReceivedMessageSize není dostatečně velký pro uložení data načtená z tabulky Zákazníci a objednávky. V následujícím postupu zvýšíte hodnota, která má 6553600. Bude-li změnit hodnotu na klienta, které automaticky aktualizuje odkaz na službu.

> [!NOTE]
>  Nižší výchozí velikost je určena k omezení rizika útoku DoS (DoS). Další informace naleznete v tématu <xref:System.ServiceModel.WSHttpBindingBase.MaxReceivedMessageSize%2A>.

#### <a name="to-increase-the-maxreceivedmessagesize-value"></a>Zvýšení hodnoty maxReceivedMessageSize

1.  V **Průzkumníku**, poklikejte na soubor app.config v PresentationTier projektu.

2.  Vyhledejte **maxReceivedMessage** velikost atribut a změňte hodnotu na `6553600`.

## <a name="testing-the-application"></a>Testování aplikace
Spusťte aplikaci stisknutím **F5**. Data z tabulky Zákazníci a objednávky z službu data načíst a zobrazit ve formuláři.

## <a name="next-steps"></a>Další kroky
 V závislosti na požadavcích vaší aplikace existuje několik kroků, které můžete provést po uložení souvisejících dat v aplikaci systému Windows. Například můžete dokonce vytvářet následující vylepšení do této aplikace:

-   Přidání ověřování do datové sady.

-   Přidejte další metody do služby pro aktualizaci data zpět do databáze.

## <a name="see-also"></a>Viz také

- [Práce s datovými sadami ve vícevrstvých aplikacích](../data-tools/work-with-datasets-in-n-tier-applications.md)
- [Hierarchická aktualizace](../data-tools/hierarchical-update.md)
- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)