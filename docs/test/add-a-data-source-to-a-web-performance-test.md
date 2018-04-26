---
title: Přidání zdroje dat do testu výkonnosti webu v sadě Visual Studio
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, walkthroughs
- Web performance tests, data binding (database)
ms.assetid: 2ada376d-f168-455d-9643-6acb535360c1
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 6245647ca0af639bdd960e43f2c1adeed3982562
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="add-a-data-source-to-a-web-performance-test"></a>Přidání zdroje dat do testu výkonnosti webu

Vázání dat různé hodnoty pro stejný test, třeba zajistit, aby poskytují různé hodnoty do svého formuláře odeslat parametry.

 ![Vazba dat do testu výkonnosti webu](../test/media/web_test_databinding_conceptual.png)

 Vytvoříme pomocí ukázkové aplikace ASP.NET. Má tři stránky ASPX – výchozí stránku, Red stránky a Blue stránku. Výchozí stránka má ovládací prvek přepínač zvolit red nebo blue a tlačítko pro odeslání. Další dvě stránky .aspx jsou velmi jednoduché. Jeden má popisek s názvem Red a dalších má popisek s názvem Blue. Když zvolíte odeslat na stránku výchozího zobrazujeme jedním z dalších stránek. Si můžete stáhnout [ColorWebApp](http://code.msdn.microsoft.com/Sample-ColorWebApp-76ff7506) ukázkové nebo postupujte podle společně s webovou aplikaci.

 ![Spuštění webové aplikace má být testována](../test/media/web_test_databinding_runwebapp.png)

 Řešení musí rovněž zahrnovat testu výkonnosti webu, který umožňuje prostřednictvím stránky webové aplikace.

 ![Řešení s testu výkonnosti webu](../test/media/web_test_databinding_solution.png)

## <a name="create-a-sql-database"></a>Vytvoření databáze SQL

1. Pokud nemáte Visual Studio Enterprise, cand můžete ji stáhnout z [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky.

2. Vytvoření databáze SQL.

     ![Přidat novou databázi SQL.](../test/media/web_test_databinding_sql_addnewdb.png)

3. Vytvořte projekt databáze.

     ![Vytvoření nového projektu z databáze](../test/media/web_test_databinding_sql_addnewdbproject.png)

4. Přidání tabulky do projekt databáze.

     ![Přidá novou tabulku na projekt databáze](../test/media/web_test_databinding_sql_addnewdbtablename.png)

5. Přidáte pole do tabulky.

     ![Přidat pole do tabulky](../test/media/web_test_databinding_sql_addnewdbaddfields.png)

6. Publikujte k databázovému projektu.

     ![Publikování databáze projektu v Průzkumníku řešení](../test/media/web_test_databinding_sql_addnewdbpublish.png)

7. Přidání dat do polí.

     ![Přidání dat do pole](../test/media/web_test_databinding_sql_addnewfieldsadddata.png)

## <a name="add-the-data-source"></a>Přidejte tento zdroj dat

1. Přidání zdroje dat.

     ![Přidat zdroje dat do testu výkonnosti webu](../test/media/web_test_databinding_sql_adddatasource.png)

2. Vyberte typ zdroje dat a pojmenujte ji.

     ![Název databáze zdroje](../test/media/web_test_databinding_sql_adddatasourcedialog.png)

3. Umožňuje vytvořte připojení.

     ![Zvolte nové připojení](../test/media/web_test_databinding_sql_adddatasourcedialogconnectionnew.png)

     Zadejte podrobnosti připojení.

     ![Zadejte vlastnosti připojení databáze SQL](../test/media/web_test_databinding_sql_adddatasourcedialogconnection.png)

4. Vyberte tabulku, kterou chcete použít pro svůj test.

     ![Přidat jako zdroj dat v tabulce barev](../test/media/web_test_databinding_sql_adddatasourcedialogaddtable.png)

     Tabulka je vázána na test.

     ![Přidat uzel zdroje dat do testu výkonnosti webu](../test/media/web_test_databinding_requestnodeadded_mdb.png)

5. Uložte test.

## <a name="bind-the-data"></a>Vytvoření vazby data

1. Vytvoření vazby ColorName pole.

     ![Vytvoření vazby pole ColorName RadioButtonList1 hodnotu](../test/media/web_test_databinding_sql_binddatasource.png)

2. V Průzkumníku řešení otevřete soubor Local.testsettings a vyberte jeden spustit na možnost řádek zdroje dat.

     ![Úpravy souborů nastavení testů](../test/media/web_test_databinding_sql_testsettings.png)

3. Uložte testu výkonnosti webu.

## <a name="run-the-test-with-the-data"></a>Spusťte test s daty

1. Spuštění testu.

     ![Spuštění testu výkonnosti webu Ověření vazby](../test/media/web_test_databinding_sql_runtest.png)

     Pro každý řádek dat se zobrazují dvě spustí. Spustit 1 odešle požadavek stránku Red.aspx a spustit 2 odešle požadavek na stránce Blue.aspx.

     ![Výsledky testu](../test/media/web_test_databinding_sql_runresults.png)

     Při vytvoření vazby ke zdroji dat, může narušit výchozí pravidlo adresa URL odpovědi. V takovém případě Chyba v spustit 2 je způsobená pravidla, která očekává Red.aspx stránku z původní testovací záznam, ale datové vazby teď ho přesměruje na stránku Blue.aspx.

2. Opravte chybu ověření adresa URL odpovědi ověřovací pravidlo odstranit a znovu spustit test.

     ![Odstranit pravidlo ověření adresa URL odpovědi](../test/media/web_test_databinding_sql_deleteresponseurl.png)

     Použití datových vazeb předá teď testu výkonnosti webu.

     ![Test předá použití datových vazeb](../test/media/web_test_databinding_sql_deleteresponseurlrunresults.png)

## <a name="q--a"></a>Dotazy a odpovědi

### <a name="q-what-databases-can-i-use-as-a-data-source"></a>Otázka: jaký databáze můžete použít jako zdroj dat?

**Odpověď:** můžete použít následující:

- Microsoft SQL Azure.

- Všechny verze systému Microsoft SQL Server 2005 nebo novější.

- Soubor databáze Microsoft SQL Server (včetně SQL Express).

- Microsoft ODBC.

- Soubor aplikace Microsoft Access pomocí poskytovatele rozhraní .NET Framework pro OLE DB.

- Oracle 7.3, 8i, 9i nebo 10g.

### <a name="q-how-do-i-use-a-comma-separated-value-csv-text-file-as-a-data-source"></a>Otázka: jak používat textový soubor čárkami oddělených hodnot (CSV) jako zdroj dat?

**Odpověď:** tady je jak:

1. Vytvořte složku pro uspořádání artefakty databáze projekty a přidejte položku.

     ![Přidání nové položky ke složce Data](../test/media/web_test_databinding_foldernewitem.png "Web_Test_DataBinding_FolderNewItem")

2. Vytvořte textový soubor.

     ![Název nového textového souboru ColorData.csv](../test/media/web_test_databinding_foldernewitemtextfile.png "Web_Test_DataBinding_FolderNewItemTextFile")

3. Upravit textový soubor a přidejte následující:

    ```
    ColorId, ColorName
    0,Red
    1,Blue
    ```

4. Postupujte podle kroků v [vazby dat SQL](#AddingDataBindingWebTest_BindSQLData), zvolte soubor CSV jako zdroj dat, ale.

     ![Zadejte název a vyberte soubor CSV](../test/media/web_test_databinding_adddatasourcedialog.png "Web_Test_DataBinding_AddDataSourceDialog")

### <a name="q-what-if-my-existing-csv-file-does-not-contain-column-headers"></a>Otázka: Co když Můj existující soubor CSV neobsahuje záhlaví sloupců?

**Odpověď:** Pokud záhlaví sloupců nelze přidat, můžete použít soubor popisu schématu do souboru CSV považovat za databázi.

1. Přidáte nový textový soubor s názvem schema.ini.

     ![Přidejte soubor schema.ini](../test/media/web_test_databinding_schemafile.png "Web_Test_DataBinding_SchemaFile")

2. Upravte soubor schema.ini přidat informace, které popisuje strukturu vaše data. Například soubor schématu s popisem soubor CSV může vypadat například takto:

    ```
    [testdata.csv]
    ColNameHeader=False
    ```

3. Přidání zdroje dat na test.

     ![Přidat zdroje dat do testu výkonnosti webu](../test/media/web_test_databinding_sql_adddatasource.png "Web_Test_DataBinding_SQL_AddDataSource")

4. Pokud používáte soubor schema.ini, vyberte jako zdroj dat a název databáze (ne soubor CSV).

     ![Přidat zdroje dat databáze](../test/media/web_test_databinding_adddatasourcecolortext.png "Web_Test_DataBinding_AddDataSourceColorText")

5. Vytvoření nového připojení.

     ![Zvolte nové připojení](../test/media/web_test_databinding_sql_adddatasourcedialogconnectionnew.png "Web_Test_DataBinding_SQL_AddDataSourceDialogConnectionNew")

6. Vyberte zprostředkovatele dat .NET Framework pro OLE DB.

     ![Vyberte zprostředkovatele dat .NET framework OLE DB](../test/media/web_test_databinding_adddatasourcecolortext2.png "Web_Test_DataBinding_AddDataSourceColorText2")

7. Vyberte rozšířené.

     ![Vyberte rozšířené](../test/media/web_test_databinding_advanced.png "Web_Test_DataBinding_Advanced")

8. Pro vlastnost poskytovatele vyberte Microsoft.Jet.OLEDB.4.0 a pak nastavte rozšířené vlastnosti k textu. ZÁHLAVÍ = NE.

     ![Použít rozšířené vlastnosti](../test/media/web_test_databinding_advancedproperties.png "Web_Test_DataBinding_AdvancedProperties")

9. Zadejte název složky, která obsahuje soubor schématu a vyzkoušejte připojení.

     ![Zadejte cestu ke složce data](../test/media/web_test_databinding_adddatasourcecolortext5.png "Web_Test_DataBinding_AddDataSourceColorText5")

10. Vyberte soubor CSV, který chcete použít.

     ![Vyberte soubor text](../test/media/web_test_databinding_adddatasourcecolortext6.png "Web_Test_DataBinding_AddDataSourceColorText6")

     Po dokončení, zobrazí se soubor CSV jako tabulku.

     ![Zdroj dat přidat k testování](../test/media/web_test_databinding_adddatasourcecolortext7.png "Web_Test_DataBinding_AddDataSourceColorText7")

### <a name="q-how-do-i-use-an-xml-file-as-a-data-source"></a>Otázka: jak používat soubor XML jako zdroj dat?

**Odpověď:** Ano.

1. Vytvořte složku pro uspořádání artefakty databáze projekty a přidejte položku.

     ![Přidání nové položky ke složce Data](../test/media/web_test_databinding_foldernewitem.png "Web_Test_DataBinding_FolderNewItem")

2. Vytvořte soubor XML.

     ![Přidejte soubor ColorData.xml](../test/media/web_test_databinding_additemxmlfile.png "Web_Test_DataBinding_AddItemXMLFile")

3. Upravte soubor XML a přidejte data:

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <ColorData>
        <Color>
            <ColorId>0</ColorId>
            <ColorName>Red</ColorName>
        </Color>
        <Color>
            <ColorId>1</ColorId>
            <ColorName>Blue</ColorName>
        </Color>
    </ColorData>
    ```

4. Postupujte podle kroků v [vazby dat SQL](#AddingDataBindingWebTest_BindSQLData), vyberte soubor XML jako zdroj dat, ale.

     ![Zadejte název a vyberte soubor XML](../test/media/web_test_databinding_adddatasourcedialogxml.png "Web_Test_DataBinding_AddDataSourceDialogXML")

### <a name="q-can-i-add-data-binding-to-a-web-service-request-that-uses-soap"></a>Otázka: je možné přidat datové vazby k požadavku webové služby, který používá SOAP?

**Odpověď:** Ano, je nutné změnit SOAP XML ručně.

1. Zvolte žádosti webové služby ve stromové struktuře požadavku a v okně Vlastnosti a potom vyberte se třemi tečkami (...) ve vlastnosti řetězec textu.

     ![Upravit těle webové služby řetězec](../test/media/web_test_databinding_webservicerequest.png "Web_Test_DataBinding_WebServiceRequest")

2. Nahraďte hodnoty v těle protokolu SOAP hodnotami vázané na data pomocí následující syntaxe:

    ```
    {{DataSourceName.TableName.ColumnName}}
    ```

    Například pokud máte následující kód:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <CheckStatus xmlns="http://tempuri.org/">
                <userName>string</userName> <password>string</password> <orderID>int</orderID>
            </CheckStatus>
        </soap:Body>
    </soap:Envelope>
    ```

    Můžete ji změnit k tomuto:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <CheckStatus xmlns="http://tempuri.org/">
                <userName>{{DataSourceName.Users.Name}}</userName> <password>{{DataSourceName.Users.Password}}</password> <orderID>{{DataSourceName.Orders.OrderID}}</orderID>
            </CheckStatus>
        </soap:Body>
    </soap:Envelope>
    ```

3. Uložte test.