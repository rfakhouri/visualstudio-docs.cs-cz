---
title: 'Postupy: Vytvoření testu jednotek řízené daty v sadě Visual Studio'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.test.testresults.unittest.datadriven
- vs.test.testresults.unittest.datadriven.failure
helpviewer_keywords:
- unit tests, running
- unit tests, data-driven
- data-driven unit tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: b72f2099f629a35659d67832f4ec583f1409f1c4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-data-driven-unit-test"></a>Postupy: Testy jednotek řízené daty

Pomocí částí Microsoft unit test framework pro spravovaný kód, můžete nastavit metoda testování částí tak, k načtení hodnoty používané v metodě testu z datového zdroje. Metoda je provozován pro každý řádek ve zdroji dat, která usnadňuje testování různých vstupu pomocí jedné metody.

Vytváření testování částí řízené daty zahrnuje následující kroky:

1.  Vytvořte zdroj dat, který obsahuje hodnoty, které použijete v metodě testu. Zdroj dat mohou být jakéhokoli typu, která je zaregistrovaná na počítači, který spouští test.

2.  Přidat privátního <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> pole a veřejné `TestContext` vlastnost k třídě testu.

3.  Vytvořte metoda testování částí a přidejte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> atribut ho.

4.  Použít <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A> vlastnost indexeru k načtení hodnoty, které můžete použít v testu.

##  <a name="BKMK_The_method_under_test"></a> Metoda testovaného

Jako příklad předpokládejme, že máte:

1.  Volá se řešení `MyBank` která přijímá a zpracovává transakcí pro různé typy účtů.

2.  Na projekt v `MyBank` názvem `BankDb` , spravuje transakce pro účty.

3.  Třída volá `Maths` v `DbBank` projekt, který provádí matematické funkce zajistit, že je výhodné bance jakékoli transakce.

4.  Jednotkové testování projekt s názvem `BankDbTests` k testování chování `BankDb` součásti.

5.  Jednotkové testování třídu s názvem `MathsTests` ověření chování `Maths` třídy.

Otestujeme, metoda v `Maths` doplňuje dvě celá čísla pomocí smyčka:

```csharp
public int AddIntegers(int first, int second)
{
    int sum = first;
    for( int i = 0; i < second; i++)
    {
        sum += 1;
    }
    return sum;
}
```

##  <a name="BKMK_Creating_a_data_source"></a> Vytváření zdroje dat
 K testování `AddIntegers` metoda, vytvořte zdroj dat, který určuje rozsah hodnot pro parametry a součet, kterou má být vrácen očekávali. V tomto příkladu vytvoříme Sql Compact databáze s názvem `MathsData` a tabulku s názvem `AddIntegersData` obsahující následující názvy sloupců a hodnot

|Prvníčíslo|Druhéčíslo|Součet|
|-----------------|------------------|---------|
|0|1|1|
|1|1|2|
|2|-3|-1|

##  <a name="BKMK_Adding_a_TestContext_to_the_test_class"></a> Přidávání TestContext do testovací – třída
 Vytvoří systém testování částí `TestContext` objekt pro uložení zdroje dat pro test řízené daty. Rozhraní framework nastaví tento objekt jako hodnotu `TestContext` vlastnost, kterou vytvoříte.

```csharp
private TestContext testContextInstance;
public TestContext TestContext
{
    get { return testContextInstance; }
    set { testContextInstance = value; }
}
```

 V testu metodu, můžete přistupovat k datům prostřednictvím `DataRow` vlastnost indexer `TestContext`.

##  <a name="BKMK_Writing_the_test_method"></a> Zápis testů metoda
 Zkušební metodu `AddIntegers` je docela jednoduché. Pro každý řádek ve zdroji dat, volání `AddIntegers` s **Prvníčíslo** a **Druhéčíslo** sloupec hodnoty jako parametry a zkontrolujte návratovou hodnotu proti **součet** Hodnota sloupce:

```csharp
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0; Data Source=C:\Data\MathsData.sdf;", "Numbers")]
[TestMethod()]
public void AddIntegers_FromDataSourceTest()
{
    var target = new Maths();

    // Access the data
    int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);
    int y = Convert.ToInt32(TestContext.DataRow["SecondNumber"]);
    int expected = Convert.ToInt32(TestContext.DataRow["Sum"]);
    int actual = target.IntegerMethod(x, y);
    Assert.AreEqual(expected, actual,
        "x:<{0}> y:<{1}>",
        new object[] {x, y});
}
```

`Assert` Metoda obsahuje zprávu, která se zobrazí `x` a `y` hodnoty selhání iterace. Ve výchozím nastavení uplatňovaná hodnoty `expected` a `actual`, jsou již zahrnuty podrobnosti o testu se nezdařila.

###  <a name="BKMK_Specifying_the_DataSourceAttribute"></a> Určení DataSourceAttribute
 `DataSource` Atribut určuje připojovací řetězec pro zdroj dat a název tabulky, který používáte v metodě testu. Přesné informace v připojovacím řetězci se liší v závislosti na tom, jaký typ zdroje dat, kterou používáte. V tomto příkladu jsme použili SqlServerCe databáze.

```
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0;Data Source=C:\Data\MathsData.sdf", "AddIntegersData")]
```

Atribut zdroje dat má tři konstruktory.

```
[DataSource(dataSourceSettingName)]
```

 Konstruktor s jeden parametr používá informace o připojení, která je uložená v souboru app.config pro řešení. *DataSourceSettingsName* je název elementu Xml v konfiguračním souboru, který obsahuje informace o připojení.

 Pomocí souboru app.config, můžete změnit umístění zdroje dat bez provedení změn testu jednotek sám sebe. Informace o tom, jak vytvořit a použít soubor app.config najdete v tématu [návod: použití konfiguračního souboru k definování zdroje dat](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md)

```
[DataSource(connectionString, tableName)]
```

 `DataSource` Konstruktor s dva parametry Určuje připojovací řetězec pro zdroj dat a název tabulky, která obsahuje data pro metodu test.

 Připojovací řetězce, závisí na typu typu zdroje dat, ale měl by obsahovat element zprostředkovatele, který určuje invariantní název zprostředkovatele dat.

```
[DataSource(
    dataProvider,
    connectionString,
    tableName,
    dataAccessMethod
    )]
```

###  <a name="BKMK_Using_TestContext_DataRow_to_access_the_data"></a> Pomocí TestContext.DataRow k přístupu k datům
 Pro přístup k datům v `AddIntegersData` tabulky, použijte `TestContext.DataRow` indexer. `DataRow` je <xref:System.Data.DataRow> objektu, takže načíst hodnoty ve sloupcích tak, že názvy indexu nebo sloupec. Protože hodnoty jsou vráceny jako objekty, je převeďte na příslušného typu:

```csharp
int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);
```

##  <a name="BKMK_Running_the_test_and_viewing_results"></a> Spouštění testu a zobrazení výsledků
 Po dokončení zápisu testovací metoda sestavte projekt test. Metoda testů se zobrazí v okně Průzkumníka testů v **není spuštění testů** skupiny. Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v skupiny **se nezdařilo testy**, **předán testy**, a **není spuštění testů**. Můžete zvolit **spustit všechny** spustit všechny testy, nebo zvolte **spustit...**  vybrat podmnožinu testů ke spuštění.

 Na panelu výsledků testu v horní části Průzkumníka je animované svůj test běží. Na konci testovacím běhu panelu bude zelený, pokud všechny testy prošly nebo red Pokud některý z testů se nezdařilo. V podokně podrobností v dolní části okna Průzkumníka testů se zobrazí souhrn testovacím běhu. Vyberte testovací Chcete-li zobrazit podrobnosti o testu v dolním podokně.

 Pokud jste spustili `AddIntegers_FromDataSourceTest` metoda v našem příkladu, na panelu výsledků na červenou a metodu test je přesunuta do **se nezdařilo testy** testu datové selže, pokud libovolná z metod iterated z dat zdroje selže. Když zvolíte testu se nezdařila řízené daty v okně Průzkumníka testů, v podokně podrobností zobrazí výsledky každé iteraci, která je identifikovaná index řádku data. V našem příkladu zdá, že `AddIntegers` algoritmus nezpracovává záporné hodnoty správně.

 Když metoda testovaného po opravě a test znovu spustit, na panelu výsledků změní na zelenou a metodu test je přesunuta do **předán testování** skupiny.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=fullName>
- [Testování částí kódu](../test/unit-test-your-code.md)
- [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)
- [Zápis testů částí pro rozhraní .NET Framework s infrastrukturou pro testování částí Microsoft Unit Test Framework pro spravovaný kód](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)