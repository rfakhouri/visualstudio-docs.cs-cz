---
title: Předávání dat mezi formuláři | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- walkthroughs [Windows Forms], data
- walkthroughs [Visual Studio], data
- data [Visual Studio], passing between forms
- forms, passing data between
- Windows Forms, walkthroughs
ms.assetid: 78bf038b-9296-4fbf-b0e8-d881d1aff0df
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 87fdd9c898b0705c2a3463cb8f9932fda22734ea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="pass-data-between-forms"></a>Předávání dat mezi formuláři
Tento názorný postup obsahuje podrobné pokyny pro předávání dat z jednoho formátu do druhého. Pomocí zákazníků a tabulky objednávky z Northwind, jeden formulář umožňuje vybrat zákazníka a druhý formulář obsahuje objednávky vybraného zákazníka. Tento návod ukazuje postup vytvoření metody na druhý formulář, který přijímá data z první formulář.  
  
> [!NOTE]
>  Tento návod ukazuje pouze jeden způsob k předávání dat mezi formuláři. Existují další možnosti pro předávání dat na formulář, včetně vytváření druhý konstruktor pro příjem dat, nebo vytvoření veřejné vlastnosti, které lze nastavit s daty z první formulář.  
  
 Úkoly v tomto návodu zahrnují:  
  
-   Vytvoření nové **formulářové aplikace Windows** projektu.  
  
-   Vytváření a konfiguraci datová sada se [Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png).  
  
-   Výběr má být vytvořen ve formuláři při přetáhnete položky z ovládacího prvku **zdroje dat** okno. Další informace najdete v tématu [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
-   Vytvoření ovládacího prvku vázané na data tak, že přetáhnete položky z **zdroje dat** okna do formuláře.  
  
-   Vytváření druhý formulář s mřížce se zobrazí data.  
  
-   Vytváření dotazu TableAdapter načíst objednávky pro konkrétního zákazníka.  
  
-   Předávání dat mezi formuláři.  
  
## <a name="prerequisites"></a>Požadavky  
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.  
  
1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [SQL Server Express stránky pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.  
  
2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:  

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .  

       Otevře se okno editoru dotazů.  

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.  

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.  

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.  
  
## <a name="create-the-windows-forms-application"></a>Vytvořte aplikaci Windows Forms  
  
#### <a name="to-create-the-new-windows-project"></a>Vytvoření nového projektu Windows  
  
1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .  
  
2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.  

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.  

4. Název projektu **PassingDataBetweenForms**a potom zvolte **OK**. 
  
     **PassingDataBetweenForms** projekt je vytvořen a přidán do **Průzkumníku řešení**.  
  
## <a name="create-the-data-source"></a>Vytvoření zdroje dat  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.  
  
2.  V **zdroje dat** vyberte **přidat nový zdroj dat** spustit **konfigurace zdroje dat** průvodce.  
  
3.  Vyberte **databáze** na **zvolte typ zdroje dat** a pak klikněte na tlačítko **Další**.  
  
4.  Na **vyberte model databáze** ověřte, zda **datovou sadu** byl zadán a pak klikněte na tlačítko **Další**.  
  
5.  Na **zvolit datové připojení** proveďte jednu z následujících:  
  
    -   Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.  
  
    -   Vyberte **nové připojení** ke spuštění **přidat či upravit připojení** dialogové okno.  
  
6.  Pokud vaše databáze vyžaduje heslo, a pokud je povolena možnost obsahují citlivá data, vyberte možnost a pak klikněte na tlačítko **Další**.  
  
7.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.  
  
8.  Na **zvolte databázové objekty** rozbalte **tabulky** uzlu.  
  
9. Vyberte **zákazníci** a **objednávky** tabulky a pak klikněte na tlačítko **Dokončit**.  
  
     **NorthwindDataSet** se přidá do projektu a **zákazníci** a **objednávky** tabulky se zobrazí v **zdroje dat** okno.  
  
## <a name="create-the-first-form-form1"></a>Vytvoření první formuláře (Form1)  
 Můžete vytvořit mřížky vázané na data ( <xref:System.Windows.Forms.DataGridView> ovládací prvek), tak, že přetáhnete **zákazníci** uzlu z **zdroje dat** window do formuláře.  
  
#### <a name="to-create-a-data-bound-grid-on-the-form"></a>Vytvoření mřížky vázané na data ve formuláři  
  
-   Přetáhněte hlavní **zákazníci** uzlu z **zdroje dat** okna do **Form1**.  
  
     A <xref:System.Windows.Forms.DataGridView> a pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>) pro procházení záznamů zobrazí na **Form1**. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent.  
  
## <a name="create-the-second-form-form2"></a>Vytvořte druhý formulář (Form2)  
  
#### <a name="to-create-a-second-form-to-pass-the-data-to"></a>Chcete-li vytvořit druhý formulář k předávání dat do  
  
1.  Z **projektu** nabídce zvolte **přidat formuláře Windows**.  
  
2.  Ponechte výchozí název **Form2**a klikněte na tlačítko **přidat**.  
  
3.  Přetáhněte hlavní **objednávky** uzlu z **zdroje dat** okna do **Form2**.  
  
     A <xref:System.Windows.Forms.DataGridView> a pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>) pro procházení záznamů zobrazí na **Form2**. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent.  
  
4.  Odstranit **OrdersBindingNavigator** z komponent.  
  
     **OrdersBindingNavigator** dané zařízení zmizí z **Form2**.  
  
## <a name="add-a-tableadapter-query-to-form2-to-load-orders-for-the-selected-customer-on-form1"></a>Přidejte do Form2 načíst objednávky pro vybrané odběratele na Form1 dotazu TableAdapter  
  
#### <a name="to-create-a-tableadapter-query"></a>K vytvoření dotazu TableAdapter  
  
1.  Dvakrát klikněte **NorthwindDataSet.xsd** souboru v **Průzkumníku řešení**.  
  
2.  Klikněte pravým tlačítkem myši **OrdersTableAdapter**a vyberte **přidat dotazu**.  
  
3.  Ponechte výchozí možnost **příkazy SQL pomocí**a potom klikněte na **Další**.  
  
4.  Ponechte výchozí možnost **vyberte, které vrací řádky**a potom klikněte na **Další**.  
  
5.  Přidejte klauzuli WHERE dotazu, vrátit `Orders` na základě `CustomerID`. Dotaz by měl vypadat přibližně takto:  
  
    ```  
    SELECT OrderID, CustomerID, EmployeeID, OrderDate, RequiredDate, ShippedDate, ShipVia, Freight, ShipName, ShipAddress, ShipCity, ShipRegion, ShipPostalCode, ShipCountry  
    FROM Orders   
    WHERE CustomerID = @CustomerID  
    ```  
  
    > [!NOTE]
    >  Ověřte syntaxi správný parametr pro vaši databázi. Například v aplikaci Microsoft Access, klauzuli WHERE bude vypadat: `WHERE CustomerID = ?`.  
  
6.  Klikněte na tlačítko **Další**.  
  
7.  Pro **zadejte název DataTableMethod**, typ `FillByCustomerID`.  
  
8.  Vymazat **vrátit DataTable** a potom klikněte na **Další**.  
  
9. Klikněte na tlačítko **Dokončit**.  
  
## <a name="create-a-method-on-form2-to-pass-data-to"></a>Vytvoření metody na Form2 k předávání dat do  
  
#### <a name="to-create-a-method-to-pass-data-to"></a>Vytvořit metodu k předávání dat do  
  
1.  Klikněte pravým tlačítkem na **Form2**a vyberte **kód zobrazení** otevřete **Form2** v **Editor kódu**.  
  
2.  Přidejte následující kód, který **Form2** po `Form2_Load` metoda:  
  
     [!code-vb[VbRaddataDisplaying#1](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_1.vb)]
     [!code-csharp[VbRaddataDisplaying#1](../data-tools/codesnippet/CSharp/pass-data-between-forms_1.cs)]  
  
## <a name="create-a-method-on-form1-to-pass-data-and-display-form2"></a>Vytvoření metody na Form1 k předávání dat a zobrazení Form2  
  
#### <a name="to-create-a-method-to-pass-data-to-form2"></a>Vytvořit metodu k předávání dat na Form2  
  
1.  V **Form1**klikněte pravým tlačítkem mřížky dat zákazníka a pak klikněte na tlačítko **vlastnosti**.  
  
2.  V **vlastnosti** okně klikněte na tlačítko **události**.  
  
3.  Dvakrát klikněte **CellDoubleClick** událostí.  
  
     Editor kódu se zobrazí.  
  
4.  Aktualizace definice metoda tak, aby odpovídala následující ukázka:  
  
     [!code-csharp[VbRaddataDisplaying#2](../data-tools/codesnippet/CSharp/pass-data-between-forms_2.cs)]
     [!code-vb[VbRaddataDisplaying#2](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_2.vb)]  
  
## <a name="run-the-application"></a>Spuštění aplikace  
  
#### <a name="to-run-the-application"></a>Ke spuštění aplikace  
  
-   Stisknutím klávesy F5 spusťte aplikaci.  
  
-   Klikněte dvakrát na záznam zákazníka v **Form1** otevřete **Form2** s objednávky tohoto zákazníka.  
  
## <a name="next-steps"></a>Další kroky  
 V závislosti na požadavcích vaší aplikace existuje několik kroků, které můžete chtít provést po předávání dat mezi formuláři. Mezi vylepšení, která je možné pro tento návod provést, patří:  
  
-   Úpravy datovou sadu, přidat nebo odebrat databázové objekty. Další informace najdete v tématu [vytvořit a nakonfigurovat datové sady](../data-tools/create-and-configure-datasets-in-visual-studio.md).  
  
-   Přidání funkce k uložení dat zpět do databáze. Další informace najdete v tématu [uložit data zpět do databáze](../data-tools/save-data-back-to-the-database.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)