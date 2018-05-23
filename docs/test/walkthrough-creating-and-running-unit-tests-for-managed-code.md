---
title: Vytváření a spouštění testování částí pro spravovaný kód
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, walkthrough
- unit tests, creating
- unit tests, generating
- unit tests, running
- unit tests, authoring
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
author: gewarren
ms.openlocfilehash: 9cfcfab850d4d56589688eea0d5833400df9cb9d
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="walkthrough-create-and-run-unit-tests-for-managed-code"></a>Návod: Vytváření a spouštění testování částí pro spravovaný kód

Tento názorný postup vás provede jednotlivými kroky vytvoření, spuštění, a přizpůsobení řadu jednotky testů pomocí částí Microsoft unit test framework pro spravovaný kód a sady Visual Studio **testování Explorer**. Spustit s projektu C#, který je ve vývoji, vytvořit testy, které vykonává jeho kód, spusťte testy a podívejte se na výsledky. Potom můžete měnit kód projektu a znovu spusťte testy.

> [!NOTE]
> Tento návod používá částí Microsoft unit test framework pro spravovaný kód. **Testování Explorer** také testy můžete spustit z jednotky třetích stran systémů testů, které mají adaptéry pro **testování Explorer**. Další informace najdete v tématu [instalace systémů testů jednotek třetích stran](../test/install-third-party-unit-test-frameworks.md)

> [!NOTE]
> Informace o tom, jak spustit testy z příkazového řádku najdete v tématu [návod: použití testů z příkazového řádku nástroje](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867).

## <a name="prerequisites"></a>Požadavky

- Projekt Bank. V tématu [ukázkový projekt testů jednotek](../test/sample-project-for-creating-unit-tests.md).

## <a name="create-a-project-to-test"></a>Vytvoření projektu testování

1. Otevřete Visual Studio.

2. Na **soubor** nabídce vyberte možnost **nový** > **projektu**.

     **Nový projekt** zobrazí se dialogové okno.

3. V části **nainstalovaných šablonách**, klikněte na tlačítko **Visual C#**.

4. V seznamu typů aplikací, klikněte na **knihovny tříd**.

5. V **název** zadejte `Bank` a pak klikněte na **OK**.

    > [!NOTE]
    > Pokud se už používá název "Banka", zvolte jiný název pro projekt.

     Nový projekt Bank se vytvoří a zobrazí v **Průzkumníku řešení** s *Class1.cs* soubor otevřete v editoru kódu.

    > [!NOTE]
    > Pokud *Class1.cs* soubor není otevřen v editoru kódu, poklikejte na soubor *Class1.cs* v Průzkumníku řešení otevřete.

6. Zkopírujte zdrojového kódu z [ukázkový projekt pro vytvoření testů jednotek](../test/sample-project-for-creating-unit-tests.md)a nahradit původní obsah *Class1.cs* zkopírovaný kódem.

7. Uložte soubor jako *BankAccount.cs*.

8. Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.

Nyní máte projekt s názvem Bank. Obsahuje zdrojový kód pro testování a nástroje pro testování se službou. Obor názvů pro Bank, BankAccountNS, obsahuje veřejná třída bankovní účet, jehož metody budete testovat v následujících postupech.

V tomto článku testy soustředit na metodě debetní. Debetní metoda je volána, když peníze stažení z účtu. Tady je definici metody:

```csharp
// Method to be tested.
public void Debit(double amount)
{
    if(amount > m_balance)
    {
        throw new ArgumentOutOfRangeException("amount");
    }
    if (amount < 0)
    {
        throw new ArgumentOutOfRangeException("amount");
    }
    m_balance += amount;
}
```

## <a name="create-a-unit-test-project"></a>Vytvoření projektu testů jednotek

1. Na **soubor** nabídce vyberte možnost **přidat** > **nový projekt**.

2. V dialogovém okně Nový projekt rozbalte **nainstalovaná**, rozbalte položku **Visual C#** a potom zvolte **Test**.

3. V seznamu šablon vyberte **projektu testování částí**.

4. V **název** zadejte `BankTests`a potom vyberte **OK**.

     **BankTests** projekt je přidán do **Bank** řešení.

5. V **BankTests** projekt, přidejte odkaz na **Bank** projektu.

     V Průzkumníku řešení, vyberte **odkazy** v **BankTests** projektu a potom zvolte **přidat odkaz na** v místní nabídce.

6. V dialogovém okně Správce odkazů rozbalte **řešení** a poté zkontrolujte **Bank** položky.

## <a name="create-the-test-class"></a>Vytvořit testovací – třída

Vytvořte třídu test ověření `BankAccount` třídy. Můžete použít *UnitTest1.cs* soubor, který byl vytvořen pomocí šablony projektu, ale zadejte soubor a třídy více popisné názvy. Můžete to udělat v jednom kroku pomocí přejmenování souboru v **Průzkumníku řešení**.

### <a name="rename-a-class-file"></a>Přejmenovat soubor – třída

V **Průzkumníku řešení**, vyberte *UnitTest1.cs* v BankTests projektu. V místní nabídce vyberte **přejmenovat**a přejmenujte soubor *BankAccountTests.cs*. Zvolte **Ano** v dialogovém okně s dotazem, pokud chcete přejmenovat všechny odkazy na tento element kódu `UnitTest1` v projektu.

Tento krok se změní název třídy pro `BankAccountTests`. *BankAccountTests.cs* soubor teď obsahuje následující kód:

```csharp
using System;
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace BankTests
{
    [TestClass]
    public class BankAccountTests
    {
        [TestMethod]
        public void TestMethod1()
        {
        }
    }
}
```

### <a name="add-a-using-statement-to-the-project-under-test"></a>Přidat pomocí příkazu do projektu testovaného

Můžete také přidat `using` příkaz k třídě, abyste mohli provést volání do projektu testovaného bez využívající plně kvalifikované názvy. V horní části souboru třídy přidejte:

```csharp
using BankAccountNS;
```

### <a name="test-class-requirements"></a>Test požadavky – třída

Minimální požadavky pro třídu test se:

- `[TestClass]` Atribut je požadován v jednotce Microsoft testování framework pro spravovaný kód pro všechny třídy, která obsahuje jednotky zkušební metody, které chcete spustit v Průzkumníku otestovat.

- Každá metoda test, který chcete spustit testovací aplikace Explorer musí mít `[TestMethod]`atribut.

Může mít jiné třídy v projektu testů jednotek, které nemají `[TestClass]` atribut a může mít jiné metody v testovací třídy, které nemají `[TestMethod]` atribut. Můžete tyto třídy a metody v zkušební metody.

## <a name="create-the-first-test-method"></a>Vytvoření první metoda testu

V tomto postupu napíšete jednotkové testování metody ověření chování `Debit` metodu `BankAccount` třídy. `Debit` Metoda je uvedený výše v tomto článku.

Existují aspoň tři chování, které je třeba ověřit:

- Vyvolá metoda <xref:System.ArgumentOutOfRangeException> Pokud debetní velikost je větší než zůstatek.

- Vyvolá metoda <xref:System.ArgumentOutOfRangeException> Pokud debetní velikost je menší než nula.

- Pokud je platné velikost debetní, metodu odečítá MD částka z zůstatek účtu.

> [!TIP]
> Můžete odstranit výchozí `TestMethod1` metoda, protože nebude ho použít v tomto průvodci.

### <a name="to-create-a-test-method"></a>Chcete-li vytvořit testovací metoda

První test ověřuje, že platnou částku (to znamená, jednu, která je menší než zůstatek účtu a je větší než nula) stáhne z účtu správnou velikost. Přidejte následující metodu do `BankAccountTests` třídy:

```csharp
[TestMethod]
public void Debit_WithValidAmount_UpdatesBalance()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 4.55;
    double expected = 7.44;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    account.Debit(debitAmount);

    // Assert
    double actual = account.Balance;
    Assert.AreEqual(expected, actual, 0.001, "Account not debited correctly");
}
```

Metoda je jednoduchá: ji nastaví nový `BankAccount` objektu s počáteční zůstatek a potom stáhne platné velikost. Použije <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A> metodu k ověření, že je konečný zůstatek podle očekávání.

### <a name="test-method-requirements"></a>Test požadavky – metoda

Metoda test musí splňovat následující požadavky:

- Je upravena pomocí `[TestMethod]` atribut.

- Vrátí `void`.

- Nemůže mít parametry.

## <a name="build-and-run-the-test"></a>Sestavení a spuštění testu

1. Na **sestavení** nabídce zvolte **sestavit řešení**.

   Pokud nejsou žádné chyby **Průzkumníka testů** se zobrazí s **Debit_WithValidAmount_UpdatesBalance** uvedené v **není spuštění testů** skupiny.

   > [!TIP]
   > Pokud **Průzkumníka testů** nezobrazí po úspěšném sestavení, zvolte **Test** v nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.

2. Zvolte **spustit všechny** ke spuštění testu. Je spuštěn test, je animované stavového řádku v horní části okna. Na konci testovacím běhu zapne panelu zelený, pokud všechny metody testovací předání nebo red Pokud některý z testů selže.

3. V takovém případě test se nezdaří. Metoda test je přesunuta do **se nezdařilo testy** skupiny. Vyberte metodu v **Průzkumníka testů** k zobrazení podrobností v dolní části okna.

## <a name="fix-your-code-and-rerun-your-tests"></a>Opravte kódu a znovu spusťte testy

**Analýza výsledků testu**

Výsledek testu obsahuje zprávu, která popisuje selhání. Pro `AreEquals` metoda, zpráva se zobrazí, co byl očekáván ( **očekávaná\<*hodnotu* >**  parametr) a ve skutečnosti přijaté ( **Skutečné\<*hodnotu* >** parametr). Očekáván vyrovnávání snížení, ale místo toho je ve skutečnosti vyšší velikostí o stažení.

Testování částí má zjištěných chyby: množství stažení je *přidat* na zůstatek účtu, pokud by měla být *odečítat*.

**Opravte chybě**

Chcete-li chybu opravit, nahraďte řádek:

```csharp
m_balance += amount;
```

Pomocí:

```csharp
m_balance -= amount;
```

**Znovu spustit test**

V Průzkumníku otestovat, zvolte **spustit všechny** znovu spustit test. Změní na zelenou znamenající test proběhl úspěšně a test je přesunuta do panelu red zelený **předán testy** skupiny.

## <a name="use-unit-tests-to-improve-your-code"></a>Testování částí použití k vylepšení vašeho kódu

Tato část popisuje, jak iterativní proces analýzy, vývoj testů jednotek a refaktoring můžete aby produkčním kódu víc robustní a efektivní.

**Analyzovat problémy**

Jste vytvořili testovací metoda potvrďte, že je platné velikost správně odečtena v `Debit` metoda. Nyní, ověřte, že vyvolá metoda <xref:System.ArgumentOutOfRangeException> Pokud MD částku je buď:

- větší než zůstatek, nebo
- menší než nula.

**Vytvořit testovací metody**

Vytvořte testovací metodu k ověření správné chování při debetní velikost je menší než nula.:

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentOutOfRangeException))]
public void Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = -100.00;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    account.Debit(debitAmount);

    // Assert is handled by the ExpectedException attribute on the test method.
}
```

Použití <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> atribut k vyhodnocení, zda byla vyvolána výjimka správné. Atribut způsobí, že test nezdaří, pokud <xref:System.ArgumentOutOfRangeException> je vyvolána výjimka. Pokud změníte dočasně metodu testovaného throw další Obecné <xref:System.ApplicationException> při MD částku menší než nula, test chovat správně&mdash;to znamená, se nezdaří.

K testování případě, když stažené velikost je větší než zůstatek, proveďte následující kroky:

1. Vytvoření nové metody test s názvem `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`.

2. Zkopírujte text metoda z `Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange` nové metody.

3. Nastavte `debitAmount` na číslo větší než zůstatek.

**Spouštění testů**

Spuštění tyto dvě metody testovací ukazuje testy fungovat správně.

**Pokračovat analýzy**

Poslední dva testovací metody jsou však také zneklidňují nové. Vám nemůže být určité která podmínka v metodě testovaného vyvolá výjimku při spuštění buď test. Nějakým způsobem rozlišení dvě podmínky, který je záporný MD částka nebo hodnota větší než zůstatek, by zvýšit vaši důvěru testy.

Podívejte se na metodu testovaného znovu a Všimněte si, že pomocí obou podmíněné příkazy `ArgumentOutOfRangeException` konstruktor, který právě přebírá název argumentu jako parametr:

```csharp
throw new ArgumentOutOfRangeException("amount");
```

Je můžete použít konstruktor, který hlásí mnohem širší informace: <xref:System.ArgumentOutOfRangeException.%23ctor%2A> `(String, Object, String)` obsahuje název argument, hodnota argumentu a uživatelem definovaná zpráva. Můžete Refaktorovat metodu testovaného používat tento konstruktor. Můžete i lépe členy typu veřejně dostupné k určení chyby.

**Refaktorovat testovaného kódu**

Nejprve definujte dvě konstanty pro chybové zprávy na rozsah třídy. Tyto ve třídě testovaného PUT (`Bank`):

```csharp
public const string DebitAmountExceedsBalanceMessage = "Debit amount exceeds balance";
public const string DebitAmountLessThanZeroMessage = "Debit amount is less than zero";
```

Upravte dvě podmíněné příkazy v `Debit` metoda:

```csharp
    if (amount > m_balance)
    {
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountExceedsBalanceMessage);
    }

    if (amount < 0)
    {
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountLessThanZeroMessage);
    }
```

**Refaktorovat zkušební metody**

Odeberte `ExpectedException` testování metoda atribut a místo toho catch vyvolaná výjimka a ověřte jeho přidružené zprávy. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=fullName> Metoda poskytuje možnost k porovnání dvou řetězců.

Nyní `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` může vypadat například takto:

```csharp
[TestMethod]
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 20.0;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    try
    {
        account.Debit(debitAmount);
    }
    catch (ArgumentOutOfRangeException e)
    {
        // Assert
        StringAssert.Contains(e.Message, BankAccount.DebitAmountExceedsBalanceMessage);
    }
}
```

**Testování, přepisování a opakovat analýzu**

Předpokládejme, je chyba v metodě testovaného a `Debit` metoda není i *throw* <xref:System.ArgumentOutOfRangeException>, nevermind výstup správné zprávu s výjimkou. V současné době metodu test nemůže pracovat s tento případ. Pokud `debitAmount` hodnota je platná (to znamená, je menší než zůstatek ale větší než nula), žádná výjimka je zachycena, takže assert nikdy aktivuje. Ještě předá metodu test. Toto není funkční, protože chcete, aby metoda test nezdaří, pokud nedojde k výjimce.

To je chyba v metodě testu. Chcete-li problém vyřešit, přidejte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> assert na konci testu metody pro zpracování případu, kdy je vyvolána žádná výjimka.

Znovu spustit test ukazuje, že testu nyní, ale *selže* Pokud je správná výjimka zachycena. `catch` Bloku zachytí výjimky, ale metoda bude pokračovat v provádění a selže v nové <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> assert. Chcete-li vyřešit tento problém, přidejte `return` příkaz po `StringAssert` v `catch` bloku. Znovu spustit test potvrdí, že je tento problém vyřešili. Finální verzi `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` vypadá podobně jako tento:

```csharp
[TestMethod]
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 20.0;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    try
    {
        account.Debit(debitAmount);
    }
    catch (ArgumentOutOfRangeException e)
    {
        // Assert
        StringAssert.Contains(e.Message, BankAccount.DebitAmountExceedsBalanceMessage);
        return;
    }

    Assert.Fail("The expected exception was not thrown.");
}
```

Vylepšení testovacího kódu vedla k robustnější a informativní zkušební metody. Ale ještě důležitější, taky vylepšené testovaného kódu.
