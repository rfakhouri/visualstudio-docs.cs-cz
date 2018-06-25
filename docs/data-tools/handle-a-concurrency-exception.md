---
title: Zpracování výjimky souběžnosti
ms.date: 09/11/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- concurrency control, exceptions
- datasets [Visual Basic], errors
- exception handling, concurrency issues
- data concurrency, walkthroughs
- updating datasets, errors
- concurrency control, walkthroughs
ms.assetid: 73ee9759-0a90-48a9-bf7b-9d6fc17bff93
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 179718223f181619a3121df8c88132a07e392678
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757172"
---
# <a name="handle-a-concurrency-exception"></a>Zpracování výjimky souběžnosti
Výjimky souběžnosti (<xref:System.Data.DBConcurrencyException>) se vyvolá, když dva uživatelé pokusí změnit stejná data v databázi ve stejnou dobu. V tomto návodu vytvoříte aplikace systému Windows, která ukazuje, jak zachytit <xref:System.Data.DBConcurrencyException>, vyhledejte řádek, který chybu způsobil a další strategie, jak se nezdařilo.

 Tento názorný postup vás provede následující proces:

1.  Vytvořte novou **formulářové aplikace Windows** projektu.

2.  Vytvořit novou sadu dat podle Northwind `Customers` tabulky.

3.  Vytvořte formulář s <xref:System.Windows.Forms.DataGridView> a zobrazí data.

4.  Vyplnění datové sady s daty z `Customers` tabulky v databázi Northwind.

5.  Použití **zobrazit Data tabulky** funkci v **Průzkumníka serveru** pro přístup k `Customers` dat a změňte záznam tabulky.

6.  Změňte stejné záznam na jinou hodnotu, aktualizujte datovou sadu a pokus o zápis do databáze, což vede k chybě souběžnosti vyvolaných změny.

7.  Catch – chyba, zobrazit různé verze na záznam, které uživateli umožňují určit, jestli chcete pokračovat a aktualizaci databáze nebo zrušit aktualizaci.

## <a name="prerequisites"></a>Požadavky
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.

1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [SQL Server Express stránky pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo pomocí **instalační program Visual Studio**. V **instalační program Visual Studio**, SQL Server Express LocalDB můžete nainstalovat jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.

2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz**.

       Otevře se okno editoru dotazů.

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.

       Po krátkou dobu dotaz dokončení spuštění a vytvoření databáze Northwind.

> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě v závislosti na nastavení active nebo na edici, který používáte. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

## <a name="create-a-new-project"></a>Vytvoření nového projektu
 Vaše návod začnete tak, že vytvoříte novou aplikaci Windows Forms.

#### <a name="to-create-a-new-windows-forms-application-project"></a>Chcete-li vytvořit nový projekt aplikace Windows Forms

1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu**.

2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Desktop**.

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.

4. Název projektu **ConcurrencyWalkthrough**a potom zvolte **OK**.

     **ConcurrencyWalkthrough** je vytvořen a přidán do projektu **Průzkumníku**, a otevře se nový formulář v návrháři.

## <a name="create-the-northwind-dataset"></a>Vytvořit datová sada Northwind
 V této části vytvoříte datovou sadu s názvem `NorthwindDataSet`.

#### <a name="to-create-the-northwinddataset"></a>Chcete-li vytvořit NorthwindDataSet

1.  Na **Data** nabídce zvolte **přidat nová Data zdroj**.

     [Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png) otevře.

2.  Na **zvolte typ zdroje dat** obrazovku, vyberte **databáze**.

3.  Vyberte připojení k ukázková databáze Northwind ze seznamu dostupných připojení. Pokud připojení není k dispozici v seznamu připojení, vyberte **nové připojení**.

    > [!NOTE]
    >  Pokud se připojujete k lokálním databázovém souboru, vyberte **ne** když se zobrazí dotaz, pokud byste chtěli soubor přidat do projektu.

4.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace** obrazovku, vyberte **Další**.

5.  Rozbalte **tabulky** uzel a vyberte možnost `Customers` tabulky. Výchozí název pro datovou sadu musí být `NorthwindDataSet`.

6.  Vyberte **Dokončit** přidat datovou sadu do projektu.

## <a name="create-a-data-bound-datagridview-control"></a>Vytvoření ovládacího prvku DataGridView vázané na data
 V této části vytvoříte <xref:System.Windows.Forms.DataGridView> přetažením **zákazníci** položky z **zdroje dat** okna do svého formuláře systému Windows.

#### <a name="to-create-a-datagridview-control-that-is-bound-to-the-customers-table"></a>Chcete-li vytvořit DataGridView – ovládací prvek, který je vázaný na tabulku zákazníků

1.  Na **Data** nabídce zvolte **zobrazit zdroje dat** otevřete **okno zdroje dat**.

2.  V **zdroje dat** okno, rozbalte **NorthwindDataSet** uzel a potom vyberte **zákazníci** tabulky.

3.  Vyberte šipku dolů na uzlu tabulky a pak vyberte **DataGridView** v rozevíracím seznamu.

4.  Přetažením v tabulce na na prázdnou oblast formuláře.

     A <xref:System.Windows.Forms.DataGridView> ovládací prvek s názvem `CustomersDataGridView` a <xref:System.Windows.Forms.BindingNavigator> s názvem `CustomersBindingNavigator` jsou přidány do formulář, který je vázána <xref:System.Windows.Forms.BindingSource>. To je, pak vázána `Customers` tabulky v `NorthwindDataSet`.

## <a name="test-the-form"></a>Testování formuláře
 Nyní můžete otestovat formuláře a ujistěte se, že se chová jako očekávány maximálně tento bod.

#### <a name="to-test-the-form"></a>Postup testování formuláře

1.  Vyberte **F5** ke spuštění aplikace.

     Formulář se zobrazí s <xref:System.Windows.Forms.DataGridView> ovládací prvek v něm, který naplní se data z `Customers` tabulky.

2.  Na **ladění** nabídce vyberte možnost **Zastavte ladění**.

## <a name="handle-concurrency-errors"></a>Zpracování chyb souběžnosti
 Způsob zpracování chyb závisí na konkrétní obchodní pravidla, které řídí vaší aplikace. V tomto návodu použijeme následující strategie jako příklad určuje způsob zpracování chyba souběžnosti.

 Aplikace zobrazí uživatele s tři verze záznamu:

-   Na aktuální záznam v databázi

-   Původní záznam, který je načten do datové sady

-   Navrhované změny v datové sadě

Uživatel je pak možné přepsat databázi navrhované verzí, nebo zrušit aktualizaci a aktualizovat datovou sadu s novými hodnotami z databáze.

#### <a name="to-enable-the-handling-of-concurrency-errors"></a>Chcete-li povolit řešení souběžného zpracování chyb

1.  Vytvořte obslužnou rutinu vlastní chyby.

2.  Zobrazí možnosti pro uživatele.

3.  Zpracování odpovědi uživatele.

4.  Znovu odeslal aktualizaci nebo obnovení dat v datové sadě.

### <a name="add-code-to-handle-the-concurrency-exception"></a>Přidat kód pro zpracování výjimky souběžnosti
 Když se pokusíte provést aktualizace a je vyvolána výjimka, obvykle chcete něco s informacemi, které zajišťuje vyvolané výjimky.

 V této části přidáte kód, který se pokouší aktualizovat databázi. Také zpracovat žádné <xref:System.Data.DBConcurrencyException> , může být vyvolána, a také všechny ostatní výjimky.

> [!NOTE]
>  `CreateMessage` a `ProcessDialogResults` metody jsou přidány později v tomto návodu.

##### <a name="to-add-error-handling-for-the-concurrency-error"></a>Přidání zpracování chyb pro chyba souběžnosti

1.  Přidejte následující kód níže `Form1_Load` metoda:

     [!code-csharp[VbRaddataConcurrency#1](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_1.cs)]
     [!code-vb[VbRaddataConcurrency#1](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_1.vb)]

2.  Nahraďte `CustomersBindingNavigatorSaveItem_Click` metoda k volání `UpdateDatabase` metoda tak, aby vypadala takto:

     [!code-csharp[VbRaddataConcurrency#2](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_2.cs)]
     [!code-vb[VbRaddataConcurrency#2](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_2.vb)]

### <a name="display-choices-to-the-user"></a>Zobrazit možnosti pro uživatele
 Kód, který jste právě napsali volání `CreateMessage` postup zobrazení informací o chybách pro uživatele. Pro účely tohoto postupu použít okno se zprávou má zobrazit různé verze v záznamu uživatele. To umožňuje uživatelům zvolit, zda chcete přepsat záznam změny nebo zrušit úpravy. Jakmile uživatel vybere možnost (kliknutím na tlačítko) v okně se zprávou, je předán odpovědi `ProcessDialogResult` metoda.

##### <a name="to-create-the-message-to-display-to-the-user"></a>Chcete-li vytvořit zprávu, která se zobrazí uživateli

-   Vytvořit zprávu přidáním následující kód, který **Editor kódu**. Zadejte níže tento kód `UpdateDatabase` metoda.

     [!code-csharp[VbRaddataConcurrency#4](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_3.cs)]
     [!code-vb[VbRaddataConcurrency#4](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_3.vb)]

### <a name="process-the-users-response"></a>Zpracovat odpověď uživatele
 Musíte taky kód se zpracovat odpověď uživatele do pole zpráva. Možnosti jsou buď na aktuální záznam v databázi přepsat navrhované změny, nebo zrušte místní změny a aktualizujte tabulku dat s záznam, který je aktuálně v databázi. Pokud se uživatel rozhodne **Ano**, <xref:System.Data.DataTable.Merge%2A> metoda je volána s *preserveChanges* argument nastaven na hodnotu `true`. To způsobí, že pokus o aktualizaci být úspěšné, protože původní verzi záznamu teď odpovídající záznam v databázi.

##### <a name="to-process-the-user-input-from-the-message-box"></a>Při zpracování uživatele vstup z okno se zprávou

-   Přidejte následující kód pod kód, který byl přidán v předchozí části.

     [!code-csharp[VbRaddataConcurrency#3](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_4.cs)]
     [!code-vb[VbRaddataConcurrency#3](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_4.vb)]

## <a name="test-the-form"></a>Testování formuláře
 Nyní můžete otestovat formuláře a ujistěte se, že se chová podle očekávání. K simulaci narušení souběžnosti, změníte po vyplnění NorthwindDataSet data v databázi.

#### <a name="to-test-the-form"></a>Postup testování formuláře

1.  Vyberte **F5** ke spuštění aplikace.

2.  Jakmile se zobrazí formulář, necháte spuštěné a přepněte do prostředí Visual Studio IDE.

3.  Na **zobrazení** nabídce zvolte **Průzkumníka serveru**.

4.  V **Průzkumníka serveru**, rozbalte připojení, vaše aplikace používá a potom rozbalte **tabulky** uzlu.

5.  Klikněte pravým tlačítkem myši **zákazníci** tabulky a potom vyberte **zobrazit Data tabulky**.

6.  V prvním záznamu (`ALFKI`) změnit `ContactName` k `Maria Anders2`.

    > [!NOTE]
    >  Přejděte na jiný řádek potvrzení změn.

7.  Přepnout `ConcurrencyWalkthrough`je spuštěna formuláře.

8.  V prvním záznamu na formuláři (`ALFKI`), změnit`ContactName` k `Maria Anders1`.

9. Vyberte **Uložit** tlačítko.

     Chyba souběžnosti se vyvolá, a zobrazí se okno se zprávou.

10. Výběr **ne** zruší aktualizace a aktualizace datovou sadu s hodnotami, které jsou aktuálně v databázi. Výběr **Ano** navržená hodnota zapisuje do databáze.

## <a name="see-also"></a>Viz také:

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)