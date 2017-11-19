---
title: "Návod: Ukládání dat v transakci | Microsoft Docs"
ms.custom: 
ms.date: 09/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- System.Transactions namespace
- data [Visual Studio], saving in a transaction
- transactions, saving data
- Transactions namespace
- saving data
ms.assetid: 80260118-08bc-4b37-bfe5-9422ee7a1e4e
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: f8d1d25c2aaa66658df53dbaea366c196e8e7f6b
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="walkthrough-save-data-in-a-transaction"></a>Návod: Ukládání dat do transakce
Tento návod ukazuje, jak k uložení dat v transakci pomocí <xref:System.Transactions> oboru názvů. V tomto návodu vytvoříte aplikaci Windows Forms. Průvodce konfigurací zdroje dat použijete k vytvoření datové sady pro dvě tabulky v ukázkové databázi Northwind. Data vázané ovládací prvky na formuláři Windows, a budete upravovat kód pro objektu BindingNavigator na tlačítko Uložit k aktualizaci databáze uvnitř objekt TransactionScope přidáte.  
  
## <a name="prerequisites"></a>Požadavky  
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.  
  
1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [stránce pro stažení edice serveru SQL](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **vývoj aplikací .NET** zatížení, nebo jako jednotlivých součástí.  
  
2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:  

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .  

       Otevře se okno editoru dotazů.  

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.  

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.  

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.  
  
## <a name="create-a-windows-forms-application"></a>Vytvoření aplikace Windows Forms  
 Prvním krokem je vytvoření **formulářové aplikace Windows**.  
  
#### <a name="to-create-the-new-windows-project"></a>Vytvoření nového projektu Windows  
  
1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .  
  
2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.  

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.  

4. Název projektu **SavingDataInATransactionWalkthrough**a potom zvolte **OK**. 
  
     **SavingDataInATransactionWalkthrough** je vytvořen a přidán do projektu **Průzkumníku řešení**.  
  
## <a name="create-a-database-data-source"></a>Vytvoření zdroje dat databáze  
 Tento krok používá **Průvodce konfigurací zdroje dat** vytvořit zdroj dat na základě `Customers` a `Orders` tabulky v ukázkové databázi Northwind.  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Na **Data** nabídce vyberte možnost **zobrazit zdroje dat**.  
  
2.  V **zdroje dat** vyberte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
3.  Na **zvolte typ zdroje dat** obrazovku, vyberte **databáze**a potom vyberte **Další**.  
  
4.  Na **zvolit datové připojení** proveďte obrazovky, jednu z následujících akcí:  
  
    -   Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.  
  
         -nebo-  
  
    -   Vyberte **nové připojení** ke spuštění **přidat či upravit připojení** dialogové okno pole a vytvořit připojení k databázi Northwind.  
  
5.  Pokud vaše databáze vyžaduje heslo, vyberte možnost obsahují citlivá data a pak vyberte **Další**.  
  
6.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace** obrazovku, vyberte **Další**.  
  
7.  Na **zvolte databázové objekty** obrazovky, rozbalte **tabulky** uzlu.  
  
8.  Vyberte `Customers` a `Orders` tabulky a potom vyberte **Dokončit**.  
  
     **NorthwindDataSet** se přidá do projektu a `Customers` a `Orders` tabulky se zobrazí v **zdroje dat** okno.  
  
## <a name="add-controls-to-the-form"></a>Přidání ovládacích prvků formuláře  
 Ovládací prvky vázané na data můžete vytvořit tak, že přetáhnete položky z **zdroje dat** okna do svého formuláře.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Chcete-li vytvořit data vázané ovládací prvky na formuláři Windows  
  
-   V **zdroje dat** okno, rozbalte **zákazníci** uzlu.  
  
-   Přetáhněte hlavní **zákazníci** uzlu z **zdroje dat** okna do **Form1**.  
  
     A <xref:System.Windows.Forms.DataGridView> řízení a pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>) pro procházení záznamů jsou zobrazena na formuláři. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `CustomersTableAdapter`, <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent.  
  
-   Přetáhněte související **objednávky** uzlu (není hlavním **objednávky** uzlu, ale uzlu související podřízenou tabulku níže **Fax** sloupce) do následující formulář  **CustomersDataGridView**.  
  
     A <xref:System.Windows.Forms.DataGridView> se zobrazí na formuláři. `OrdersTableAdapter` a <xref:System.Windows.Forms.BindingSource> se zobrazí v okně komponent.  
  
## <a name="add-a-reference-to-the-systemtransactions-assembly"></a>Přidat odkaz na sestavení System.Transactions –  
 Použití transakcí <xref:System.Transactions> oboru názvů. Projektu odkaz na sestavení System.Transactions – nebyla přidána ve výchozím nastavení, takže budete muset ručně ji přidejte.  
  
#### <a name="to-add-a-reference-to-the-systemtransactions-dll-file"></a>Chcete-li přidat odkaz na soubor System.Transactions – knihovny DLL  
  
1.  Na **projektu** nabídce vyberte možnost **přidat odkaz na**.  
  
2.  Vyberte **System.Transactions –** (na **.NET** kartě) a potom vyberte **OK**.  
  
     Odkaz na **System.Transactions** se přidá do projektu.  
  
## <a name="modify-the-code-in-the-bindingnavigators-saveitem-button"></a>Změňte kód v tlačítko SaveItem BindingNavigator  
 Pro první tabulky vyřadit do formuláře, je přidán kód ve výchozím nastavení `click` událostí uložení tlačítko <xref:System.Windows.Forms.BindingNavigator>. Budete muset ručně přidejte kód, který umožňuje aktualizovat všechny další tabulky. V tomto návodu budeme Refaktorovat existující uložit kód mimo uložení tlačítko obslužné rutiny události. Můžeme také vytvořit několik další metody, které poskytují funkce konkrétní aktualizaci založené na tom, zda řádek je nutné přidat nebo odstranit.  
  
#### <a name="to-modify-the-auto-generated-save-code"></a>Chcete-li upravit automaticky generovaný uložit kódu  
  
1.  Vyberte **Uložit** tlačítko **CustomersBindingNavigator** (tlačítko s ikonou disketovou jednotku).  
  
2.  Nahraďte `CustomersBindingNavigatorSaveItem_Click` metoda následujícím kódem:  
  
     [!code-vb[VbRaddataSaving#4](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#4](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_1.cs)]  
  
Pořadí pro vyřešení změny na souvisejících dat je následující:  
  
-   Odstraňte podřízené záznamy. (V takovém případě odstraňte záznamy z `Orders` tabulku.)  
  
-   Odstraňte nadřazené záznamy. (V takovém případě odstraňte záznamy z `Customers` tabulku.)  
  
-   Vložte nadřazené záznamy. (V tomto případě vložit záznamů `Customers` tabulku.)  
  
-   Vložte podřízené záznamy. (V tomto případě vložit záznamů `Orders` tabulku.)  
  
#### <a name="to-delete-existing-orders"></a>Chcete-li odstranit existující objednávky  
  
-   Přidejte následující `DeleteOrders` metodu **Form1**:  
  
     [!code-vb[VbRaddataSaving#5](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_2.vb)]
     [!code-csharp[VbRaddataSaving#5](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_2.cs)]  
  
#### <a name="to-delete-existing-customers"></a>Chcete-li odstranit stávající zákazníky služby  
  
-   Přidejte následující `DeleteCustomers` metodu **Form1**:  
  
     [!code-vb[VbRaddataSaving#6](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_3.vb)]
     [!code-csharp[VbRaddataSaving#6](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_3.cs)]  
  
#### <a name="to-add-new-customers"></a>Chcete-li přidat nové zákazníky  
  
-   Přidejte následující `AddNewCustomers` metodu **Form1**:  
  
     [!code-vb[VbRaddataSaving#7](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_4.vb)]
     [!code-csharp[VbRaddataSaving#7](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_4.cs)]  
  
#### <a name="to-add-new-orders"></a>Chcete-li přidat nové objednávky  
  
-   Přidejte následující `AddNewOrders` metodu **Form1**:  
  
     [!code-vb[VbRaddataSaving#8](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_5.vb)]
     [!code-csharp[VbRaddataSaving#8](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_5.cs)]  
  
## <a name="run-the-application"></a>Spuštění aplikace  
  
#### <a name="to-run-the-application"></a>Ke spuštění aplikace  
  
-   Vyberte **F5** ke spuštění aplikace.  
  
## <a name="see-also"></a>Viz také
[Postupy: ukládání dat pomocí transakce](../data-tools/save-data-by-using-a-transaction.md)  
[Uložit data zpět do databáze](../data-tools/save-data-back-to-the-database.md)