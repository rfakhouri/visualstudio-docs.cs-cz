---
title: "Testování částí | Microsoft Docs"
ms.custom: 
ms.date: 2016-01-07
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.UnitTest.CreateUnitTest
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4f74ecf0bf6df346383fccea7e72604c1ffef662
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="unit-test-basics"></a>Základní informace o testech jednotek

Zkontrolujte, že váš kód funguje podle očekávání tím vytváření a spouštění testování částí. Je volána testování, protože rozdělíte dolů funkce vašeho programu do diskrétní možností intenzivního testování chování, které můžete testovat jako jednotlivých částí *jednotky*. Visual Studio Průzkumníka testů poskytuje flexibilní a efektivní způsob, jak spustit testy částí a zobrazit jejich výsledky v sadě Visual Studio. Visual Studio nainstaluje testování architektury pro spravovaná a nativní kód částí společnosti Microsoft. Použití *framework testování částí* vytvářet testy částí, spouštění je a ohlásí výsledky tyto testy. Testování částí spusťte při provádění změn pro testování, aby váš kód stále funguje správně. Visual Studio Enterprise můžete k tomu automaticky s [Live testování částí](live-unit-testing-intro.md), který zjistí testy vliv kódu změní a běží na pozadí během psaní.

Testování částí má největší vliv na kvalitu kódu, pokud je nedílnou součástí pracovního postupu vývoj softwaru. Jakmile napíšete funkce nebo další blok kódu aplikace, vytvořte testy částí, ověřte chování kód v reakci na standardní, hranice a nesprávný případech vstupních dat, a který Zkontrolujte předpoklady žádné explicitní nebo implicitní kód. S *vývoj řízený testy*, vytvoříte testy jednotek, než napíšete kód, abyste používat testy jednotek jako dokumentace návrhu a funkčních specifikací.

Můžete rychle vytvořit projektů testování a zkušební metody z vašeho kódu nebo ručně vytvořit testy podle potřeby. Pokud používáte IntelliTest prozkoumat kódu .NET, můžete vygenerovat testovací data a sada testů jednotek. Pro každý příkaz v kódu, je generována testovací vstup, spustí tento příkaz. Zjistěte, jak [generování testů částí kódu](http://msdn.microsoft.com/library/dn823749.aspx).

Průzkumníka testů můžete také spouštět třetích stran s otevřeným zdrojem systémů testů jednotek, které jste implementovali rozhraní rozšíření Průzkumníka testů. Můžete přidat řadu tyto architektury prostřednictvím Správce rozšíření Visual Studio a Galerii Visual Studio. V tématu [instalace systémů testů jednotek třetích stran](../test/install-third-party-unit-test-frameworks.md)

## <a name="quick-starts"></a>Rychlé spuštění

Úvod do testování částí, které přejdete přímo do kódování najdete v jednom z těchto témat:

- [Návod: Vytváření a spouštění testů částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)

- [Rychlý začátek: Vývoj řízený testy s použitím Průzkumníka testů](../test/quick-start-test-driven-development-with-test-explorer.md)

- [Zápis testů částí pro C/C++ v sadě Visual Studio](../test/writing-unit-tests-for-c-cpp.md)

## <a name="the-mybank-solution-example"></a>Příklad MyBank řešení

V tomto tématu používáme vývoj fiktivních aplikace s názvem `MyBank` jako příklad. Nepotřebujete skutečný kód podle vysvětlení v tomto tématu. Test metody jsou napsané v C# a zobrazovat pomocí Microsoft Unit Testing Framework pro spravovaný kód, ale koncepty snadno přenést do jiných jazyků a rozhraní.  
  
 ![Řešení MyBank](../test/media/ute_mybanksolution.png "UTE_MyBankSolution")  
  
 Naše o první pokus o navrhnout `MyBank` aplikace obsahuje komponentu účty, který představuje samostatný účet a jeho transakce s banka a databáze komponenty, která představuje funkci agregace a spravovat jednotlivé účty.  
  
 Vytvoříme `MyBank` řešení, které obsahuje dva projekty:  
  
-   `Accounts`  
  
-   `BankDb`  
  
 Naše o první pokus o návrhu `Accounts` projektu obsahovat třídu pro uložení základní informace o účtu, který určuje běžné funkce libovolného typu účtu, jako je uloží a odebírají prostředky z účtu a třídu rozhraní odvozené z rozhraní, které představuje účet kontroluje. Projekty účty začneme vytvořením následujících zdrojové soubory:  
  
-   `AccountInfo.cs`definuje základní informace o účtu.  
  
-   `IAccount.cs`definuje standard `IAccount` rozhraní pro účet, včetně metody pro uložení a odebrání prostředky z účtu a k načítání zůstatek účtu.  
  
-   `CheckingAccount.cs`obsahuje `CheckingAccount` třídu, která implementuje `IAccounts` rozhraní pro účet kontroluje.  
  
Víme ze zkušeností, že je tento jednou z věcí, které musíte provést odstoupení od účet kontroluje a ujistěte se, že stažené velikost je menší než zůstatek účtu. Proto jsme přepsat `IAccount.Withdaw` metoda v `CheckingAccount` pomocí metody, která kontroluje pro tuto podmínku. Metoda může vypadat například takto:  

```csharp
public void Withdraw(double amount)  
{  
    if(m_balance >= amount)  
    {  
        m_balance -= amount;  
    }  
    else  
    {  
        throw new ArgumentException(amount, "Withdrawal exceeds balance!")  
    }  
}
```

Teď, když máme nějaký kód, je čas pro testování.

## <a name="create-unit-test-projects-and-test-methods"></a>Vytváření projektů testování částí a testování metody

Často je rychlejší k vytvoření projektu testování částí a test jednotky zástupných procedur z vašeho kódu. Nebo můžete k vytvoření projektu testování částí a testy ručně v závislosti na vaše požadavky.  
  
 **Generování projektu testování částí a jednotkové testování zástupných procedur**  
  
1.  V okně editoru kódu, klikněte pravým tlačítkem a zvolte **vytvořit testování částí** v místní nabídce.  
  
     ![V okně editor zobrazení v místní nabídce](../test/media/createunittestsrightclick.png "CreateUnitTestsRightClick")  
  
2.  Klikněte na tlačítko OK potvrďte výchozí nastavení k vytvoření testů jednotek nebo změně hodnoty používané k vytvoření a název jednotka testování projektu a testování částí. Můžete vybrat kód, který je ve výchozím nastavení do metody test jednotky.  
  
     ![P & č. 45; klikněte v editoru a zvolte Vytvořit testování částí](../test/media/createunittestsdialog.png "CreateUnitTestsDialog")  
  
3.  Zástupných procedur test jednotky jsou vytvořené v nového projektu testů jednotek pro všechny metody ve třídě.  
  
     ![Testování částí vytvářejí](../test/media/createunittestsstubs.png "CreateUnitTestsStubs")  
  
4.  Teď přeskočit další postup [přidat kód do metody test jednotky](#BKMK_Writing_your_tests) , aby vaše smysluplný testování částí a všechny další jednotky testy, které chcete přidat do důkladně otestujte svůj kód.  
  
 **Vytvoření vaší testování částí projektu a jednotka testy ručně**  
  
 Projektu testování částí obvykle zrcadlí strukturu jeden kód projektu. V příkladu MyBank přidejte dva projektů testů jednotek s názvem `AccountsTests` a `BankDbTests` k `MyBanks` řešení. Názvy projektů testů jsou libovolný, ale přijetí standardní zásady vytváření názvů je vhodné.  
  
 **Přidání projektu testů jednotek do řešení:**  
  
1.  Na **soubor** nabídce zvolte **nový** a potom zvolte **projektu** (klávesnice Ctrl + Shift + N).  
  
2.  V dialogovém okně Nový projekt, rozbalte **nainstalovaná** uzlu, zvolte jazyk, který chcete použít pro projekt test a potom zvolte **testování**.  
  
3.  Chcete-li použít jeden z systémů testování částí Microsoft, zvolte **projektu testování částí** ze seznamu šablon projektu. Jinak zvolte šablonu projektu jednotky test framework, který chcete použít. K testování `Accounts` projektu našem příkladu by název projektu `AccountsTests`.  
  
    > [!WARNING]
    >  Ne všechny systémů testů jednotek třetích stran s otevřeným zdrojem zadejte šablona projektu sady Visual Studio. Informace o vytvoření projektu naleznete v dokumentu framework.  
  
4.  Ve vašem projektu testování částí přidáte odkaz na projekt kódu testovaného v našem příkladu do projektu účty.  
  
     Pokud chcete vytvořit odkaz na projekt kódu:  
  
    1.  Vyberte projekt v Průzkumníku řešení.  
  
    2.  Na **projektu** nabídky, zvolte **přidat odkaz na**.  
  
    3.  Otevřete v dialogovém okně Správce odkazů **řešení** uzel a zvolte **projekty**. Vyberte název projektu kódu a zavřete dialogové okno.  
  
 Každý projektu testů jednotek obsahuje třídy, které zrcadlení názvy tříd v projektu kódu. V našem příkladu `AccountsTests` projekt by obsahovat následující třídy:  
  
-   `AccountInfoTests`Třída obsahuje metody testů jednotek pro `AccountInfo` třídy v `BankAccount` projektu  
  
-   `CheckingAccountTests`Třída obsahuje metody testů jednotek pro `CheckingAccount` třídy.  
  
## <a name="write-your-tests"></a>Zápis testů

Jednotka testování framework, který používáte a Visual Studio IntelliSense provede zápis kódu pro testy částí pro projekt kódu. Pokud chcete spustit v Průzkumníku otestovat, většina architektury vyžadují přidat konkrétní atributy, které určují metody test jednotky. Rozhraní také poskytnout způsob – obvykle prostřednictvím assert – příkazy nebo atributy metody – indikující, zda metoda testovací vyhověla, nebo se nezdařilo. Ostatní atributy Identifikujte volitelné nastavení metody, které jsou při inicializaci třídy a před každou testovací metoda a rušením metody, které spouštějí po jednotlivých metod test a zničen třídy.  

Vzor AAA (uspořádat, Application Compatibility Toolkit, Assert) je běžný způsob zápis testů částí pro metodu v rámci testu.  

- **Uspořádat** části Metoda testování částí inicializuje objekty a nastaví hodnotu data, která je předána metodě v rámci testu.  

- **Act** části vyvolá metodu testovaného s uspořádaných parametry.  

- **Assert** části ověřuje, že akce metody testovaného chová podle očekávání.  

K testování `CheckingAccount.Withdraw` metoda našem příkladu jsme zápisu dva testy: jednu, která ověřuje standardní chování metody a ten, který ověřuje, že stažení o více než zůstatek se nezdaří. V `CheckingAccountTests` třída, jsme přidejte následující metody:  

```csharp
[TestMethod]  
public void Withdraw_ValidAmount_ChangesBalance()  
{  
    // arrange  
    double currentBalance = 10.0;  
    double withdrawal = 1.0;  
    double expected = 9.0;  
    var account = new CheckingAccount("JohnDoe", currentBalance);  
    // act  
    account.Withdraw(withdrawal);  
    double actual = account.Balance;  
    // assert  
    Assert.AreEqual(expected, actual);  
}  
  
[TestMethod]  
[ExpectedException(typeof(ArgumentException))]  
public void Withdraw_AmountMoreThanBalance_Throws()  
{  
    // arrange  
    var account = new CheckingAccount("John Doe", 10.0);  
    // act  
    account.Withdraw(20.0);  
    // assert is handled by the ExpectedException  
}
```

Všimněte si, že `Withdraw_ValidAmount_ChangesBalance` používá explicitního `Assert` příkaz k určení, zda metoda testovací předá nebo selže, zatímco `Withdraw_AmountMoreThanBalance_Throws` používá `ExpectedException` atribut, abyste zjistili úspěšnost zkušební metody. V pozadí částí unit test framework zabalí testovací metody v try/catch – příkazy. Ve většině případů pokud výjimka zachycena, metoda testovací selže a výjimka je ignorován. `ExpectedException` Atributu způsobí, že metoda testovací předání, pokud zadaná výjimka.  

Další informace o rozhraní testování částí Microsoft najdete v jednom z následujících témat:  

-   [Zápis testů částí pro rozhraní .NET Framework s infrastrukturou pro testování částí Microsoft Unit Test Framework pro spravovaný kód](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)  

-   [Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)  

## <a name="set-timeouts-for-unit-tests"></a>Nastavit časové limity pro testování částí

Chcete-li nastavit vypršení časového limitu na metodu jednotlivé testy:  

```csharp  
[TestMethod]  
[Timeout(2000)]  // Milliseconds  
public void My_Test()  
{ ...  
}  
```

Nastavit časový limit pro maximální povolený počet:  

```csharp
[TestMethod]  
[Timeout(TestTimeout.Infinite)]  // Milliseconds  
public void My_Test ()  
{ ...  
}
```

## <a name="run-tests-in-test-explorer"></a>Spuštění testů Průzkumníka testů

Při sestavování testovacího projektu testů se zobrazí v Průzkumníku otestovat. Pokud není viditelná Průzkumníka testů, zvolte **Test** v sadě Visual Studio nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.  
  
 ![Průzkumníka testů jednotek](../test/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")  
  
 Při spuštění, zápisu a znovu spusťte testy, výchozí zobrazení Průzkumníka testů zobrazí výsledky v skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a  **Nejde spustit testy**. Můžete použít záhlaví skupiny k otevření zobrazení, které se zobrazí všechny je testů v této skupině.  
  
 Testy v libovolném zobrazení můžete také filtrovat podle odpovídající textu do vyhledávacího pole na globální úrovni, nebo výběrem jeden z předdefinovaných filtrů. Všechny výběr testy můžete spustit kdykoli. Výsledky testu spustit se okamžitě zřejmá panelu průchodu nebo selže v horní části okna Průzkumníka. Když vyberete test jsou zobrazené podrobnosti metoda výsledků testu.  
  
### <a name="run-and-view-tests"></a>Spustit a zobrazit testy

Panel nástrojů Průzkumníka testů umožňuje zjistit, organizovat a spustit testy, které vás zajímají.  
  
 ![Spouštění testů z panelu nástrojů Průzkumníka testů](../test/media/ute_toolbar.png "UTE_ToolBar")  
  
 Můžete zvolit **spustit všechny** spustit všechny testy, nebo zvolte **spustit** vybrat podmnožinu testů ke spuštění. Po spuštění sada testů se zobrazí souhrn testovacím běhu v dolní části okna Průzkumníka testů. Vyberte testovací Chcete-li zobrazit podrobnosti o testu v dolním podokně. Zvolte **otevřete testovací** z místní nabídky (klávesnice: F12) Chcete-li zobrazit zdrojový kód pro vybrané test.  
  
 Pokud jednotlivé testy žádné závislosti, které je zabránit spouštění v libovolném pořadí, zapnout spuštění testu paralelní s ![UTE &#95; parallelicon & č. 45; malá](../test/media/ute_parallelicon-small.png "UTE_parallelicon malá") přepínací tlačítko na panelu nástrojů. To může výrazně snížit čas potřebný k spustit všechny testy.  
  
### <a name="run-tests-after-every-build"></a>Spouštění testů po každé sestavení

> [!WARNING]
> Po každé sestavení je podporován pouze ve Visual Studio Enterprise testů spuštěné jednotek.  

|||  
|-|-|  
|![Po sestavení spustit](../test/media/ute_runafterbuild_btn.png "UTE_RunAfterBuild_btn")|Spouštění testů jednotek po každé místní sestavení, zvolte **Test** na standardní nabídce zvolte **spustit testy po sestavení** na panelu nástrojů Průzkumníka testů.|  
  
### <a name="filter-and-group-the-test-list"></a>Filtr a seskupení seznamu testů

Když máte velký počet testů, můžete zadat Průzkumníka testů vyhledávacího pole pro filtrování seznamu podle zadaného řetězce. Můžete omezit další výběrem ze seznamu filtru filtru událost.  
  
 ![Prohledat kategorie filtru](../test/media/ute_searchfilter.png "UTE_SearchFilter")  
  
|||  
|-|-|  
|![Tlačítko Testovat Explorer skupiny](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn")|Pro seskupení testů podle kategorie, vyberte **Group By** tlačítko.|  
  
 Další informace najdete v tématu [spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)  
  
## <a name="qa"></a>MODUL OTÁZKY A ODPOVĚDI

**Otázka: Jak mohu ladit testování částí?**  
  
**Odpověď:** pomocí Průzkumníka testů pro spuštění relace ladění testů. Procházení kódu s ladicím programu sady Visual Studio bezproblémově přejdete oběma směry mezi testy částí a projekt v rámci testu. Spustit ladění:  
  
1.  V editoru Visual Studio nastavte zarážky v jedné nebo několika metod testovací, které chcete ladit.  
  
    > [!NOTE]
    > Vzhledem k tomu, že testovací metody můžete spustit v libovolném pořadí, nastavte zarážky v všechny testovací metody, které chcete ladit.  
  
2.  V Průzkumníku testování vybrat metody testu a pak zvolte **ladění vybrané testy** z místní nabídky.  
  
Podrobné informace o [ladění testování částí](../debugger/debugging-in-visual-studio.md).  
  
 **Otázka: Pokud používám TDD, postup generování kódu z mé testy?**  
  
 **Odpověď:** pomocí IntelliSense pro generování třídy a metody ve vašem projektu kódu. Napsat příkaz v testovací metodu, která volá třída nebo metoda, kterou chcete vygenerovat, a otevřete nabídku IntelliSense v části volání. Pokud je volání konstruktoru nové třídy, vyberte **vygenerovat nový typ** z nabídky a postupujte podle průvodce a vloží třídu do projektu kódu. Pokud je volání do metody, zvolte **generovat nové metody** z nabídky IntelliSense.  
  
 ![Metoda se zakázaným inzerováním Intellisense nabídka Generovat](../test/media/ute_generatemethodstubintellisense.png "UTE_GenerateMethodStubIntellisense")  
  
 **Otázka: je možné vytvářet testy částí, které provést několik sad dat jako vstup pro spuštění testu?**  
  
 **Odpověď:** Ano. *Řízené daty testovací metody* umožňují testování rozsah hodnot pomocí metody testu jedné jednotky. Použití `DataSource` atribut pro testovací metody, která určuje zdroje dat a tabulky, který obsahuje hodnoty proměnné, které chcete testovat.  V těle metoda přiřadit hodnoty řádků pomocí proměnných `TestContext.DataRow[` *ColumnName* `]` indexer.  
  
> [!NOTE]
> Tyto postupy lze použít pouze k testování metody, které můžete psát pomocí částí Microsoft unit test framework pro spravovaný kód. Pokud používáte jiné rozhraní, najdete v dokumentaci framework pro ekvivalentní funkce.  
  
 Předpokládejme například, přidáme metodu nepotřebné k `CheckingAccount` třídu, která je s názvem `AddIntegerHelper`. `AddIntegerHelper`přidá dvě celá čísla.  
  
 K vytvoření testu řízené daty pro `AddIntegerHelper` metoda, nejdřív vytvoříme databáze Access s názvem `AccountsTest.accdb` a tabulku s názvem `AddIntegerHelperData`. `AddIntegerHelperData` Tabulka definuje sloupce, které chcete zadat první a druhý operandy přidání a ve sloupci k určení očekávaný výsledek. Počet řádků jsme vyplní s příslušnými hodnotami.  
  
```csharp
[DataSource(  
    @"Provider=Microsoft.ACE.OLEDB.12.0;Data Source=C:\Projects\MyBank\TestData\AccountsTest.accdb",   
    "AddIntegerHelperData"  
)]  
[TestMethod()]  
public void AddIntegerHelper_DataDrivenValues_AllShouldPass()  
{  
    var target = new CheckingAccount();  
    int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);  
    int y = Convert.ToInt32(TestContext.DataRow["SecondNumber"]);   
    int expected = Convert.ToInt32(TestContext.DataRow["Sum"]);  
    int actual = target.AddIntegerHelper(x, y);  
    Assert.AreEqual(expected, actual);  
}
```

S atributy metoda spustí jednou pro každý řádek v tabulce. Průzkumníka testů hlásí selhání testu pro metodu, pokud všechny iterace selže. Na panelu informací o výsledky testu pro metodu ukazuje metodu průchodu nebo selhání stav pro každý řádek dat.  
  
 Další informace o [testy jednotek řízené daty](../test/how-to-create-a-data-driven-unit-test.md).  
  
 **Otázka: je možné zobrazit, kolik z vlastního kódu je testován Moje testování částí?**  
  
 **Odpověď:** Ano. Můžete určit dobu, ve skutečnosti je během testování testů jednotek pomocí nástroje Visual Studio code pokrytí kódu. Jsou podporované jazyky nativní a spravovaná a všech systémů testů jednotek, které lze spustit Unit Test Framework.  
  
 Pokrytí kódu můžete spustit na vybrané testy nebo na všechny testy v řešení. Okno výsledků pokrytí kódu zobrazuje procento bloků kódu produktu, které byly vykonávají řádku, funkce, třída, obor názvů a modulu.  
  
 Spouštění pokrytí kódu pro metody testu v řešení, zvolte **testy** v nabídce sady Visual Studio a zvolte **analýza pokrytí kódu**.  
  
 Pokrytí výsledky se zobrazí v okně Výsledky pokrytí kódu.  
  
 ![Výsledky pokrytí kódu](../test/media/ute_codecoverageresults.png "UTE_CodeCoverageResults")  
  
 Další informace o [pokrytí kódu](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md) .  
  
 **Otázka: jak můžete otestovat metody v vlastního kódu, které mají vnější závislosti?**  
  
 **Odpověď:** Ano. Pokud máte Visual Studio Enterprise, Microsoft Fakes lze použít s zkušební metody, které můžete psát pomocí systémů testování částí pro spravovaný kód.  
  
 Microsoft Fakes používá dva přístupy k vytváření tříd substitute pro externí závislosti:
  
1.  *Zástupných procedur* vygenerovat substitute třídy odvozené z rozhraní nadřazené cílové třídy závislostí. Se zakázaným inzerováním metody lze nahradit veřejné virtuální metody cílové třídy.  
  
2.  *Překrytí* pomocí modulu runtime instrumentace přesměrovat volání do cílové metody metodě shim substitute pro jiný virtuální metody.  
  
V obou přístupů použijete generovaného delegáty volání do metody závislostí určit způsob chování, které chcete v metodě test.  
  
Další informace o [izolace metody test jednotky s Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md).  
  
 **Otázka: je možné použít jiné systémů testů jednotek vytvářet testy částí?**  
  
 **Odpověď:** Ano, postupujte podle těchto kroků [najít a nainstalovat ostatní platformy](../test/install-third-party-unit-test-frameworks.md). Po restartování sady Visual Studio otevřete řešení vytváření testů jednotek a poté vyberte nainstalované rozhraní tady:  
  
 ![Vyberte jiné nainstalované částí unit test framework](../test/media/createunittestsdialogextensions.png "CreateUnitTestsDialogExtensions")  
  
 Vaše zástupných procedur test jednotky se vytvoří pomocí rozhraní vybrané.
