---
title: 'Návod: Použití konfiguračního souboru k definování zdroje dat v sadě Visual Studio'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- configuration files [Visual Studio ALM], defining data sources
- unit tests, walkthrough
- data sources, defining with configuration files
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0de562e1000c7c1fe8976252c046b27f4751b871
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-using-a-configuration-file-to-define-a-data-source"></a>Návod: Použití konfiguračního souboru k definování zdroje dat

Tento návod ukazuje, jak používat zdroj dat definované v *app.config* testování částí v souboru. Se dozvíte, jak vytvořit soubor app.config, který definuje zdroj dat, který můžete používat <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> třídy. Úlohy, které jsou uvedené v tomto návodu zahrnují následující:

- Vytvoření souboru app.config.

- Definování vlastní konfigurační oddíl.

- Definování připojovací řetězce.

- Definování datových zdrojů.

- Přístupu k datům zdroje pomocí <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> třídy.

## <a name="prerequisites"></a>Požadavky

K dokončení tohoto postupu potřebujete:

- Visual Studio Enterprise

- Buď Microsoft Access nebo Microsoft Excel poskytující data pro alespoň jednu z metod testu.

- Řešení sady Visual Studio, který obsahuje testovacího projektu.

## <a name="add-an-appconfig-file-to-the-project"></a>Soubor app.config přidejte do projektu

1. Pokud váš projekt test již má soubor app.config, přejděte na [definovat vlastní konfigurační sekce](#DefineCustomConfigurationSection).

2. Klikněte pravým tlačítkem na projekt testu v **Průzkumníku řešení**a potom vyberte **přidat** > **novou položku**.

     **Přidat novou položku** otevře se okno.

3. Vyberte **konfigurační soubor aplikace** šablonu a klikněte na tlačítko **přidat**.

##  <a name="DefineCustomConfigurationSection"></a> Definovat vlastní konfigurační oddíl

Zkontrolujte *app.config* souboru. Obsahuje alespoň deklarace XML a kořenový element.

### <a name="to-add-the-custom-configuration-section-to-the-appconfig-file"></a>Chcete-li přidat vlastní konfigurační oddíl do souboru app.config

1. Kořenový prvek app.config by měla být **konfigurace** elementu. Vytvoření **configSections** v rámci **konfigurace** elementu. **ConfigSections** musí být prvním elementem v *app.config* souboru.

2. V rámci **configSections** elementu, vytvoření **části** elementu.

3. V **části** elementu, přidejte atribut nazvaný `name` a přiřaďte ho hodnotu `microsoft.visualstudio.testtools`. Přidejte jiný atribut názvem `type` a přiřaďte ho hodnotu `Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`.

**Části** element by měl vypadat podobně jako tento:

```
<section name="microsoft.visualstudio.testtools" type="Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>
```

> [!NOTE]
> Název sestavení musí odpovídat sestavení Microsoft Visual Studio .NET Framework, který používáte. Nastavte verzi na 9.0.0.0, pokud používáte Visual Studio .NET Framework 3.5. Pokud používáte Visual Studio .NET Framework 2.0, nastavte verzi na 8.0.0.0.

## <a name="define-connection-strings"></a>Definujte připojovací řetězce

Připojovací řetězce definovat informace specifické pro zprostředkovatele pro přístup k datové zdroje. Připojovací řetězce, které jsou definované v konfiguračních souborech poskytují informace zprostředkovatele opakovaně použitelné dat v aplikaci. V této části vytvoříte dva připojovací řetězce, které budou používat zdroje dat, které jsou definovány v části vlastní konfigurace.

### <a name="to-define-connection-strings"></a>Chcete-li definovat připojovací řetězce

1. Po **configSections** elementu, vytvoření **connectionStrings** elementu.

2. V rámci **connectionStrings** elementu, vytvořte dvě **přidat** elementy.

3. V prvním **přidat** elementu, vytvořte následující atributy a hodnoty pro připojení k databázi Microsoft Access:

|Atribut|Hodnoty|
|---------------|------------|
|`name`|`"MyJetConn"`|
|`connectionString`|`"Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;"`|
|`providerName`|`"System.Data.OleDb"`|

Ve druhém **přidat** elementu, vytvořte následující atributy a hodnoty pro připojení k sešitu aplikace Microsoft Excel:

|||
|-|-|
|`name`|`"MyExcelConn"`|
|`connectionString`|`"Dsn=Excel Files;dbq=data.xlsx;defaultdir=.\; driverid=790;maxbuffersize=2048;pagetimeout=5"`|
|`providerName`|`"System.Data.Odbc"`|

**ConnectionStrings** element by měl vypadat podobně jako tento:

```
<connectionStrings>
    <add name="MyJetConn" connectionString="Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;" providerName="System.Data.OleDb" />
    <add name="MyExcelConn" connectionString="Dsn=Excel Files;dbq=data.xlsx;defaultdir=.\; driverid=790;maxbuffersize=2048;pagetimeout=5" providerName="System.Data.Odbc" />
</connectionStrings>
```

## <a name="define-data-sources"></a>Definování zdrojů dat

Zdroje dat obsahuje čtyři atributy, které jsou k načtení dat ze zdroje dat použít modul testu.

- `name` definuje identitu používané <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> k určení, která data zdroje používat.

- `connectionString` Určuje připojovací řetězec vytvořený v předchozí části zadejte připojovací řetězce.

- `dataTableName` Definuje tabulky nebo listu, která obsahuje data, která mají použít v testu.

- `dataAccessMethod` Definuje technika pro přístup k hodnotám dat ve zdroji dat.

V této části definujete dva zdroje dat pro použití v testování částí.

### <a name="to-define-data-sources"></a>K definování zdroje dat

1. Po **connectionStrings** elementu, vytvoření **microsoft.visualstudio.testtools** element. Tato část byla vytvořena v definovat vlastní konfigurační sekce.

2. V rámci **microsoft.visualstudio.testtools** elementu, vytvoření **zdrojů dat** elementu.

3. V rámci **zdrojů dat** elementu, vytvořte dvě **přidat** elementy.

4. V prvním **přidat** elementu, vytvořte následující atributy a hodnoty pro zdroj dat aplikace Microsoft Access:

|Atribut|Hodnoty|
|---------------|------------|
|`name`|`"MyJetDataSource"`|
|`connectionString`|`"MyJetConn"`|
|`dataTableName`|`"MyDataTable"`|
|`dataAccessMethod`|`"Sequential"`|

Ve druhém **přidat** elementu, vytvořte následující atributy a hodnoty pro zdroj dat Microsoft Excelu:

|||
|-|-|
|`Name`|`"MyExcelDataSource"`|
|`connectionString`|`"MyExcelConn"`|
|`dataTableName`|`"Sheet1$"`|
|`dataAccessMethod`|`"Sequential"`|

**Microsoft.visualstudio.testtools** element by měl vypadat podobně jako tento:

```xml
<microsoft.visualstudio.testtools>
    <dataSources>
        <add name="MyJetDataSource" connectionString="MyJetConn" dataTableName="MyDataTable" dataAccessMethod="Sequential"/>
        <add name="MyExcelDataSource" connectionString="MyExcelConn" dataTableName="Sheet1$" dataAccessMethod="Sequential"/>
    </dataSources>
</microsoft.visualstudio.testtools>
```

Konečné *app.config* soubor by měl vypadat podobně jako tento:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <configSections>
        <section name="microsoft.visualstudio.testtools" type="Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>
    </configSections>
    <connectionStrings>
        <add name="MyJetConn" connectionString="Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;" providerName="System.Data.OleDb" />
        <add name="MyExcelConn" connectionString="Dsn=Excel Files;dbq=data.xlsx;defaultdir=.\; driverid=790;maxbuffersize=2048;pagetimeout=5" providerName="System.Data.Odbc" />
    </connectionStrings>
    <microsoft.visualstudio.testtools>
        <dataSources>
            <add name="MyJetDataSource" connectionString="MyJetConn" dataTableName="MyDataTable" dataAccessMethod="Sequential"/>
            <add name="MyExcelDataSource" connectionString="MyExcelConn" dataTableName="Sheet1$" dataAccessMethod="Sequential"/>
        </dataSources>
    </microsoft.visualstudio.testtools>
</configuration>
```

## <a name="create-a-unit-test-that-uses-data-sources-defined-in-appconfig"></a>Vytvoření testů jednotek, která používá zdroje dat definované v souboru app.config

Teď, když byla definována soubor app.config, vytvoříte testů jednotek, která používá data umístěná v zdroje dat, které jsou definovány v souboru app.config. V této části provedeme následující:

- Vytvoření zdroje dat nalezen v souboru app.config.

- Zdroje dat v dvě testovací metody, které porovnat hodnoty u každého zdroje dat použijte.

### <a name="to-create-a-microsoft-access-data-source"></a>Chcete-li vytvořit zdroj dat aplikace Microsoft Access

1. Vytvořit databázi Microsoft Access s názvem *testdatasource.accdb*.

2. Vytvořte tabulku s názvem `MyDataTable` v *testdatasource.accdb*.

3. Vytvořte dvě pole v `MyDataTable` s názvem `Arg1` a `Arg2` pomocí `Number` datového typu.

4. Přidat pět entity k `MyDataTable` s následujícími hodnotami pro `Arg1` a `Arg2`, v uvedeném pořadí: (10,50), (3,2), (6,0), (0,8) a (12312,1000).

5. Uložte a zavřete databázi.

6. Změňte připojovací řetězec k přejděte do umístění souboru databáze. Změňte hodnotu `Data Source` tak, aby odrážela umístění databáze.

### <a name="to-create-a-microsoft-excel-data-source"></a>Chcete-li vytvořit zdroj dat aplikace Microsoft Excel

1. Vytvoření tabulky aplikace Microsoft Excel s názvem *data.xlsx*.

2. Vytvoření seznamu s názvem `Sheet1` Pokud již neexistuje v *data.xlsx*.

3. Vytvořte dvě záhlaví sloupců a název je `Val1` a `Val2` v `Sheet1`.

4. Přidat pět entity k `Sheet1` s následujícími hodnotami pro `Val1` a `Val2`, v uvedeném pořadí: (1; 1), (2,2), (3,3), (4,4) a (5,0).

5. Uložte a zavřete tabulku.

6. Změňte připojovací řetězec tak, aby odkazovalo na umístění tabulky. Změňte hodnotu `dbq` tak, aby odrážela umístění tabulky.

### <a name="to-create-a-unit-test-using-the-appconfig-data-sources"></a>Chcete-li vytvořit testů jednotek pomocí souboru app.config zdroje dat

1. Přidání testů jednotek pro projekt test.

2. Automaticky generovaný obsah testování částí nahraďte následujícím kódem:

    ```csharp
    using System;
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    namespace TestProject1
    {
         [TestClass]
        public class UnitTest1
        {
            private TestContext context;

            public TestContext TestContext
            {
                get { return context; }
                set { context = value; }
            }

            [TestMethod()]
            [DeploymentItem("MyTestProject\\testdatasource.accdb")]
            [DataSource("MyJetDataSource")]
            public void MyTestMethod()
            {
                int a = Int32.Parse(context.DataRow["Arg1"].ToString());
                int b = Int32.Parse(context.DataRow["Arg2"].ToString());
                Assert.AreNotEqual(a, b, "A value was equal.");
            }

            [TestMethod()]
            [DeploymentItem("MyTestProject\\data.xlsx")]
            [DataSource("MyExcelDataSource")]
            public void MyTestMethod2()
            {
                Assert.AreEqual(context.DataRow["Val1"], context.DataRow["Val2"]);
            }
        }
    }
    ```

3. Zkontrolujte atributy DataSource. Všimněte si, názvy nastavení ze souboru app.config.

4. Sestavte řešení a spusťte MyTestMethod a MyTestMethod2 testy.

> [!IMPORTANT]
> Nasaďte položky jako zdroje dat tak, že jsou přístupné pro test v adresáři pro nasazení.

## <a name="see-also"></a>Viz také

- [Testování částí kódu](../test/unit-test-your-code.md)
- [Postupy: Testy částí řízené daty](../test/how-to-create-a-data-driven-unit-test.md)