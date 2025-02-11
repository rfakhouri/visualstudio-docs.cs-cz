---
title: Vytvoření datové služby WCF pomocí & WPF Entity Framework
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
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 6ed07e723b2cb423883491d7e6ca3774a12d0824
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925457"
---
# <a name="walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework"></a>Návod: Vytvoření datové služby WCF pomocí WPF a Entity Framework
Tento návod ukazuje, jak vytvořit jednoduchý [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] hostovaný [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] ve webové aplikaci a pak k němu přistupovat z aplikace model Windows Forms.

V tomto návodu:

- Vytvořte webovou aplikaci pro hostování [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

- Vytvořte, který `Customers` představuje tabulku v databázi Northwind. [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]

- Vytvoření [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

- Vytvořte klientskou aplikaci a přidejte do ní odkaz [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

- Vytvořit datovou vazbu na službu a vygenerovat uživatelské rozhraní

- Volitelně přidat do aplikace možnosti filtrování

## <a name="prerequisites"></a>Požadavky
Tento návod používá SQL Server Express LocalDB a ukázkovou databázi Northwind.

1. Pokud nemáte SQL Server Express LocalDB, nainstalujte ji buď ze [stránky pro stažení SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo prostřednictvím **instalační program pro Visual Studio**. V **instalační program pro Visual Studio**můžete nainstalovat SQL Server Express LocalDB jako součást úlohy **ukládání a zpracování dat** nebo jako jednotlivé komponenty.

2. Nainstalujte ukázkovou databázi Northwind pomocí následujících kroků:

    1. V aplikaci Visual Studio otevřete okno **Průzkumník objektů systému SQL Server** . (**Průzkumník objektů systému SQL Server** je nainstalován v rámci úlohy **úložiště dat a zpracování** v instalační program pro Visual Studio.) Rozbalte uzel **SQL Server** . Klikněte pravým tlačítkem na instanci LocalDB a vyberte **Nový dotaz**.

       Otevře se okno editor dotazů.

    2. Zkopírujte [skript Transact-SQL Northwind](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní ji daty.

    3. Vložte skript T-SQL do editoru dotazů a klikněte na tlačítko **Execute** tlačítko.

       Po krátké době se dotaz dokončí a vytvoří se databáze Northwind.

## <a name="creating-the-service"></a>Vytvoření služby
Chcete-li [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]vytvořit, přidejte webový projekt, [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]vytvořte a potom vytvořte službu z modelu.

V prvním kroku přidáte webový projekt, který bude hostitelem služby.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-the-web-project"></a>Vytvoření webového projektu

1. V panelu nabídky zvolte **souboru** > **nový** > **projektu**.

2. V dialogovém okně **Nový projekt** rozbalte **Visual Basic** nebo **Visual C#**  a **webové** uzly a pak zvolte šablonu **webové aplikace ASP.NET** .

3. Do textového pole **název** zadejte **NorthwindWeb**a poté klikněte na tlačítko **OK** .

4. V dialogovém okně **Nový projekt ASP.NET** v seznamu **Vyberte šablonu** zvolte **prázdné**a pak klikněte na tlačítko **OK** .

V dalším kroku vytvoříte [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] , který `Customers` představuje tabulku v databázi Northwind.

### <a name="to-create-the-entity-data-model"></a>Vytvoření modelu Entity Data Model

1. V panelu nabídky zvolte **projektu** > **přidat novou položku**.

2. V dialogovém okně **Přidat novou položku** zvolte uzel **dat** a pak zvolte položku **ADO.NET model EDM (Entity Data Model)** .

3. Do textového pole **název** zadejte `NorthwindModel`a pak klikněte na tlačítko **Přidat** .

     Zobrazí se Průvodce modelem Entity Data Model.

4. V průvodci model EDM (Entity Data Model) na stránce **Výběr obsahu modelu** zvolte položku **Návrhář EF z položky databáze** a poté klikněte na tlačítko **Další** .

5. Na stránce **Vyberte datové připojení** proveďte jeden z následujících kroků:

    - Pokud je datové připojení k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.

         -nebo-

    - Klikněte na tlačítko **nové připojení** a nakonfigurujte nové datové připojení. Další informace najdete v tématu [Přidání nových připojení](../data-tools/add-new-connections.md).

6. Pokud databáze vyžaduje heslo, vyberte možnost **Ano, zahrnout citlivá data do připojovacího řetězce** a potom klikněte na tlačítko **Další** .

    > [!NOTE]
    > Pokud se zobrazí dialogové okno, klikněte na **tlačítko Ano** a uložte soubor do projektu.

7. Na stránce **Zvolte verzi** zvolte možnost **Entity Framework 5,0** a potom klikněte na tlačítko **Další** .

    > [!NOTE]
    > Aby bylo možné používat nejnovější verzi Entity Framework 6 se službami WCF, bude nutné nainstalovat balíček NuGet poskytovatele WCF Data Services Entity Framework. Viz [použití WCF Data Services 5.6.0 s Entity Framework 6 +](https://devblogs.microsoft.com/odata/using-wcf-data-services-5-6-0-with-entity-framework-6/).

8. Na stránce **Zvolte vaše databázové objekty** rozbalte uzel **tabulky** , zaškrtněte políčko **zákazníci** a pak klikněte na tlačítko **Dokončit** .

     V diagramu modelu entit se zobrazí a do projektu se přidá soubor *NorthwindModel. edmx* .

V dalším kroku vytvoříte a otestujete datovou službu.

### <a name="to-create-the-data-service"></a>Vytvoření datové služby

1. V panelu nabídky zvolte **projektu** > **přidat novou položku**.

2. V dialogovém okně **Přidat novou položku** zvolte uzel **Web** a pak zvolte položku **WCF Data Service 5,6** .

3. Do textového pole **název** zadejte `NorthwindCustomers`a pak klikněte na tlačítko **Přidat** .

     V **editoru kódu**se zobrazí soubor **NorthwindCustomers. svc** .

4. V **editoru kódu**vyhledejte první `TODO:` komentář a nahraďte kód následujícím kódem:

     [!code-vb[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.cs)]

5. Nahraďte komentáře v `InitializeService` obslužné rutině události následujícím kódem:

     [!code-vb[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.cs)]

6. Na panelu nabídek vyberte možnost **ladit** > **Spustit bez ladění** a spusťte službu. Otevře se okno prohlížeče a zobrazí se schéma XML pro službu.

7. Do **adresního** řádku zadejte `Customers` na konci adresy URL pro **NorthwindCustomers. svc**a pak zvolte klávesu **ENTER** .

     Zobrazí se reprezentace dat v `Customers` tabulce v jazyce XML.

    > [!NOTE]
    > V některých případech bude aplikace Internet Explorer chybně interpretovat data jako informační kanál RSS. Zkontrolujte, zda je zakázána možnost zobrazení informačních kanálů RSS. Další informace najdete v tématu [řešení potíží s odkazy na služby](../data-tools/troubleshooting-service-references.md).

8. Zavřete okno prohlížeče.

V dalších krocích vytvoříte klientskou aplikaci model Windows Forms pro využívání služby.

## <a name="creating-the-client-application"></a>Vytvoření klientské aplikace
Chcete-li vytvořit klientskou aplikaci, přidejte druhý projekt, přidejte do projektu odkaz na službu, nakonfigurujte zdroj dat a vytvořte uživatelské rozhraní pro zobrazení dat ze služby.

V prvním kroku přidáte model Windows Forms projekt do řešení a nastavíte ho jako spouštěný projekt.

### <a name="to-create-the-client-application"></a>Vytvoření klientské aplikace

1. Na panelu nabídek vyberte možnost soubor, **Přidat** > **Nový projekt**.

2. V dialogovém okně **Nový projekt** rozbalte uzel **Visual Basic** nebo **Visual C#**  , zvolte uzel **Windows** a pak zvolte **model Windows Forms aplikace**.

3. Do textového pole **název** zadejte `NorthwindClient`a pak klikněte na tlačítko **OK** .

4. V **Průzkumník řešení**vyberte uzel projektu **NorthwindClient** .

5. V panelu nabídek vyberte položku **projekt**, **nastavit jako spouštěný projekt**.

V dalším kroku přidáte odkaz na službu do [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] webového projektu.

### <a name="to-add-a-service-reference"></a>Přidání odkazu na službu

1. Na panelu nabídek vyberte možnost **projekt** > **Přidat odkaz na službu**.

2. V dialogovém okně **Přidat odkaz na službu** klikněte na tlačítko **Vyhledat** .

     Adresa URL služby NorthwindCustomers se zobrazí v poli **adresa** .

3. Kliknutím na tlačítko **OK** přidejte odkaz na službu.

V dalším kroku nakonfigurujete zdroj dat, který povolí datovou vazbu ke službě.

### <a name="to-enable-data-binding-to-the-service"></a>Vytvoření datové vazby na službu

1. Na panelu nabídek vyberte možnost **Zobrazit** > **ostatní** > **zdroje dat**Windows.

   Otevře se okno **zdroje dat** .

2. V okně **zdroje dat** klikněte na tlačítko **Přidat nový zdroj dat** .

3. Na stránce **Vybrat typ zdroje dat** v **Průvodci konfigurací zdroje dat**zvolte možnost **objekt**a poté klikněte na tlačítko **Další** .

4. Na stránce **Vyberte datové objekty** rozbalte uzel **NorthwindClient** a potom rozbalte uzel **NorthwindClient. ServiceReference1** .

5. Zaškrtněte políčko **Zákazník** a pak klikněte na tlačítko **Dokončit** .

V dalším kroku vytvoříte uživatelské rozhraní, které zobrazí data ze služby.

### <a name="to-create-the-user-interface"></a>Vytvoření uživatelského rozhraní

1. V okně **zdroje dat** otevřete místní nabídku uzlu Customers a vyberte možnost **Kopírovat**.

2. V návrháři formuláře **Form1. vb** nebo **Form1.cs** otevřete místní nabídku a vyberte možnost **Vložit**.

    Do formuláře jsou přidány <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingNavigator> ovládací prvky, komponenty a komponenta. <xref:System.Windows.Forms.DataGridView>

3. Zvolte ovládací prvek **customersDataGridView** a potom v okně **vlastnosti** nastavte vlastnost **Dock** na **Fill**.

4. V **Průzkumník řešení**otevřete místní nabídku pro uzel **Form1** a výběrem možnosti **Zobrazit kód** otevřete Editor kódu a přidejte následující `Imports` příkaz nebo `Using` příkaz v horní části souboru:

   ```vb
   Imports NorthwindClient.ServiceReference1
   ```

   ```csharp
   using NorthwindClient.ServiceReference1;
   ```

5. Do obslužné rutiny `Form1_Load` události přidejte následující kód:

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

6. V **Průzkumník řešení**otevřete místní nabídku pro soubor **NorthwindCustomers. svc** a v prohlížeči vyberte možnost **Zobrazit**. Otevře se aplikace Internet Explorer a zobrazí se schéma XML pro službu.

7. Zkopírujte adresu URL z panelu Adresa aplikace Internet Explorer.

8. V kódu, který jste přidali v kroku 4, vyberte `http://localhost:53161/NorthwindCustomers.svc/` a nahraďte ji adresou URL, kterou jste právě zkopírovali.

9. Na panelu nabídek vyberte **ladit** > **Spustit ladění** a spusťte aplikaci. Zobrazí se informace o zákazníkovi.

   Nyní máte funkční aplikaci, která zobrazuje seznam zákazníků ze služby NorthwindCustomers. Pokud chcete zpřístupnit další data prostřednictvím služby, můžete upravit [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] tak, aby zahrnovalo další tabulky z databáze Northwind.

V dalším volitelném kroku se dozvíte, jak filtrovat data, která služba vrací.

## <a name="adding-filtering-capabilities"></a>Přidání možností filtrování
V tomto kroku přizpůsobíte aplikaci pro filtrování dat podle města zákazníka.

### <a name="to-add-filtering-by-city"></a>Přidání filtrování podle města

1. V **Průzkumník řešení**otevřete místní nabídku uzlu **Form1. vb** nebo **Form1.cs** a klikněte na tlačítko **otevřít**.

2. Přidejte ovládací prvek <xref:System.Windows.Forms.Button> a ovládací prvek ze **sady nástrojů do formuláře** <xref:System.Windows.Forms.TextBox> .

3. Otevřete místní nabídku pro <xref:System.Windows.Forms.Button> ovládací prvek, zvolte možnost **Zobrazit kód**a přidejte `Button1_Click` následující kód do obslužné rutiny události:

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

4. V předchozím kódu nahraďte `http://localhost:53161/NorthwindCustomers.svc` adresu URL `Form1_Load` z obslužné rutiny události.

5. Na panelu nabídek vyberte **ladit** > **Spustit ladění** a spusťte aplikaci.

6. Do textového pole zadejte **London**a pak klikněte na tlačítko. Zobrazí se pouze zákazníci z Londýna.

## <a name="see-also"></a>Viz také:

- [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
- [Postupy: Přidání, aktualizace nebo odebrání odkazu na službu WCF Data Service](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)