---
title: 'Návod: Vytvoření služby WCF Data Service pomocí grafického subsystému WPF a Entity Framework'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data services in Visual Studio
- WCF Data Services, Visual Studio
- ADO.NET Data Services, Visual Studio
- WCF data services in Visual Studio
ms.assetid: da66ad1b-a25d-485c-af13-2d18f0422e3d
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 1433620303c8bf300645681eeabcd12c4a9c36d7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework"></a>Návod: Vytvoření služby WCF Data Service pomocí grafického subsystému WPF a Entity Framework
Tento návod ukazuje, jak vytvořit jednoduchou [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] který je hostován v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci a potom k němu přístup z aplikace Windows Forms.

V tomto návodu se dozvíte, jak:

-   Vytvoření webové aplikace do hostitele [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

-   Vytvoření [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] zákazníkům tabulky v databázi Northwind, která představuje.

-   Vytvoření [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

-   Vytvořit klientskou aplikaci a přidejte odkaz na [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

-   Vytvořit datovou vazbu na službu a vygenerovat uživatelské rozhraní

-   Volitelně přidat do aplikace možnosti filtrování

## <a name="prerequisites"></a>Požadavky
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.

1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [SQL Server Express stránky pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.

2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .

       Otevře se okno editoru dotazů.

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.

## <a name="creating-the-service"></a>Vytvoření služby
Chcete-li vytvořit [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], bude přidejte webový projekt, vytvořte [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]a potom vytvoříte službu z modelu.

V prvním kroku přidáte webový projekt pro hostování služby.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-create-the-web-project"></a>Vytvoření webového projektu

1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.

2.  V **nový projekt** dialogové okno, rozbalte seznam **jazyka Visual Basic** nebo **Visual C#** a **webové** uzly a potom vyberte **ASP. NET webové aplikace** šablony.

3.  V **název** textové pole, zadejte **NorthwindWeb**a potom zvolte **OK** tlačítko.

4.  V **nový projekt ASP.NET** v dialogovém **vyberte šablonu** vyberte **prázdný**a potom zvolte **OK** tlačítko.

V dalším kroku vytvoříte [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] zákazníkům tabulky v databázi Northwind, která představuje.

#### <a name="to-create-the-entity-data-model"></a>Vytvoření modelu Entity Data Model

1.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.

2.  V **přidat novou položku** dialogovém okně vyberte **Data** uzel a potom vyberte **ADO.NET Entity Data Model** položky.

3.  V **název** textové pole, zadejte `NorthwindModel`a potom zvolte **přidat** tlačítko.

     Zobrazí se Průvodce modelem Entity Data Model.

4.  V průvodci Entity Data Model na **zvolte obsah modelu** vyberte **EF Designer z databáze** položku a potom vyberte **Další** tlačítko.

5.  Na **vybrat datové připojení** proveďte některý z následujících kroků:

    -   Pokud je datové připojení k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.

         -nebo-

    -   Vyberte **nové připojení** tlačítko Konfigurovat nové datové připojení. Další informace najdete v tématu [přidat nová připojení](../data-tools/add-new-connections.md).

6.  Pokud databáze vyžaduje heslo, vyberte **Ano, zahrnout důvěrné osobní údaje v připojovacím řetězci** možnost tlačítko a potom vyberte **Další** tlačítko.

    > [!NOTE]
    >  Pokud se zobrazí dialogové okno, zvolte **Ano** k uložení souboru do projektu.

7.  Na **zvolíte verzi** vyberte **Entity Framework 5.0** možnost tlačítko a potom vyberte **Další** tlačítko.

    > [!NOTE]
    >  Abyste mohli používat nejnovější verzi Entity Framework 6 s služby WCF, budete muset nainstalovat balíček NuGet pro WCF Data Services Entity Framework zprostředkovatele. V tématu [pomocí WCF Data Services 5.6.0 s platformou Entity Framework 6 +](http://blogs.msdn.com/b/odatateam/archive/2013/10/02/using-wcf-data-services-5-6-0-with-entity-framework-6.aspx).

8.  Na **zvolte si databázové objekty** rozbalte **tabulky** uzlu, vyberte **zákazníci** zaškrtněte políčko a potom vyberte **Dokončit** tlačítko.

     Zobrazí se diagram modelu entit a do projektu bude přidán soubor NorthwindModel.edmx.

V dalším kroku vytvoříte a testovat službu data.

#### <a name="to-create-the-data-service"></a>Vytvoření datové služby

1.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.

2.  V **přidat novou položku** dialogovém okně vyberte **webové** uzel a potom vyberte **WCF Data Service 5.6** položky.

3.  V **název** textové pole, zadejte `NorthwindCustomers`a potom zvolte **přidat** tlačítko.

     Soubor NorthwindCustomers.svc se zobrazí v **Editor kódu**.

4.  V **Editor kódu**, vyhledejte první `TODO:` komentovat a kódu nahraďte následujícím kódem:

     [!code-vb[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.cs)]

5.  Nahraďte komentáře v `InitializeService` obslužné rutiny události s následujícím kódem:

     [!code-vb[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.cs)]

6.  Na řádku nabídek zvolte **ladění**, **spustit bez ladění** službu spustit. Otevře se okno prohlížeče a zobrazí se schéma XML pro službu.

7.  V **adresu** panel, zadejte `Customers` na konci adresy URL pro NorthwindCustomers.svc a potom zvolte **ENTER** klíč.

     Zobrazí se reprezentace dat z tabulky Customers v jazyce XML.

    > [!NOTE]
    >  V některých případech bude aplikace Internet Explorer chybně interpretovat data jako informační kanál RSS. Zkontrolujte, zda je zakázána možnost zobrazení informačních kanálů RSS. Další informace najdete v tématu [řešení potíží s odkazy na službu](../data-tools/troubleshooting-service-references.md).

8.  Zavřete okno prohlížeče.

V dalších krocích vytvoříte klientskou aplikaci založenou na modelu Windows Forms, která bude službu používat.

## <a name="creating-the-client-application"></a>Vytvoření klientské aplikace
 Vytvoříte klientskou aplikaci tak, že přidáte druhý projekt, do projektu přidáte odkaz na službu, nakonfigurujete zdroj dat a vytvoříte uživatelské rozhraní pro zobrazení dat ze služby.

 V prvním kroku přidáte do řešení projekt modelu Windows Forms a nastavíte ho jako spouštěný projekt.

#### <a name="to-create-the-client-application"></a>Vytvoření klientské aplikace

1.  V řádku nabídek zvolte soubor, **přidat**, **nový projekt**.

2.  V **nový projekt** dialogové okno, rozbalte seznam **jazyka Visual Basic** nebo **Visual C#** uzel a zvolte **Windows** uzel a potom zvolte  **Aplikaci Windows Forms**.

3.  V **název** textové pole, zadejte `NorthwindClient`a potom zvolte **OK** tlačítko.

4.  V **Průzkumníku řešení**, vyberte **NorthwindClient** uzel projektu.

5.  Na řádku nabídek zvolte **projektu**, **nastavit jako spouštěný projekt**.

V dalším kroku přidáte odkaz na službu [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] webového projektu.

#### <a name="to-add-a-service-reference"></a>Přidání odkazu na službu

1.  Na řádku nabídek zvolte **projektu**, **přidat odkaz na službu**.

2.  V **přidat odkaz na službu** dialogovém okně vyberte **Discover** tlačítko.

     Adresa URL služby NorthwindCustomers se zobrazí v **adresu** pole.

3.  Vyberte **OK** tlačítko Přidat odkaz na službu.

V dalším kroku můžete nakonfigurovat zdroji dat povolit datové vazby ke službě.

#### <a name="to-enable-data-binding-to-the-service"></a>Vytvoření datové vazby na službu

1.  Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **zdroje dat**.

2.  V **zdroje dat** okně zvolte **přidat nový zdroj dat** tlačítko.

3.  Na **zvolte typ zdroje dat** stránky **Průvodce konfigurací zdroje dat**, zvolte **objekt**a potom zvolte **Další** tlačítko .

4.  Na **vyberte datové objekty** rozbalte **NorthwindClient** uzel a potom rozbalte **NorthwindClient.ServiceReference1** uzlu.

5.  Vyberte **zákazníka** zaškrtněte políčko a potom vyberte **Dokončit** tlačítko.

V dalším kroku vytvoříte uživatelské rozhraní, které se zobrazí data ze služby.

#### <a name="to-create-the-user-interface"></a>Vytvoření uživatelského rozhraní

1.  V **zdroje dat** okně otevřete místní nabídku pro **zákazníci** uzel a zvolte **kopie**.

2.  V **Form1.vb** nebo **Form1.cs** formuláři designer, otevřete místní nabídku a vyberte možnost **vložení**.

     A <xref:System.Windows.Forms.DataGridView> řízení, <xref:System.Windows.Forms.BindingSource> součást a <xref:System.Windows.Forms.BindingNavigator> součásti jsou přidány do formuláře.

3.  Vyberte **CustomersDataGridView** řízení a pak v **vlastnosti** okno sady **ukotvení** vlastnost **vyplnění**.

4.  V **Průzkumníku řešení**, otevřete místní nabídku pro **Form1** uzel a zvolte **kód zobrazení** otevření editoru kódu a přidejte následující importy nebo pomocí příkazu na horní části souboru:

    ```vb
    Imports NorthwindClient.ServiceReference1
    ```

    ```csharp
    using NorthwindClient.ServiceReference1;
    ```

5.  Přidejte následující kód, který `Form1_Load` obslužné rutiny události:

    ```vb
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
            Dim proxy As New NorthwindEntities _
    (New Uri("http://localhost:53161/NorthwindCustomers.svc/"))
            Me.CustomersBindingSource.DataSource = proxy.Customers
        End Sub
    ```

    ```csharp
    private void Form1_Load(object sender, EventArgs e)
    {
    NorthwindEntities proxy = new NorthwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc/"));
    this.CustomersBindingSource.DataSource = proxy.Customers;
    }

    ```

6.  V **Průzkumníku řešení**, otevřete místní nabídku pro soubor NorthwindCustomers.svc a zvolte **zobrazit v prohlížeči**. Spustí se aplikace Internet Explorer a zobrazí se schéma XML pro službu.

7.  Zkopírujte adresu URL z panelu Adresa aplikace Internet Explorer.

8.  V kódu, který jste přidali v kroku 4, vyberte `http://localhost:53161/NorthwindCustomers.svc/` a nahraďte adresu URL, kterou jste právě zkopírovali.

9. Na řádku nabídek zvolte **ladění**, **spustit ladění** ke spuštění aplikace. Zobrazí se informace o zákazníkovi.

 Nyní máte funkční aplikaci, která zobrazuje seznam zákazníků ze služby NorthwindCustomers. Pokud chcete zobrazit další data prostřednictvím služby, můžete upravit [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] chcete zahrnout další tabulky z databáze Northwind.

V dalším volitelném kroku se dozvíte, jak filtrovat data, která služba vrací.

## <a name="adding-filtering-capabilities"></a>Přidání možností filtrování
 V tomto kroku přizpůsobíte aplikaci tak, aby umožňovala filtrování dat podle města zákazníka.

#### <a name="to-add-filtering-by-city"></a>Přidání filtrování podle města

1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **Form1.vb** nebo **Form1.cs** uzel a zvolte **otevřete**.

2.  Přidat <xref:System.Windows.Forms.TextBox> řízení a <xref:System.Windows.Forms.Button> řídit z **sada nástrojů** do formuláře.

3.  Otevřete místní nabídku pro <xref:System.Windows.Forms.Button> řízení a zvolte **kód zobrazení**a poté přidejte následující kód do `Button1_Click` obslužné rutiny události:

    ```vb
    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
            Dim proxy As New northwindEntities _
    (New Uri("http://localhost:53161/NorthwindCustomers.svc"))
            Dim city As String = TextBox1.Text

            If city <> "" Then
                Me.CustomersBindingSource.DataSource = From c In _
             proxy.Customers Where c.City = city
            End If

        End Sub
    ```

    ```csharp
    private void Button1_Click(object sender, EventArgs e)
    {
    ServiceReference1.northwindModel.northwindEntities proxy = new northwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc"));
    string city = TextBox1.Text;

    if (!string.IsNullOrEmpty(city)) {
    this.CustomersBindingSource.DataSource = from c in proxy.Customers where c.City == city;
    }

    }
    ```

4.  V předchozí kód, nahraďte `http://localhost:53161/NorthwindCustomers.svc` s adresou URL z `Form1_Load` obslužné rutiny události.

5.  Na řádku nabídek zvolte **ladění**, **spustit ladění** ke spuštění aplikace.

6.  Do textového pole zadejte **Londýn**a pak zvolte tlačítko. Zobrazí se pouze zákazníci z Londýna.

## <a name="see-also"></a>Viz také

- [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
- [Postupy: Přidání, aktualizace nebo odebrání odkazu na službu WCF Data](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)