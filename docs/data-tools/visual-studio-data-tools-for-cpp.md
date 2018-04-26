---
title: Data nástroje sady Visual Studio pro jazyk C++
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CPP
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
- cplusplus
ms.openlocfilehash: fa732c8b2fbf55b1cb2c8b80a06cf1ab18d6b50c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="visual-studio-data-tools-for-c"></a>Data nástroje sady Visual Studio pro jazyk C++

Nativní C++ často poskytují nejrychlejší výkon při přístupu k zdroje dat. Data nástrojů pro aplikací C++ v sadě Visual Studio však nejsou bohaté, protože je pro aplikace .NET. Například windows zdroje dat nelze použít pro přetažení zdroje dat na návrhovou plochu C++. Pokud potřebujete relační objekt vrstvy, budete muset napsat vlastní, nebo použijte produkt jiného výrobce.  Totéž platí pro datovou vazbu funkce, i když se aplikace, které používají knihovnu Microsoft Foundation Class library můžete použít některé databázové třídy, společně s dokumenty a zobrazení, uložit do paměti data a zobrazit ji pro uživatele. Další informace najdete v tématu [přístup k datům v jazyce Visual C++](/cpp/data/data-access-in-cpp).

Pro připojení k databázím SQL, můžete použít nativních aplikací C++ ovladače ODBC a OLE DB a ADO zprostředkovatele, které jsou součástí systému Windows. Tyto můžete připojit k jakékoli databázi, která podporuje tato rozhraní. Ovladač ODBC je standardní. OLE DB slouží k zajištění zpětné kompatibility. Další informace o těchto technologií dat najdete v tématu [Windows Data Access Components](https://msdn.microsoft.com/library/windows/desktop/aa968814.aspx).

Využít výhod vlastních funkcí v systému SQL Server 2005 a novější, použijte [SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client). Nativní klient také obsahuje ovladač ODBC systému SQL Server a SQL Server zprostředkovateli OLE DB v jedné nativní dynamická knihovna (DLL). Tyto podporovat aplikace pomocí nativního kódu rozhraní API (rozhraní ODBC, OLE DB a ADO) systému Microsoft SQL Server.  SQL Server Native Client nainstaluje SQL Server Data Tools. Průvodce programováním se zde: [SQL serveru Nativní klient programování](/sql/relational-databases/native-client/sql-server-native-client-programming).

## <a name="to-connect-to-localdb-through-odbc-and-sql-native-client-from-a-c-application"></a>Pro připojení k localDB přes rozhraní ODBC a nativní klient SQL z aplikace C++

1.  Nainstalujte nástroje SQL Server Data Tools.

2.  Pokud potřebujete ukázkovou databázi SQL pro připojení k, databázi Northwind stáhněte a rozbalte ho do nového umístění.

3.  Pomocí SQL Server Management Studio pro připojení souboru rozbalené Northwind.mdf na instanci localDB. Při spuštění služby SQL Server Management Studio připojte \MSSQLLocalDB (localdb).

     ![Dialogové okno připojení přes SSMS](../data-tools/media/raddata-ssms-connect-dialog.png "raddata SSMS připojit dialogové okno")

     Klikněte pravým tlačítkem na uzel localdb v levém podokně a zvolte **Attach**.

     ![Aplikace SSMS připojit databázi](../data-tools/media/raddata-ssms-attach-database.png "raddata SSMS připojit databáze")

4.  Stažení ukázky ODBC Windows SDK a rozbalte ho do nového umístění. Tento příklad ukazuje základní rozhraní ODBC příkazy, které se používají pro připojení k databázi a problém dotazy a příkazy. Další informace o těchto funkcí v [Microsoft připojení ODBC (Open Database)](/sql/odbc/microsoft-open-database-connectivity-odbc). Při načítání nejprve řešení (se nachází v C++ složce), Visual Studio navrhne upgrade řešení na aktuální verzi sady Visual Studio. Klikněte na tlačítko **Ano**.

5.  Použít nativní klient, musíte její hlavičkový soubor a soubor lib. Tyto soubory obsahují funkce a definice specifické pro systém SQL Server, nad rámec ODBC funkce definované v sql.h. V **projektu** > **vlastnosti** > **adresáře VC ++**, přidejte adresář include následující:

**%ProgramFiles%\Microsoft SQL Server\110\SDK\Include**

A tento adresář knihovny:

**%ProgramFiles%\Microsoft SQL Server\110\SDK\Lib**

6.  Přidejte tyto řádky odbcsql.cpp. #Define brání důležité definice OLE DB z kompilován.

    ```cpp
    #define _SQLNCLI_ODBC_
    #include <sqlncli.h>
    ```

    Všimněte si, ukázka nepoužívá ve skutečnosti všechny funkce nativního klienta, takže nejsou předchozí kroky nezbytné k zkompilování a spuštění. Ale pro vás k použití této funkce je nyní nakonfigurována projektu. Další informace najdete v tématu [SQL serveru Nativní klient programování](/sql/relational-databases/native-client/sql-server-native-client).

7.  Určete, který ovladač pro použití v subsystému ODBC. Ukázka předá atribut ovladač připojovacího řetězce v jako argument příkazového řádku. V **projektu** > **vlastnosti** > **ladění**, přidejte tento argument příkazu:

    ```cpp
    DRIVER="SQL Server Native Client 11.0"
    ```

8.  Stisknutím klávesy F5 sestavení a spuštění aplikace. Měli byste vidět dialogové okno z ovladače, která vás vyzve k databázi. Zadejte `(localdb)\MSSQLLocalDB`a zkontrolujte **použít důvěryhodné připojení**. Press **OK**. Měli byste vidět Konzola se zpráva s informací, úspěšné připojení. Měli byste taky vidět příkazového řádku můžete zadat v příkazu jazyka SQL. Následující obrazovka ukazuje příklad dotazu a výsledky:

     ![ODBC ukázkový dotaz výstup](../data-tools/media/raddata-odbc-sample-query-output.png "raddata ODBC ukázkový dotaz výstup")

## <a name="see-also"></a>Viz také

- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)