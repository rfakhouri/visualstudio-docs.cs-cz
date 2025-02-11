---
title: Vytvořit testy jednotek řízené daty
ms.date: 05/08/2019
ms.topic: conceptual
f1_keywords:
- vs.test.testresults.unittest.datadriven
- vs.test.testresults.unittest.datadriven.failure
helpviewer_keywords:
- unit tests, running
- unit tests, data-driven
- data-driven unit tests
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 5960c84e2cb389580f2d7b0f476da2a456e62585
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66745859"
---
# <a name="how-to-create-a-data-driven-unit-test"></a>Postupy: Vytvoření testu jednotek řízené daty

Chcete-li nastavit metodu testovací jednotky k načtení hodnoty ze zdroje dat můžete použít rozhraní testování částí Microsoft pro spravovaný kód. Metoda se spouští postupně pro každý řádek ve zdroji dat, která usnadňuje testování celé škály vstup pomocí jedné metody.

Vytvoření testu jednotek řízené daty zahrnuje následující kroky:

1. Vytvořte zdroj dat, který obsahuje hodnoty, které můžete použít testovací metody. Zdroj dat může být libovolný typ, který je registrován v počítači, na kterém běží test.

2. Přidat soukromé <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> pole a veřejnou `TestContext` vlastnost testovací třídy.

3. Vytvořit metodu testovací jednotky a přidejte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> atribut k němu.

4. Použít <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A> vlastnost indexeru pro načtení hodnoty, které můžete použít v rámci testu.

## <a name="the-method-under-test"></a>Testované metody

Jako příklad předpokládejme, že máte:

1. Volá se řešení `MyBank` , který přijme a zpracuje transakce pro různé typy účtů.

2. Projekt v `MyBank` volá `BankDb` , který spravuje transakce pro účty.

3. Třída nazývá `Maths` v `BankDb` projekt, který provádí matematické funkce zajistit, že všechny transakce je výhodné banky.

4. Projekt s názvem testování částí `BankDbTests` otestovat chování `BankDb` komponenty.

5. Testování částí třídu s názvem `MathsTests` ověření chování `Maths` třídy.

Otestujeme metody v `Maths` , který přidá dvou celých čísel pomocí smyčka:

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

## <a name="create-a-data-source"></a>Vytvoření zdroje dat

K testování `AddIntegers` metodu, vytvořte zdroj dat, která určuje rozsah hodnot pro parametry a součet, který očekáváte, že má být vrácen. V tomto příkladu vytvoříme s názvem databáze Sql Compact `MathsData` a tabulku s názvem `AddIntegersData` , který obsahuje následující názvy sloupců a hodnot

|Prvníčíslo|Druhéčíslo|Součet|
|-|------------------|-|
|0|1|1|
|1|1|2|
|2|-3|-1|

## <a name="add-a-testcontext-to-the-test-class"></a>Přidat TestContext pro třídu testu

Vytvoří rozhraní testování částí `TestContext` objekt pro uložení informace o zdroji dat pro test řízený daty. Tento objekt rozhraní pak nastaví jako hodnotu `TestContext` vlastnost, která vytvoříte.

```csharp
private TestContext testContextInstance;
public TestContext TestContext
{
    get { return testContextInstance; }
    set { testContextInstance = value; }
}
```

V testovací metodě, získáte přístup k datům prostřednictvím `DataRow` vlastnost indexer `TestContext`.

> [!NOTE]
> Nepodporuje .NET core [DataSource](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute) atribut. Pokud se pokusíte získat přístup k datům test tímto způsobem v projektu testů jednotek .NET Core nebo UPW, zobrazí se vám chybu podobnou této **"'TestContext' neobsahuje definici pro"DataRow"a žádná metoda rozšíření přístupné DataRow přijímala první argument typu. TestContext' nebyl nalezen (nechybí using – direktiva nebo odkaz na sestavení?) "** .

## <a name="write-the-test-method"></a>Zápis testovací metody

Testovací metody pro `AddIntegers` je docela jednoduché. Pro každý řádek ve zdroji dat volání `AddIntegers` s **Prvníčíslo** a **Druhéčíslo** sloupec hodnoty jako parametry a ověřte návratovou hodnotu proti **součet** Hodnota sloupce:

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

`Assert` Metoda obsahuje zprávu, která se zobrazí `x` a `y` hodnoty selhání iterace. Ve výchozím nastavení s potvrzením hodnot – `expected` a `actual` – jsou již zahrnuty podrobnosti o neúspěšných testů.

### <a name="specify-the-datasourceattribute"></a>Zadejte atribut

`DataSource` Atribut určuje připojovací řetězec pro zdroj dat a název tabulky, který používáte v testovací metodě. Přesné informace v připojovacím řetězci se liší v závislosti na tom, jaký druh zdroje dat, kterou používáte. V tomto příkladu jsme použili SqlServerCe databáze.

```csharp
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0;Data Source=C:\Data\MathsData.sdf", "AddIntegersData")]
```

Atribut zdroje dat má tři konstruktory.

```csharp
[DataSource(dataSourceSettingName)]
```

Konstruktor s jedním parametrem používá informace o připojení, která je uložena v *app.config* soubor řešení. *DataSourceSettingsName* je název elementu Xml v konfiguračním souboru, který určuje informace o připojení.

Pomocí *app.config* souborů umožňuje změnit umístění zdroje dat bez provedení změn samotného testu. Informace o tom, jak vytvořit a používat *app.config* souborů naleznete v tématu [názorný postup: Použití konfiguračního souboru k definování zdroje dat](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md)

```csharp
[DataSource(connectionString, tableName)]
```

`DataSource` Konstruktor se dvěma parametry Určuje připojovací řetězec pro zdroj dat a název tabulky, která obsahuje data pro testovací metodu.

Připojovací řetězce závisí na typu zdroje dat, ale měl by obsahovat element zprostředkovatele, který určuje výchozí název zprostředkovatele dat.

```csharp
[DataSource(
    dataProvider,
    connectionString,
    tableName,
    dataAccessMethod
    )]
```

### <a name="use-testcontextdatarow-to-access-the-data"></a>Použití TestContext.DataRow pro přístup k datům

Pro přístup k datům v `AddIntegersData` tabulky, použijte `TestContext.DataRow` indexeru. `DataRow` je <xref:System.Data.DataRow> objektu, proto načtení hodnot sloupců podle názvů index nebo sloupec. Protože hodnoty jsou vráceny jako objekty, je převeďte na typ odpovídající:

```csharp
int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);
```

## <a name="run-the-test-and-view-results"></a>Spusťte test a zobrazit výsledky

Po dokončení zápisu testovací metody vytvoření testovacího projektu. Metoda testu se zobrazí v **Průzkumníka testů** v **nespuštěné testy** skupiny. Při spouštění, zápis a znovu spustit testy, **Průzkumník testů** zobrazuje výsledky ve skupinách **neúspěšné testy**, **úspěšné testy**, a **nespuštěné testy**. Můžete zvolit **spustit všechny** chcete spustit všechny testy, nebo zvolte **spustit** vybrat podmnožinu testů ke spuštění.

Panel výsledků testu v horní části **Průzkumníka testů** je animovaný při spuštění testu. Na konci testovacího běhu panelu budou zelené, pokud všechny testy prošly nebo red Pokud některé testy selhaly. Přehled testovacího běhu se zobrazí v podokně podrobností v dolní části **Průzkumníka testů** okna. Vyberte test, chcete-li zobrazit podrobnosti o testu v dolním podokně.

> [!NOTE]
> Neexistuje výsledek pro každý řádek dat a také jeden výsledek sumarizace. Pokud test proběhl úspěšně. na každém řádku dat spustit souhrn zobrazuje jako **proběhl**. Pokud se test nezdařil na libovolný řádek dat, spusťte souhrn zobrazuje jako **neúspěšné**.

Pokud jste spustili `AddIntegers_FromDataSourceTest` metoda v našem příkladu, na panelu výsledků na červenou a testovací metoda je přesunuta do **neúspěšné testy**. Test řízený daty selže, pokud některé z metod iterovaném ze zdroje dat se nezdaří. Pokud zvolíte selhání testu s daty v **Průzkumníka testů** okně, v podokně podrobností se zobrazí výsledky každé iterace, která je identifikovaná index řádku dat. V našem příkladu zdá se, `AddIntegers` algoritmus nezpracovává záporné hodnoty správně.

Při nápravě testované metody a test spustit znovu, výsledky panel zbarví zeleně a testovací metoda je přesunuta do **předaný testování** skupiny.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=fullName>
- [Testování částí kódu](../test/unit-test-your-code.md)
- [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)
- [Zápis testů částí pro rozhraní .NET pomocí rozhraní testování částí Microsoft](../test/unit-test-your-code.md)
