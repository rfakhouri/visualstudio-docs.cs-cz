---
title: "Návod: Vytváření a spouštění testování částí pro spravovaný kód | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit tests, walkthrough
- unit tests, creating
- unit tests, generating
- unit tests, running
- unit tests, authoring
ms.assetid: 2b018b18-b412-4e0e-b0ee-b580a2f3ba9c
caps.latest.revision: "83"
ms.author: douge
manager: douge
ms.openlocfilehash: 825adc757b9ae984bb39b308bab37a0d98b63ab5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="walkthrough-creating-and-running-unit-tests-for-managed-code"></a>Postupy: Vytváření a spouštění testů jednotek pro spravovaný kód
Tento názorný postup bude krok vás vytvoření, spuštění a přizpůsobení řadu testů jednotek pomocí částí Microsoft unit test framework pro spravovaný kód a Průzkumníka testů Visual Studio. Spustit s projektu C#, který je ve vývoji, vytvořit testy, které vykonává jeho kód, spusťte testy a podívejte se na výsledky. Potom můžete měnit kód projektu a znovu spusťte testy.  
  
 Toto téma obsahuje následující oddíly:  
  
 [Příprava Průvodce](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Prepare_the_walkthrough)  
  
 [Vytvoření projektu testování částí](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Create_a_unit_test_project)  
  
 [Vytvořit testovací – třída](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Create_the_test_class)  
  
-   [Test požadavky – třída](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Test_class_requirements)  
  
 [Vytvoření první metoda testu](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Create_the_first_test_method)  
  
-   [Test požadavky – metoda](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Test_method_requirements)  
  
 [Sestavení a spuštění testu](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Build_and_run_the_test)  
  
 [Opravte kódu a znovu spusťte testy](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Fix_your_code_and_rerun_your_tests)  
  
 [Testování částí použití k vylepšení vašeho kódu](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Use_unit_tests_to_improve_your_code)  
  
> [!NOTE]
>  Tento návod používá částí Microsoft unit test framework pro spravovaný kód. Průzkumníka testů také testy můžete spustit z jednotky třetích stran testovací architektury, které mají adaptéry pro testování Explorer. Další informace najdete v tématu [instalace systémů testů jednotek třetích stran](../test/install-third-party-unit-test-frameworks.md)  
  
> [!NOTE]
>  Informace o tom, jak spustit testy z příkazového řádku najdete v tématu [návod: použití nástroje testů z příkazového řádku](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867).  
  
## <a name="prerequisites"></a>Požadavky  
  
-   Projekt Bank. V tématu [ukázkový projekt testů jednotek](../test/sample-project-for-creating-unit-tests.md).  
  
##  <a name="BKMK_Prepare_the_walkthrough"></a>Příprava Průvodce  
  
1.  Otevřete Visual Studio.  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový** a pak klikněte na **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
3.  V části **nainstalovaných šablonách**, klikněte na tlačítko **Visual C#**.  
  
4.  V seznamu typů aplikací, klikněte na **knihovny tříd**.  
  
5.  V **název** zadejte `Bank` a pak klikněte na **OK**.  
  
    > [!NOTE]
    >  Pokud se už používá název "Banka", zvolte jiný název pro projekt.  
  
     Nový projekt Bank se vytvoří a zobrazí v Průzkumníku řešení s Class1.cs soubor otevřete v editoru kódu.  
  
    > [!NOTE]
    >  Pokud soubor Class1.cs není otevřen v editoru kódu, poklikejte na soubor Class1.cs v Průzkumníku řešení otevřete.  
  
6.  Zkopírujte zdrojového kódu z [ukázkový projekt pro vytvoření testů jednotek](../test/sample-project-for-creating-unit-tests.md).  
  
7.  Nahraďte kód z původní obsah Class1.cs [ukázkový projekt pro vytvoření testů jednotek](../test/sample-project-for-creating-unit-tests.md).  
  
8.  Uložte soubor jako BankAccount.cs  
  
9. Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
 Nyní máte projekt s názvem Bank. Obsahuje zdrojový kód pro testování a nástroje pro testování se službou. Obor názvů pro Bank **BankAccountNS**, obsahuje veřejná třída **bankovní účet**, jejichž metody budete testovat v následujících postupech.  
  
 V této úvodní zaměříme na to `Debit` metoda. Debetní metoda je volána, když je odvolají peníze účtu a obsahuje následující kód:  
  
```csharp  
// method under test  
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
  
##  <a name="BKMK_Create_a_unit_test_project"></a>Vytvoření projektu testování částí  
 **Požadovaný**: postupujte podle kroků v postupu [příprava Průvodce](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Prepare_the_walkthrough).  
  
#### <a name="to-create-a-unit-test-project"></a>Vytvoření projektu testování částí  
  
1.  Na **soubor** nabídce zvolte **přidat**a potom zvolte **nový projekt...** .  
  
2.  V dialogovém okně Nový projekt rozbalte **nainstalovaná**, rozbalte položku **Visual C#**a potom zvolte **Test**.  
  
3.  V seznamu šablon vyberte **projektu testování částí**.  
  
4.  V **název** zadejte BankTest a potom zvolte **OK**.  
  
     **BankTests** projekt je přidán do **Bank** řešení.  
  
5.  V **BankTests** projekt, přidejte odkaz na **Bank** řešení.  
  
     V Průzkumníku řešení, vyberte **odkazy** v **BankTests** projektu a potom zvolte **přidat odkaz na...**  v místní nabídce.  
  
6.  V dialogovém okně Správce odkazů rozbalte **řešení** a poté zkontrolujte **Bank** položky.  
  
##  <a name="BKMK_Create_the_test_class"></a>Vytvořit testovací – třída  
 Potřebujeme třídu test pro ověření `BankAccount` třídy. Můžeme použít UnitTest1.cs, který byl vytvořen pomocí šablony projektu, ale jsme by měly poskytnout soubor a třídy více popisné názvy. Jsme to můžete provést v jednom kroku přejmenování souboru v Průzkumníku řešení.  
  
 **Přejmenování souboru – třída**  
  
 V Průzkumníku řešení vyberte soubor UnitTest1.cs v BankTests projektu. V místní nabídce vyberte **přejmenovat**a přejmenujte soubor na BankAccountTests.cs. Zvolte **Ano** v dialogovém okně s dotazem, pokud chcete přejmenovat všechny odkazy v projektu na tento element kódu 'UnitTest1'. Tento krok se změní název třídy pro `BankAccountTest`.  
  
 Soubor BankAccountTests.cs teď obsahuje následující kód:  
  
```csharp  
// unit test code  
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
  
 **Přidat pomocí příkazu do projektu testovaného**  
  
 Nyní můžete také přidat pomocí příkazu k třídě dejte nám to provést volání do projektu testovaného bez využívající plně kvalifikované názvy. V horní části souboru třídy přidejte:  
  
```csharp  
using BankAccountNS;  
```  
  
###  <a name="BKMK_Test_class_requirements"></a>Test požadavky – třída  
 Minimální požadavky na testovací třídy jsou následující:  
  
-   `[TestClass]` Atribut je požadován v jednotce Microsoft testování framework pro spravovaný kód pro všechny třídy, která obsahuje jednotky zkušební metody, které chcete spustit v Průzkumníku otestovat.  
  
-   Každá metoda test, který chcete spustit testovací aplikace Explorer musí mít `[TestMethod]`atribut.  
  
 Může mít jiné třídy v projektu testů jednotek, které nemají `[TestClass]` atribut a může mít jiné metody v testovací třídy, které nemají `[TestMethod]` atribut. Můžete tyto třídy a metody v zkušební metody.  
  
##  <a name="BKMK_Create_the_first_test_method"></a>Vytvoření první metoda testu  
 V tomto postupu budeme zapisovat jednotkové testování metody ověření chování `Debit` metodu `BankAccount` třídy. Metoda je uveden výše.  
  
 Analýzou metodu testovaného jsme určit, že existují aspoň tři chování, které je třeba ověřit:  
  
1.  Vyvolá metoda <xref:System.ArgumentOutOfRangeException> Pokud debetní velikost je větší než zůstatek.  
  
2.  Také vyvolá `ArgumentOutOfRangeException` Pokud debetní velikost je menší než nula.  
  
3.  Pokud kontroly v 1.) a 2.) jsou splněny, metoda odečítá velikost z zůstatek účtu.  
  
 V našem prvním testu jsme ověřte, že platné velikost, (toho, která je menší než zůstatek účtu a který je větší než nula) stáhne z účtu správnou velikost.  
  
#### <a name="to-create-a-test-method"></a>Chcete-li vytvořit testovací metoda  
  
1.  Přidat pomocí `BankAccountNS;` příkaz do souboru BankAccountTests.cs.  
  
2.  Přidejte následující metodu do `BankAccountTests` třídy:  
  
    ```csharp  
    // unit test code  
    [TestMethod]  
    public void Debit_WithValidAmount_UpdatesBalance()  
    {  
        // arrange  
        double beginningBalance = 11.99;  
        double debitAmount = 4.55;  
        double expected = 7.44;  
        BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);  
  
        // act  
        account.Debit(debitAmount);  
  
        // assert  
        double actual = account.Balance;  
        Assert.AreEqual(expected, actual, 0.001, "Account not debited correctly");  
    }  
    ```  
  
 Tato metoda je spíš jednoduchá. Nemůžeme nastavit nový `BankAccount` objektu s počáteční zůstatek a pak odstoupení platné velikost. Používáme částí Microsoft unit test framework pro spravovaný kód <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A> metodu k ověření, že konečný zůstatek je jsme očekávat.  
  
###  <a name="BKMK_Test_method_requirements"></a>Test požadavky – metoda  
 Metoda test musí splňovat následující požadavky:  
  
-   Metoda musí být doplněny pomocí `[TestMethod]` atribut.  
  
-   Metoda musí vracet `void`.  
  
-   Metoda nemůže mít parametry.  
  
##  <a name="BKMK_Build_and_run_the_test"></a>Sestavení a spuštění testu  
  
#### <a name="to-build-and-run-the-test"></a>Sestavení a spuštění testu  
  
1.  Na **sestavení** nabídce zvolte **sestavit řešení**.  
  
     Pokud nejsou žádné chyby, zobrazí se okno UnitTestExplorer **Debit_WithValidAmount_UpdatesBalance** uvedené v **není spuštění testů** skupiny. Pokud se nezobrazí Průzkumníka testů po úspěšném sestavení, zvolte **Test** v nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.  
  
2.  Zvolte **spustit všechny** ke spuštění testu. Animovaný je jako test běží stavového řádku v horní části okna. Na konci testovacím běhu zapne panelu zelený, pokud všechny metody testovací předání nebo red Pokud některý z testů selže.  
  
3.  V takovém případě test nezdaří. Metoda test je přesunuta do **se nezdařilo testy**. Skupina. Vyberte metodu v Průzkumníka testů k zobrazení podrobností v dolní části okna.  
  
##  <a name="BKMK_Fix_your_code_and_rerun_your_tests"></a>Opravte kódu a znovu spusťte testy  
 **Analýza výsledků testu**  
  
 Výsledek testu obsahuje zprávu, která popisuje selhání. Pro `AreEquals` metody zpráva zobrazí co byl očekáván ((**očekávaná\<*XXX*>**parametr) a ve skutečnosti přijaté (na  **Skutečný\<*YYY* >**  parametr). Byl očekáván vyrovnávání chcete odmítnout z počáteční zůstatek, ale místo toho se zvýšila o množství stažení.  
  
 Přezkoumání debetní kódu ukazuje, že proběhla úspěšně testování částí v hledání chyby. Množství stažení se přidá do zůstatek účtu, když se bude odečítat.  
  
 **Opravte chybě**  
  
 Chcete-li chybu opravit, jednoduše nahraďte na řádku  
  
```csharp  
m_balance += amount;  
```  
  
 with  
  
```csharp  
m_balance -= amount;  
```  
  
 **Znovu spustit test**  
  
 V Průzkumníku otestovat, zvolte **spustit všechny** znovu spustit test. Změní na zelenou panelu red zelený a test je přesunuta do **předán testy** skupiny.  
  
##  <a name="BKMK_Use_unit_tests_to_improve_your_code"></a>Testování částí použití k vylepšení vašeho kódu  
 Tato část popisuje, jak iterativní proces analýzy, vývoj testů jednotek a refaktoring můžete aby produkčním kódu víc robustní a efektivní.  
  
 **Analyzovat problémy**  
  
 Po vytvoření testovací metoda potvrďte, že platné velikost je správně odečtena v `Debit` metoda, jsme můžete zapnout na zbývající případy v našem původní analýza:  
  
1.  Vyvolá metoda `ArgumentOutOfRangeException` Pokud debetní velikost je větší než zůstatek.  
  
2.  Také vyvolá `ArgumentOutOfRangeException` Pokud debetní velikost je menší než nula.  
  
 **Vytvořit testovací metody**  
  
 O první pokus o vytvoření testovací metoda tyto problémy řeší zdá se, že Slíbení:  
  
```csharp  
//unit test method  
[TestMethod]  
[ExpectedException(typeof(ArgumentOutOfRangeException))]  
public void Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange()  
{  
    // arrange  
    double beginningBalance = 11.99;  
    double debitAmount = -100.00;  
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);  
  
    // act  
    account.Debit(debitAmount);  
  
    // assert is handled by ExpectedException  
}  
  
```  
  
 Používáme <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> atribut k vyhodnocení, zda byla vyvolána výjimka správné. Atribut způsobí, že test nezdaří, pokud `ArgumentOutOfRangeException` je vyvolána výjimka. Spouštění testu se oba kladné a záporné `debitAmount` hodnoty a pak dočasně úprava metodu testovaného throw obecný <xref:System.ApplicationException> při velikost je menší než nula ukazuje testu chovat správně. K testování případě, když stažené velikost je větší než zůstatek, je potřeba udělat je:  
  
1.  Vytvoření nové metody test s názvem `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`.  
  
2.  Zkopírujte text metoda z `Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange` nové metody.  
  
3.  Nastavte `debitAmount` na číslo větší než zůstatek.  
  
 **Spouštění testů**  
  
 S různé hodnoty pro tyto dvě metody `debitAmount` ukazuje, že testy adekvátní zpracovávat naše zbývající případech. Všechny tři testy potvrďte, že všechny případy v našem původní analysis podléhají správně spuštěna.  
  
 **Pokračovat analýzy**  
  
 Poslední dva testovací metody jsou však také poněkud zneklidňují nové. Jsme nemůže být určité podmínky, které v testovaného kódu vyvolá výjimku, když buď test spustí. Nějakým způsobem rozlišení dvě podmínky mohou být užitečné. Jako jsme přemýšlení o problému další, je zřejmé, že zároveň budete vědět, která podmínka porušené zvýší naše důvěru testy. Tyto informace také velmi pravděpodobně bude vhodné produkční mechanismus, který zpracovává výjimku, pokud je vyvolána metoda testovaného. Generování Další informace, když metoda vrátí by pomůže všechny dotčené, ale `ExpectedException` atributu nelze zadat tyto informace...  
  
 Metoda testovaného prohlížení znovu, vidíme obou podmíněné příkazy použít `ArgumentOutOfRangeException` konstruktor, který přebírá název argumentu jako parametr:  
  
```csharp  
throw new ArgumentOutOfRangeException("amount");  
```  
  
 Z hledání v knihovně MSDN Probíhá zjišťování, zda existuje konstruktor sestav mnohem širší informace. <xref:System.ArgumentOutOfRangeException.%23ctor%2A>`(String, Object, String)`obsahuje název argument, hodnota argumentu a uživatelem definovaná zpráva. Jsme můžete Refaktorovat metodu testovaného používat tento konstruktor. Členy typu veřejně dostupné jsme i lépe, můžete použít k určení chyby.  
  
 **Refaktorovat testovaného kódu**  
  
 Nejprve definujeme dvě konstanty pro chybové zprávy na rozsah třídy:  
  
```csharp  
// class under test  
public const string DebitAmountExceedsBalanceMessage = "Debit amount exceeds balance";  
public const string DebitAmountLessThanZeroMessage = "Debit amount less than zero";  
```  
  
 Upravte jsme dvě podmíněné příkazy v `Debit` metoda:  
  
```csharp  
// method under test  
// ...  
    if (amount > m_balance)  
    {  
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountExceedsBalanceMessage);  
    }  
  
    if (amount < 0)  
    {  
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountLessThanZeroMessage);  
    }  
// ...  
```  
  
 **Refaktorovat zkušební metody**  
  
 V našem testu metoda jsme nejprve odebrat `ExpectedException` atribut. Místo toho jsme catch vyvolaná výjimka a ověřte, že byla vydána v příkaz správné podmínky. Ale jsme musíte rozhodnout teď mezi dvěma možnostmi ověřit naše zbývající podmínky. Například v `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` metoda, jsme můžete provést jednu z následujících akcí:  
  
-   Assert, který `ActualValue` vlastnost výjimky (druhý parametr `ArgumentOutOfRangeException` konstruktor) je větší než počáteční zůstatek. Tato možnost vyžaduje, že jsme test `ActualValue` vlastnost výjimky proti `beginningBalance` proměnné zkušební metody a také vyžaduje poté ověřte, že `ActualValue` je větší než nula.  
  
-   Assert, že zpráva (třetí parametr konstruktoru) obsahuje `DebitAmountExceedsBalanceMessage` definované v `BankAccount` třídy.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=fullName> Metoda v částí Microsoft unit test framework umožňuje nám ověřit druhá možnost bez výpočtů, které jsou požadovány první možnosti.  
  
 Druhý pokus o na úprava `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` může vypadat například:  
  
```csharp  
[TestMethod]  
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()  
{  
    // arrange  
    double beginningBalance = 11.99;  
    double debitAmount = 20.0;  
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);  
  
    // act  
    try  
    {  
        account.Debit(debitAmount);  
    }  
    catch (ArgumentOutOfRangeException e)  
    {  
        // assert  
        StringAssert.Contains(e.Message, BankAccount. DebitAmountExceedsBalanceMessage);  
    }  
}  
```  
  
 **Testování, přepisování a opakovat analýzu**  
  
 Když testujeme metody test s různými hodnotami, dojde k jsme tyto skutečnosti:  
  
1.  Pokud jsme catch opravte chyby pomocí assert kde `debitAmount` větší než balance, `Contains` předá assert, výjimka je ignorován a proto metodu testovací předá. Toto je chování, které má být.  
  
2.  Pokud používáme `debitAmount` je menší než 0, assert nezdaří, protože je vrácená nesprávný chybová zpráva. Assert se také nezdaří, pokud zavedeme dočasného `ArgumentOutOfRange` výjimky na jiný bod v metodě v cestě kódu test. Toto příliš je funkční.  
  
3.  Pokud `debitAmount` hodnota je platná (tj, méně než zůstatek ale větší než nula, žádné je byla zachycena výjimka, tak assert se nikdy zachycena. Metoda testovací předá. Toto není funkční, protože chceme metodu test nezdaří, pokud nedojde k výjimce.  
  
 Třetí fakt je chybou v našem testu metoda. Se pokusit o vyřešení problému, přidáme <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> assert na konci testu metody pro zpracování případu, kdy je vyvolána žádná výjimka.  
  
 Ale opětovném testování ukazuje, že test nyní selže, pokud je správná výjimka zachycena. Příkaz catch obnoví výjimku a metodu bude pokračovat v provádění, nové assert po selhání. Nové problém vyřešíte přidáme `return` příkaz po `StringAssert`. Opětovném testování potvrdí, že vyřešili jsme naše problémy. Naše finální verzi `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` vypadá podobně jako následující:  
  
```csharp  
[TestMethod]  
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()  
{  
    // arrange  
    double beginningBalance = 11.99;  
    double debitAmount = 20.0;  
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);  
  
    // act  
    try  
    {  
        account.Debit(debitAmount);  
    }  
    catch (ArgumentOutOfRangeException e)  
    {  
        // assert  
        StringAssert.Contains(e.Message, BankAccount. DebitAmountExceedsBalanceMessage);  
        return;  
    }  
    Assert.Fail("No exception was thrown.");  
}  
  
```  
  
 V této části konečné v práci jsme jste provedli zlepšení našeho testovacího kódu vedla k robustnější a informativní zkušební metody. Ale je důležité, navíc analysis také vedla k lepší kódu v našem projektu v rámci testu.
