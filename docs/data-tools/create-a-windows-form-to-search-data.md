---
title: Vytvoření formuláře Windows k vyhledávání dat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Windows Forms, searching data
- Windows Forms, displaying data
- parameters, displaying filtered data
- data [Visual Studio], parameterizing queries
- data [Visual Studio], searching
ms.assetid: 65ca79a9-7458-466c-af55-978cd24c549e
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d725459f3623803cbcd02d83e3050ccd9c7f6aed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-windows-form-to-search-data"></a>Vytvoření formuláře Windows k vyhledávání dat
Běžný scénář aplikace je zobrazení vybrané dat ve formuláři. Například můžete chtít zobrazit objednávky pro konkrétního zákazníka nebo podrobnosti o určitém pořadí. V tomto scénáři uživatel zadá informace do formuláře a potom je dotaz proveden se vstupem uživatele jako parametr; To znamená je vybraná data, na základě parametrizovaného dotazu. Dotaz vrátí jenom data, která splňuje kritéria zadaná uživatelem. Tento návod ukazuje, jak vytvořit dotaz, který vrátí zákazníků v konkrétním městě a upravit uživatelské rozhraní, aby uživatelé mohli zadejte název města a stiskněte tlačítko provést dotaz.  
  
 Použití parametrických dotazů pomáhá efektivní aplikace tím, že databáze je vhodné v práci – rychlé filtrování záznamů. Naproti tomu pokud vyžádáte k tabulce celé databáze, přenos přes síť a potom pomocí aplikací logiky najít požadované záznamy, aplikace se může stát pomalé a neefektivní.  
  
 Parametrizované dotazy můžete přidat všechny TableAdapter (a ovládací prvky přijmout hodnoty parametrů a provést dotaz), pomocí **Tvůrce kritérií vyhledávání** dialogové okno. Otevřete dialogové okno výběrem **přidat dotazu** příkaz na **Data** nabídky (nebo na jakékoli TableAdapter inteligentních značek).  
  
 Úkoly v tomto návodu zahrnují:  
  
-   Vytvoření nového projektu aplikace Windows Forms.  
  
-   Vytváření a konfiguraci zdroje dat v aplikaci s **konfigurace zdroje dat** průvodce.  
  
-   Typ položky v nastavení **zdroje dat**okno.  
  
-   Vytváření ovládacích prvků, které zobrazují data tak, že přetáhnete položky z **zdroje dat** okna do formuláře.  
  
-   Přidání ovládacích prvků pro zobrazení dat ve formuláři.  
  
-   Dokončení **Tvůrce kritérií vyhledávání** dialogové okno.  
  
-   Zadání parametrů do formuláře a provádění parametrizovaného dotazu.  
  
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
 Prvním krokem je vytvoření **formulářové aplikace Windows**. Název přiřazení do projektu je nepovinný v tomto kroku, ale můžete budete pojmenujte ho tady vzhledem k tomu, že budete později uložení projektu.  
  
#### <a name="to-create-the-new-windows-forms-application-project"></a>Chcete-li vytvořit nový projekt aplikace Windows Forms  
  
1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .  
  
2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.  

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.  

4. Název projektu **WindowsSearchForm**a potom zvolte **OK**. 
  
     **WindowsSearchForm** je vytvořen a přidán do projektu **Průzkumníku řešení**.  
  
## <a name="create-the-data-source"></a>Vytvoření zdroje dat  
Tento krok vytvoří zdroj dat z databáze pomocí **konfigurace zdroje dat** průvodce.  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.  
  
2.  V **zdroje dat** vyberte **přidat nový zdroj dat** spustit **konfigurace zdroje dat** průvodce.  
  
3.  Vyberte **databáze** na **zvolte typ zdroje dat** a pak klikněte na tlačítko **Další**.  
  
4.  Na **zvolit datové připojení** proveďte jednu z následujících akcí:  
  
    -   Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.  
  
    -   Vyberte **nové připojení** ke spuštění **přidat či upravit připojení** dialogové okno.  
  
5.  Pokud vaše databáze vyžaduje heslo, vyberte možnost obsahují citlivá data, a pak klikněte na **Další**.  
  
6.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.  
  
7.  Na **zvolte databázové objekty** rozbalte **tabulky** uzlu.  
  
8.  Vyberte **zákazníci** tabulky a potom klikněte na **Dokončit**.  
  
     **NorthwindDataSet** se přidá do projektu a **zákazníci** tabulky se zobrazí v **zdroje dat** okno.  
  
## <a name="create-the-form"></a>Vytvoření formuláře  
 Ovládací prvky vázané na data můžete vytvořit tak, že přetáhnete položky z **zdroje dat** okna do svého formuláře.  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>Vytvoření ovládacích prvků vázaných na data ve formuláři  
  
1.  Rozbalte **zákazníci** uzel v **zdroje dat** okno.  
  
2.  Přetáhněte **zákazníci** uzlu z **zdroje dat** okna do svého formuláře.  
  
     A <xref:System.Windows.Forms.DataGridView> a pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>) pro procházení záznamů jsou zobrazena na formuláři. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent.  
  
## <a name="add-parameterization-search-functionality-to-the-query"></a>Chcete do dotazu přidat Parametrizace (funkce vyhledávání)  
 Můžete přidat klauzuli WHERE dotazu na původní pomocí **Tvůrce kritérií vyhledávání** dialogové okno.  
  
#### <a name="to-create-a-parameterized-query-and-controls-to-enter-the-parameters"></a>Vytvoření parametrického dotazu a ovládacích prvků k zadání parametrů  
  
1.  Vyberte <xref:System.Windows.Forms.DataGridView> řízení a potom vyberte **přidat dotazu** na **Data** nabídky.  
  
2.  Typ `FillByCity` v **nový název dotazu** oblast na **Tvůrce kritérií vyhledávání** dialogové okno.  
  
3.  Přidat `WHERE City = @City` k dotazu v **Text dotazu** oblasti.  
  
     Dotaz by měl vypadat přibližně takto:  
  
     ```sql
     SELECT CustomerID, CompanyName, ContactName, ContactTitle,  
          Address, City, Region, PostalCode, Country, Phone, Fax  
     FROM Customers
     WHERE City = @City  
     ```
  
    > [!NOTE]
    >  Přístup a OLE DB zdroje dat použít znaky otazníku ('? ') k označení parametrů, takže klauzule WHERE bude vypadat takto: `WHERE City = ?`.  
  
4.  Klikněte na tlačítko **OK** zavřete **Tvůrce kritérií vyhledávání** dialogové okno.  
  
     A **FillByCityToolStrip** je přidán do formuláře.  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Spuštění aplikace otevře připravena převzít parametr jako vstup formuláře.  
  
#### <a name="to-test-the-application"></a>Testování aplikace  
  
1.  Stisknutím klávesy F5 spusťte aplikaci.  
  
2.  Typ **Londýn** do **města** textového pole a pak klikněte na tlačítko **FillByCity**.  
  
     Datová mřížka naplněný zákazníků, které splňují kritéria. V tomto příkladu datové mřížce se zobrazí pouze zákazníků, kteří mají hodnotu **Londýn** v jejich **města** sloupce.  
  
## <a name="next-steps"></a>Další kroky  
 V závislosti na požadavcích vaší aplikace existuje několik kroků, které můžete chtít provést po vytvoření parametrizovaného formuláře. Mezi vylepšení, která je možné pro tento návod provést, patří:  
  
-   Přidání ovládacích prvků, které zobrazují data v relaci. Další informace najdete v tématu [vztahy v datových sadách](relationships-in-datasets.md).  
  
-   Úpravy datovou sadu, která přidat nebo odebrat databázové objekty. Další informace najdete v tématu [vytvořit a nakonfigurovat datové sady](../data-tools/create-and-configure-datasets-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)