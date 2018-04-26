---
title: Uložení dat do databáze (více tabulek)
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], updating
ms.assetid: 7ebe03da-ce8c-4cbc-bac0-a2fde4ae4d07
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5be0cccd71a356a78a04c3d15cdb2f080e30c9e4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="save-data-to-a-database-multiple-tables"></a>Uložení dat do databáze (více tabulek)
Jeden z nejběžnějších scénářů při vývoji aplikace je k zobrazení dat ve formuláři v aplikaci Windows, upravte údaje a odeslat aktualizovaná data zpět do databáze. Tento návod vytvoří formulář, který zobrazuje data ze dvou souvisejících tabulek a ukazuje, jak upravit záznamy a uložte změny zpět do databáze. Tento příklad používá `Customers` a `Orders` tabulky z ukázková databáze Northwind.

 Data můžete uložit ve vaší aplikaci zpět do databáze při volání `Update` metoda TableAdapter. Při přetažení z tabulky **zdroje dat** okna do formuláře, kód, který je nutné pro ukládání dat se automaticky přidá. Libovolné další tabulky, které jsou přidány do formuláře vyžadují ruční přidání tohoto kódu. Tento návod ukazuje, jak přidat kód pro uložení aktualizací z více než jedna tabulka.

> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě v závislosti na nastavení active nebo na edici, který používáte. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

 Úkoly v tomto návodu zahrnují:

-   Vytvoření nové **formulářové aplikace Windows** projektu.

-   Vytváření a konfiguraci zdroje dat v aplikaci s [Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png).

-   Nastavení ovládacích prvků položek v [okno zdroje dat](add-new-data-sources.md). Další informace najdete v tématu [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

-   Vytváření ovládacích prvků vázaných na data tak, že přetáhnete položky z **zdroje dat** okna do svého formuláře.

-   Úpravy několik záznamů v každé tabulce v datové sadě.

-   Změny kódu odeslat aktualizovaná data zpět do databáze v datové sadě.

## <a name="prerequisites"></a>Požadavky
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.

1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [SQL Server Express stránky pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.

2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .

       Otevře se okno editoru dotazů.

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.

## <a name="create-the-windows-forms-application"></a>Vytvoření aplikace Windows Forms
 Prvním krokem je vytvoření **formulářové aplikace Windows**. Přiřazování název projektu během tento krok je nepovinný, ale jsme budete pojmenujte ho vzhledem k tomu, že jsme budete později uložit projektu.

#### <a name="to-create-the-new-windows-forms-application-project"></a>Chcete-li vytvořit nový projekt aplikace Windows forms

1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .

2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.

4. Název projektu **UpdateMultipleTablesWalkthrough**a potom zvolte **OK**.

     **UpdateMultipleTablesWalkthrough** je vytvořen a přidán do projektu **Průzkumníku řešení**.

## <a name="create-the-data-source"></a>Vytvoření zdroje dat
 Tento krok vytvoří zdroj dat z databáze Northwind pomocí **Průvodce konfigurací zdroje dat**. Musíte mít přístup k ukázková databáze Northwind k vytvoření připojení. Informace o nastavení ukázková databáze Northwind najdete v tématu [postupy: Instalace ukázkové databáze](../data-tools/installing-database-systems-tools-and-samples.md).

#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat

1.  Na **Data** nabídce vyberte možnost **zobrazit zdroje dat**.

2.  V **zdroje dat** vyberte**přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.

3.  Na **zvolte typ zdroje dat** obrazovku, vyberte **databáze**a potom vyberte **Další**.

4.  Na **zvolit datové připojení** proveďte obrazovky, jednu z následujících akcí:

    -   Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.

         -nebo-

    -   Vyberte **nové připojení** otevřete **přidat či upravit připojení** dialogové okno.

5.  Pokud vaše databáze vyžaduje heslo, vyberte možnost obsahují citlivá data a pak vyberte **Další**.

6.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace**, vyberte **Další**.

7.  Na **zvolte databázové objekty**obrazovky, rozbalte **tabulky** uzlu.

8.  Vyberte **zákazníci** a **objednávky** tabulky a potom vyberte **Dokončit**.

     **NorthwindDataSet** se přidá do projektu, a tabulky se zobrazí v **zdroje dat** okno.

## <a name="set-the-controls-to-be-created"></a>Nastavit vytvořit ovládací prvky
 V tomto návodu data v `Customers` tabulka je v **podrobnosti** rozložení, kde se zobrazí data v jednotlivých ovládacích prvků. Data z `Orders` tabulka je v **mřížky** rozložení, který se zobrazí v <xref:System.Windows.Forms.DataGridView> ovládacího prvku.

#### <a name="to-set-the-drop-type-for-the-items-in-the-data-sources-window"></a>Chcete-li nastavit typ pro položky v okně zdroje dat

1.  V **zdroje dat** okno, rozbalte **zákazníci** uzlu.

2.  Na **zákazníci** uzlu, vyberte **podrobnosti** ovládací prvek seznamu můžete změnit řízení **zákazníci** tabulka, která se jednotlivých ovládacích prvků. Další informace najdete v tématu [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

## <a name="create-the-data-bound-form"></a>Vytvoření formuláře vázané na data
 Ovládací prvky vázané na data můžete vytvořit tak, že přetáhnete položky z **zdroje dat** okna do svého formuláře.

#### <a name="to-create-data-bound-controls-on-the-form"></a>Vytvoření ovládacích prvků vázaných na data ve formuláři

1.  Přetáhněte hlavní **zákazníci** uzlu z **zdroje dat** okna do **Form1**.

     Ovládací prvky vázané na data s popisky jsou zobrazena na formuláři, společně s pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>) pro procházení záznamů. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `CustomersTableAdapter`, <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent.

2.  Přetáhněte související **objednávky** uzlu z **zdroje dat** okna do **Form1**.

    > [!NOTE]
    >  Související **objednávky** uzlu se nachází pod **Fax** sloupce a podřízený uzel **zákazníci** uzlu.

     A <xref:System.Windows.Forms.DataGridView> řízení a pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>) pro procházení záznamů jsou zobrazena na formuláři. `OrdersTableAdapter` a <xref:System.Windows.Forms.BindingSource> se zobrazí v okně komponent.

## <a name="add-code-to-update-the-database"></a>Přidejte kód k aktualizaci databáze
 Databázi můžete aktualizovat pomocí volání `Update` metody **zákazníci** a **objednávky** TableAdapters. Ve výchozím nastavení, obslužné rutiny události pro **Uložit** tlačítko<xref:System.Windows.Forms.BindingNavigator> se přidá do kódu formuláře k odesílání aktualizací do databáze. Tento postup upravuje kód k odesílání aktualizací ve správném pořadí. Tím se eliminuje možnost vyvolání chyby referenční integrity. Kód také implementuje pomocí zabalení volání aktualizace v bloku try-catch – zpracování chyb. Můžete upravit kód, aby vyhovovaly potřebám vaší aplikace.

> [!NOTE]
>  Tento názorný postup pro přehlednost, nepoužívá transakce. Ale pokud aktualizujete dva nebo více souvisejících tabulek, zahrnout veškerou logiku aktualizace v rámci transakce. Transakce je proces, který zaručuje, že všechny související změny databáze jsou úspěšné, než jsou všechny změny potvrzeny. Další informace najdete v tématu [transakce a souběžnost](/dotnet/framework/data/adonet/transactions-and-concurrency).

#### <a name="to-add-update-logic-to-the-application"></a>Chcete-li přidat logiku aktualizace do aplikace

1.  Vyberte **Uložit** tlačítko <xref:System.Windows.Forms.BindingNavigator>. Tím se otevře editoru kódu `bindingNavigatorSaveItem_Click` obslužné rutiny události.

2.  Nahraďte kód v obslužné rutiny události pro volání `Update` metody související TableAdapters. Následující kód nejdřív vytvoří tři dočasná data tabulky pro uložení aktualizované informace pro každý <xref:System.Data.DataRowState> (<xref:System.Data.DataRowState.Deleted>, <xref:System.Data.DataRowState.Added>, a <xref:System.Data.DataRowState.Modified>). Aktualizace jsou pak spusťte ve správném pořadí. Kód by měl vypadat asi takto:

     [!code-vb[VbRaddataSaving#10](../data-tools/codesnippet/VisualBasic/save-data-to-a-database-multiple-tables_1.vb)]
     [!code-csharp[VbRaddataSaving#10](../data-tools/codesnippet/CSharp/save-data-to-a-database-multiple-tables_1.cs)]

## <a name="test-the-application"></a>Testování aplikace

#### <a name="to-test-the-application"></a>Testování aplikace

1.  Vyberte **F5**.

2.  Některé změny dat jeden nebo více záznamů v každé tabulce.

3.  Vyberte **Uložit** tlačítko.

4.  Zkontrolujte hodnoty v databázi a ověřte, že změny nebyly uloženy.


## <a name="see-also"></a>Viz také

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)