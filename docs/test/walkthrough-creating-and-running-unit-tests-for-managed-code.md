---
title: C#kurz testu jednotek
ms.date: 05/14/2019
ms.topic: conceptual
helpviewer_keywords:
- unit tests, walkthrough
- unit tests, creating
- unit tests, generating
- unit tests, running
- unit tests, authoring
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
author: gewarren
ms.openlocfilehash: 7c588966a957cf6d3127e03c67ad1a1d605fabce
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66401723"
---
# <a name="walkthrough-create-and-run-unit-tests-for-managed-code"></a>Návod: Vytváření a spouštění testů jednotek pro spravovaný kód

Tento článek vás provede vytvořením, spuštěný, a přizpůsobením série jednotky testů pomocí rozhraní pro testování jednotek Microsoft pro spravovaný kód a Visual Studio **Průzkumníka testů**. Spustit u projektu C#, která je ve vývoji, vytvoříte testy, které testují jeho kód, spusťte testy a podívejte se na výsledky. Pak můžete změnit kód projektu a znovu spusťte testy.

## <a name="create-a-project-to-test"></a>Vytvoření projektu pro testování

::: moniker range="vs-2017"

1. Otevřít Visual Studio.

2. Na **souboru** nabídce vyberte možnost **nový** > **projektu**.

   Zobrazí se dialogové okno **Nový projekt**.

3. V části **Visual C#**  > **.NET Core** kategorie, zvolte **Konzolová aplikace (.NET Core)** šablony projektu.

4. Pojmenujte projekt **Bank**a potom klikněte na tlačítko **OK**.

   Projekt banky se vytvoří a zobrazí v **Průzkumníka řešení** s *Program.cs* soubor je otevřen v editoru kódu.

   > [!NOTE]
   > Pokud *Program.cs* nelze otevřít v editoru, poklikejte na soubor *Program.cs* v **Průzkumníka řešení** ho otevřete.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřít Visual Studio.

2. V okně start zvolte **vytvořte nový projekt**.

3. Vyhledání a výběr C# **Konzolová aplikace (.NET Core)** šablony projektu a pak klikněte na tlačítko **Další**.

4. Pojmenujte projekt **Bank**a potom klikněte na tlačítko **vytvořit**.

   Projekt banky se vytvoří a zobrazí v **Průzkumníka řešení** s *Program.cs* soubor je otevřen v editoru kódu.

   > [!NOTE]
   > Pokud *Program.cs* nelze otevřít v editoru, poklikejte na soubor *Program.cs* v **Průzkumníka řešení** ho otevřete.

::: moniker-end

5. Nahraďte obsah *Program.cs* následujícím C# kód, který definuje třídu, *BankAccount*:

   ```csharp
   using System;

   namespace BankAccountNS
   {
       /// <summary>
       /// Bank account demo class.
       /// </summary>
       public class BankAccount
       {
           private readonly string m_customerName;
           private double m_balance;

           private BankAccount() { }

           public BankAccount(string customerName, double balance)
           {
               m_customerName = customerName;
               m_balance = balance;
           }

           public string CustomerName
           {
               get { return m_customerName; }
           }

           public double Balance
           {
               get { return m_balance; }
           }

           public void Debit(double amount)
           {
               if (amount > m_balance)
               {
                   throw new ArgumentOutOfRangeException("amount");
               }

               if (amount < 0)
               {
                   throw new ArgumentOutOfRangeException("amount");
               }

               m_balance += amount; // intentionally incorrect code
           }

           public void Credit(double amount)
           {
               if (amount < 0)
               {
                   throw new ArgumentOutOfRangeException("amount");
               }

               m_balance += amount;
           }

           public static void Main()
           {
               BankAccount ba = new BankAccount("Mr. Bryan Walton", 11.99);

               ba.Credit(5.77);
               ba.Debit(11.22);
               Console.WriteLine("Current balance is ${0}", ba.Balance);
           }
       }
   }
   ```

6. Přejmenujte soubor na *BankAccount.cs* kliknutím pravým tlačítkem a vyberete **přejmenovat** v **Průzkumníka řešení**.

7. Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.

Nyní máte projekt s metodami, které můžete otestovat. V tomto článku se testy zaměřit `Debit` metody. `Debit` Metoda je volána, když jsou peníze z účtu.

## <a name="create-a-unit-test-project"></a>Vytvoření projektu testování částí

1. Na **souboru** nabídce vyberte možnost **přidat** > **nový projekt**.

   > [!TIP]
   > Můžete také pravým tlačítkem na řešení v **Průzkumníka řešení** a zvolte **přidat** > **nový projekt**.

::: moniker range="vs-2017"

2. V **nový projekt** dialogového okna rozbalte **nainstalováno**, rozbalte **Visual C#** a klikněte na tlačítko **Test**.

3. V seznamu šablon vyberte **projekt testů MSTest (.NET Core)** .

4. V **název** zadejte `BankTests`a pak vyberte **OK**.

   **BankTests** projekt je přidán do **Bank** řešení.

::: moniker-end

::: moniker range=">=vs-2019"

2. Vyhledání a výběr C# **projekt testů MSTest (.NET Core)** šablony projektu a pak klikněte na tlačítko **Další**.

3. Pojmenujte projekt **BankTests**.

4. Klikněte na možnost **Vytvořit**.

   **BankTests** projekt je přidán do **Bank** řešení.

::: moniker-end

5. V **BankTests** projektu, přidejte odkaz na **Bank** projektu.

   V **Průzkumníka řešení**vyberte **závislosti** pod **BankTests** projektu a klikněte na tlačítko **přidat odkaz** z pravým tlačítkem myši nabídka.

6. V **správce odkazů** dialogového okna rozbalte **projekty**vyberte **řešení**a potom zaškrtněte políčko **Bank** položky.

7. Zvolte **OK**.

## <a name="create-the-test-class"></a>Vytvoření testovací třídy

Vytvořte třídu testu k ověření `BankAccount` třídy. Můžete použít *UnitTest1.cs* soubor, který se vygeneroval pomocí šablony projektu, ale dát souboru a třídě více popisné názvy. Můžete to udělat v jednom kroku přejmenováním souboru v **Průzkumníka řešení**.

### <a name="rename-a-file-and-class"></a>Přejmenování souboru nebo třídy

1. Přejmenování souboru v **Průzkumníka řešení**, vyberte *UnitTest1.cs* soubor v projektu BankTests. V místní nabídce zvolte **přejmenovat**a potom přejmenujte soubor, který má *BankAccountTests.cs*.

   ::: moniker range="vs-2017"

   V dialogovém okně, která se otevře, zvolte **ne**.

   ::: moniker-end

2. Pro tuto třídu přejmenovat, umístěte kurzor na `UnitTest1` v editoru kódu a stiskněte klávesu **F2** (nebo klikněte pravým tlačítkem a zvolte **přejmenovat**). Zadejte **BankAccountTests** a potom stiskněte klávesu **Enter**.

*BankAccountTests.cs* soubor nyní obsahuje následující kód:

```csharp
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

### <a name="add-a-using-statement"></a>Přidat using – příkaz

Přidat [ `using` příkaz](/dotnet/csharp/language-reference/keywords/using-statement) na testovací třídě, abyste mohli provést volání do testovaného projektu bez použití plně kvalifikovaných názvů. V horní části souboru třídy přidejte:

```csharp
using BankAccountNS;
```

### <a name="test-class-requirements"></a>Požadavky na testovací třídu

Minimální požadavky na testovací třídu jsou:

- `[TestClass]` Atribut je požadován na libovolnou třídu obsahující metody jednotkového testu, které chcete spustit v aplikaci Test Explorer.

- Každá testovací metoda, která chcete, aby Test Explorer rozpoznat musí mít `[TestMethod]` atribut.

Můžete mít další třídy v projektu testů jednotek, které nemají `[TestClass]` atribut který může mít jiné metody v testovacích třídách, které nemají `[TestMethod]` atribut. Tyto třídy a metody lze volat z testovací metody.

## <a name="create-the-first-test-method"></a>Vytvoření první testovací metody

V tomto postupu budete psát testování částí, metody, které ověří chování `Debit` metodu `BankAccount` třídy.

Existují nejméně tři typy chování, které je potřeba zkontrolovat:

- Metoda vyvolá <xref:System.ArgumentOutOfRangeException> Pokud debetní velikost je větší než zůstatek na účtu.

- Metoda vyvolá <xref:System.ArgumentOutOfRangeException> Pokud debetní velikost je menší než nula.

- Pokud je hodnota debetní platný, metoda odečte MD částku od zůstatku účtu.

> [!TIP]
> Můžete odstranit výchozí `TestMethod1` metody, protože nebudeme je používat v tomto názorném postupu.

### <a name="to-create-a-test-method"></a>Vytvoření testovací metody

První test ověří, že platná částka (to znamená, že tu je menší než zůstatek na účtu a větší než nula) stáhne z účtu objektu správnou velikost. Přidejte následující metodu do `BankAccountTests` třídy:

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

Tato metoda je jednoduchý: nastaví nový `BankAccount` objekt s počáteční zůstatek a potom stáhne platnou částku. Používá <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=nameWithType> metodu k ověření, že je konečný zůstatek podle očekávání.

### <a name="test-method-requirements"></a>Požadavky na testovací metodu

Testovací metoda musí splňovat následující požadavky:

- Je doplněn `[TestMethod]` atribut.

- Vrátí `void`.

- Nemůže mít parametry.

## <a name="build-and-run-the-test"></a>Sestavení a spuštění testu

1. Na **sestavení** nabídce zvolte **sestavit řešení**.

2. Pokud **Průzkumník testů** není otevřené, otevřete ho kliknutím **testovací** > **Windows** > **Průzkumník testů** z horním řádku nabídek.

3. Zvolte **spustit všechny** pro spuštění testu.

   Když test běží, stavového řádku v horní části **Průzkumníka testů** animovat okno. Na konci testovacího běhu stavový řádek zezelená, pokud všechny testovací metody proběhly úspěšně nebo red Pokud selže některý z testů.

   V tomto případě test se nezdaří.

4. Vyberte metodu v **Průzkumník testů** k zobrazení podrobností v dolní části okna.

## <a name="fix-your-code-and-rerun-your-tests"></a>Oprava kódu a znovu spustit testy

Výsledek testu obsahuje zprávu s popisem chyby. Pro `AreEqual` metody ve zprávě zobrazí očekávaným a co skutečně byla přijata. Očekáván snížení zůstatku, ale místo toho zvětšit velikost o stažení.

Testování částí vyplynul chybu: stažení je *přidali* k zůstatku, ale měla by být *odečtena*.

### <a name="correct-the-bug"></a>Oprava chyby

Chcete-li opravit chybu, v *BankAccount.cs* souboru, nahraďte řádek:

```csharp
m_balance += amount;
```

Pomocí:

```csharp
m_balance -= amount;
```

### <a name="rerun-the-test"></a>Opětovné provedení testu

V **Průzkumníka testů**, zvolte **spustit všechny** na opětovné spuštění testu. Barva červeného/zeleného panel zbarví zeleně k označení, že test proběhl úspěšně.

![Průzkumník testů v zobrazení Visual Studio 2019 předaný testu](media/test-explorer-banktests-passed.png)

## <a name="use-unit-tests-to-improve-your-code"></a>Použití jednotkových testů ke zlepšení kódu

Tato část popisuje, jak může iterativní proces analýzy, vývoj jednotkových testů a refaktoring pomoci vám robustnějšího a efektivnějšího produkčního kódu.

### <a name="analyze-the-issues"></a>Analýza problémů

Vytvoření testovací metody pro potvrzení, správně odečtení platné částky v `Debit` metody. Nyní, ověřte, že metoda vyvolá <xref:System.ArgumentOutOfRangeException> Pokud je tato hodnota debetní buď:

- větší než zůstatek, nebo
- menší než nula.

### <a name="create-and-run-new-test-methods"></a>Vytvoření a spuštění nové metody testu

Vytvořte testovací metodu k ověření správné chování při debetní velikost je menší než nula:

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

Použití <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> atribut k vyhodnocení, že byla vyvolána správná výjimka. Atribut způsobí, že se test nezdaří, pokud <xref:System.ArgumentOutOfRangeException> je vyvolána výjimka. Pokud upravíte dočasně testované vyvolat další obecné metody <xref:System.ApplicationException> při MD částka menší než nula, správné chování testu&mdash;tedy selže.

K otestování případu, kdy vybíraná hodnota je větší než zůstatek, proveďte následující kroky:

1. Vytvořit novou testovací metodu s názvem `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`.

2. Zkopírovat tělo metody z `Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange` do nové metody.

3. Nastavte `debitAmount` na číslo větší než zůstatek na účtu.

Spuštění těchto dvou metod testu ukazuje, že testy správně fungovat.

### <a name="continue-the-analysis"></a>Pokračování analýzy

Metoda testování lze dále zvýšit. Aktuální implementaci, máme k dispozici žádný způsob, jak zjistit, která podmínka (`amount > m_balance` nebo `amount < 0`) vedla k výjimce během testu. Právě víme, že `ArgumentOutOfRangeException` byla vyvolána někde v metodě. By bylo lepší, pokud jsme může zjistit, které podmínku v `BankAccount.Debit` způsobila výjimku, která je vyvolána (`amount > m_balance` nebo `amount < 0`), můžeme být jistí, že metodě je vhodnosti kontroly argumenty správně.

Podívejte se na metody testování (`BankAccount.Debit`) znovu a Všimněte si, že oba podmíněné příkazy používají `ArgumentOutOfRangeException` konstruktor, který právě přebírá název argumentu, který jako parametr:

```csharp
throw new ArgumentOutOfRangeException("amount");
```

Je můžete použít konstruktor, který mnohem bohatší informace: <xref:System.ArgumentOutOfRangeException.%23ctor(System.String,System.Object,System.String)> obsahuje název argumentu, hodnotu argumentu a uživatelsky definovanou zprávu. Možné provést refaktoring testované používala tento konstruktor metody. Navíc můžete použít veřejně dostupné členy typů ke specifikaci chyb.

### <a name="refactor-the-code-under-test"></a>Refaktoring testovaného kódu

Nejprve definujte dvě konstanty pro chybové zprávy v oboru třídy. Vložit ve třídě v rámci testu, `BankAccount`:

```csharp
public const string DebitAmountExceedsBalanceMessage = "Debit amount exceeds balance";
public const string DebitAmountLessThanZeroMessage = "Debit amount is less than zero";
```

Změňte dva podmíněné příkazy v `Debit` metody:

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

### <a name="refactor-the-test-methods"></a>Refaktoring testovacích metod

Odeberte `ExpectedException` testu atribut method a místo toho zachyťte vyvolanou výjimku a ověřte její přidružené zprávy. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=fullName> Metoda poskytuje možnost k porovnání dvou řetězců.

Nyní `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` může vypadat třeba takto:

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

### <a name="retest-rewrite-and-reanalyze"></a>Opětovné testování, revize a analýza

Předpokládejme je chyba v metodě v rámci testu a `Debit` i metoda nevyvolá <xref:System.ArgumentOutOfRangeException> nikdy nezapomeňte výstup správné zprávy s výjimkou. Testovací metoda není v současné době zpracovávat tento případ. Pokud `debitAmount` je hodnota platná (to znamená menší než zůstatek, ale větší než nula), žádná výjimka je zachycena, takže assert nikdy aktivuje. Zatím testovací metoda skončí úspěchem. To není správné, protože chcete, aby testovací metoda selhat, pokud není vyvolána žádná výjimka.

Jedná se o chybu v testovací metodě. Chcete-li problém vyřešit, přidejte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> uplatnit na konci testovací metody pro zpracování případu, kdy není vyvolána žádná výjimka.

Znovu spustit test ukazuje, že test nyní *selže* Pokud zachycení správné výjimky. `catch` Bloku zachytí výjimku, ale metoda pokračuje v provádění a ona selže na novou <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> kontrolní výraz. Chcete-li tento problém vyřešit, přidejte `return` příkazem za `StringAssert` v `catch` bloku. Znovu spustit test potvrdí, že je tento problém vyřešili. Konečná verze `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` vypadá přibližně takto:

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

### <a name="conclusion"></a>Závěr

Vylepšení testovacího kódu vedla k robustnějším a informativnějším testovací metody. Ale důležitější je, taky vylepšené testovaného kódu.

> [!TIP]
> Tento návod používá rozhraní testování částí Microsoft pro spravovaný kód. **Průzkumník testů** také testy můžete spustit z jednotky třetí strany, které mají adaptéry pro rozhraní pro testování **Průzkumníka testů**. Další informace najdete v tématu [nainstalovat rozhraní pro testování jednotky třetí strany](../test/install-third-party-unit-test-frameworks.md)

## <a name="see-also"></a>Viz také:

Informace o tom, ke spuštění testů z příkazového řádku najdete v tématu [možnosti příkazového řádku VSTest.Console.exe](vstest-console-options.md).
