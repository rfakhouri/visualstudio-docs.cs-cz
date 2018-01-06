---
title: "Testování Visual C# – kód v aplikaci UWP částí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23cb0d82-0451-464e-98ea-fa66e7010ead
caps.latest.revision: "19"
ms.author: douge
manager: douge
ms.workload: uwp
ms.openlocfilehash: 63018bdae7cec687ccf81d53ef6e35ecdc169c83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="unit-testing-visual-c-code-in-a-uwp-app"></a>Testování Visual C# – kód v aplikaci UWP částí
Toto téma popisuje jeden způsob, jak vytvářet testy částí pro třídu Visual C# v aplikaci UWP. Třída Rooter ukazuje nepřesných vědomosti limit teoreticky z calculus implementací funkce pro výpočet odhad druhou odmocninu čísla na zadanou mocninu. Matematické výrazy aplikace potom pomocí této funkce můžete zobrazit uživatele fun věcí, které lze provést pomocí matematické.  
  
 Toto téma ukazuje, jak používat jako první krok při vývoji testování částí. V tento přístup napíšete testovací metodu, která ověřuje konkrétní chování v systému, která jsou testování a potom napíšete kód, který projde testem. Provedením změn v pořadí podle následujících postupů můžete nechat provést zpětnou Tato strategie prvním zápisu kód, který chcete otestovat a zapište si testování částí.  
  
 Toto téma také vytvoří jeden řešení sady Visual Studio a samostatné projekty pro testy částí a knihovnu DLL, kterou chcete testovat. Testy jednotek můžete zahrnout taky přímo v projektu knihovny DLL, nebo můžete vytvořit samostatné řešení pro testování částí a knihovny DLL.  
  
> [!NOTE]
>  Visual Studio Community, Enterprise a Professional poskytnutí dodatečných funkcí pro testování jednotky.  
>   
>  -   Použijte libovolnou architekturu test jednotky třetích stran s otevřeným zdrojem, vytvořený adaptér rozšíření pro Microsoft testování Explorer. Můžete také analyzovat a zobrazit informace o pokrytí kódu pro testy.  
> -   Spouštění testů po každé sestavení.  
> -   VS Enterprise také obsahuje Microsoft Fakes, představuje izolace rozhraní pro spravovaný kód, který vám umožní zaměřit testy na vlastní kód nahrazením testovacího kódu pro systém a funkce třetích stran.  
>   
>  Další informace najdete v tématu [ověřování kódu pomocí testy jednotek](http://msdn.microsoft.com/library/dd264975.aspx) v knihovně MSDN.  
  
##  <a name="BKMK_In_this_topic"></a>V tomto tématu  
 [Vytvoření řešení a projektu testování částí](#BKMK_Create_the_solution_and_the_unit_test_project)  
  
 [Ověřte, zda spustit testy v Průzkumníka testů](#BKMK_Verify_that_the_tests_run_in_Test_Explorer)  
  
 [Přidejte do projektu matematické výrazy Rooter – třída](#BKMK_Add_the_Rooter_class_to_the_Maths_project)  
  
 [Několik k testovacímu projektu do projektu aplikace](#BKMK_Couple_the_test_project_to_the_app_project)  
  
 [Opakované posílení testy a ujistěte se, je předat](#BKMK_Iteratively_augment_the_tests_and_make_them_pass)  
  
 [Ladění selhání testu](#BKMK_Debug_a_failing_test)  
  
 [Refaktorovat kód](#BKMK_Refactor_the_code_)  
  
##  <a name="BKMK_Create_the_solution_and_the_unit_test_project"></a>Vytvoření řešení a projektu testování částí  
  
1.  Na **soubor** nabídce zvolte **nový**a potom zvolte **nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **nainstalovaná**, pak rozbalte **Visual C#** a zvolte **univerzální pro Windows**. Zvolte **prázdnou aplikaci** ze seznamu šablon projektu.  
  
3.  Název projektu `Maths` a zajistěte, aby **vytvořit adresář pro řešení** je vybrána.  
  
4.  V Průzkumníku řešení, zvolte název řešení a potom vyberte **přidat** z místní nabídky a potom zvolte **nový projekt**.  
  
5.  V **nový projekt** dialogové okno, rozbalte seznam **nainstalovaná**, pak rozbalte **Visual C#** a zvolte **univerzální pro Windows** . Zvolte **knihovny Test jednotky (Universal Windows)** ze seznamu šablon projektu.  
  
     ![Vytvoření projektu testování částí](../test/media/ute_cs_windows_createunittestproject.png "UTE_Cs_windows_CreateUnitTestProject")  
  
6.  Otevřete UnitTest1.cs v editoru Visual Studio.  
  
    ```csharp  
  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using Microsoft.VisualStudio.TestPlatform.UnitTestFramework;  
    using Maths;  
  
    namespace RooterTests  
    {  
        [TestClass]  
        public class UnitTest1  
  
            [TestMethod]  
            public void TestMethod1()  
            {  
  
            }  
  
    ```  
  
     Všimněte si, že:  
  
    1.  Každý test se definuje pomocí `[TestMethod]`. Metoda test musí vracet typ void a nemůže mít žádné parametry.  
  
    2.  Test metody musí být v třídě označených pomocí `[TestClass]` atribut.  
  
         Když se testy spouštějí, se vytvoří instance třídy každého testu. Test metody jsou volány v neurčené pořadí.  
  
    3.  Můžete definovat speciální metody, které jsou vyvolány před a po každém modulu, třída nebo metoda. Další informace najdete v tématu [používání členů oboru názvů Microsoft.VisualStudio.TestTools.UnitTesting při testech jednotek](../test/using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md) v knihovně MSDN.  
  
##  <a name="BKMK_Verify_that_the_tests_run_in_Test_Explorer"></a>Ověřte, zda spustit testy v Průzkumníka testů  
  
1.  Vložit některé testovací kód v `TestMethod1` z **UnitTest1.cs** souboru:  
  
    ```csharp  
  
    [TestMethod]  
    public void TestMethod1()  
    {  
        Assert.AreEqual(0, 0);  
    }  
  
    ```  
  
     Všimněte si, že `Assert` třída poskytuje několik statických metod, které můžete ověřit výsledky v testovací metody.  
  
2.  Na **Test** nabídce zvolte **spustit** a potom zvolte **spustit všechny**.  
  
     K testovacímu projektu vytvoří a spustí. Zobrazí se okno Průzkumníka testů a testovací je uveden v části **předán testy**. Souhrn panelu v dolní části okna poskytuje další informace o vybrané testu.  
  
     ![Testování Explorer](../test/media/ute_cpp_testexplorer_testmethod1.png "UTE_Cpp_TestExplorer_TestMethod1")  
  
##  <a name="BKMK_Add_the_Rooter_class_to_the_Maths_project"></a>Přidejte do projektu matematické výrazy Rooter – třída  
  
1.  V Průzkumníku řešení, vyberte **matematické výrazy** název projektu. V místní nabídce vyberte příkaz **přidat**a potom **třída**.  
  
2.  Název souboru – třída`Rooter.cs`  
  
3.  Přidejte následující kód do třídy Rooter **Rooter.cs** souboru:  
  
    ```csharp  
  
    public Rooter()  
    {  
    }  
  
    // estimate the square root of a number  
    public double SquareRoot(double x)  
    {  
        return 0.0;  
    }  
  
    ```  
  
     `Rooter` Třída deklaruje konstruktor a `SqareRoot` odhadu metoda.  
  
4.  `SqareRoot` Metoda je pouze minimální implementace, právě dostatek otestovat základní strukturu testování instalačního programu.  
  
##  <a name="BKMK_Couple_the_test_project_to_the_app_project"></a>Několik k testovacímu projektu do projektu aplikace  
  
1.  Do projektu RooterTests přidáte odkaz na aplikaci matematické výrazy.  
  
    1.  V Průzkumníku řešení, vyberte **RooterTests** projektu a potom zvolte **přidat odkaz na...**  v místní nabídce.  
  
    2.  Na **přidat odkaz - RooterTests** dialogové okno, rozbalte seznam **řešení** a zvolte **projekty**. Vyberte **matematické výrazy** položky.  
  
         ![Přidat odkaz na projekt matematické výrazy](../test/media/ute_cs_windows_addreference.png "UTE_Cs_windows_AddReference")  
  
2.  Přidat pomocí příkazu k souboru UnitTest1.cs:  
  
    1.  Otevřete **UnitTest1.cs**.  
  
    2.  Přidejte tento kód níže `using Microsoft.VisualStudio.TestPlatform.UnitTestFramework;` řádku:  
  
        ```csharp  
        using Maths;  
        ```  
  
3.  Přidáte test, který používá funkci Rooter. Přidejte následující kód, který **UnitTest1.cpp**:  
  
    ```csharp  
    [TestMethod]  
    public void BasicTest()  
    {  
        Maths.Rooter rooter = new Rooter();  
        double expected = 0.0;  
        double actual = rooter.SquareRoot(expected * expected);  
        double tolerance = .001;  
        Assert.AreEqual(expected, actual, tolerance);  
    }  
  
    ```  
  
4.  Sestavte řešení.  
  
     Nový test se zobrazí v Průzkumníku testování v **není spuštění testů** uzlu.  
  
5.  V Průzkumníku testu zvolte **spustit všechny**.  
  
     ![Základní Test proběhl](../test/media/ute_cpp_testexplorer_basictest.png "UTE_Cpp_TestExplorer_BasicTest")  
  
 Máte nastavení testu a projektů kód a ověřit, že můžete spustit testy, které běží funkce v projektu kódu. Teď můžete začít zapisovat skutečné testy a kódu.  
  
##  <a name="BKMK_Iteratively_augment_the_tests_and_make_them_pass"></a>Opakované posílení testy a ujistěte se, je předat  
  
1.  Přidejte nový test:  
  
    ```csharp  
    [TestMethod]  
    public void RangeTest()  
    {  
        Rooter rooter = new Rooter();  
        for (double v = 1e-6; v < 1e6; v = v * 3.2)  
        {  
            double expected = v;  
            double actual = rooter.SquareRoot(v*v);  
            double tolerance = ToleranceHelper(expected);  
            Assert.AreEqual(expected, actual, tolerance);  
        }  
    }  
  
    ```  
  
    > [!TIP]
    >  Doporučujeme neměnit testy, které uplynuly. Místo toho přidejte nový test, aktualizujte kód tak, aby test bude provedeno úspěšně a poté přidejte jiného testu, a tak dále.  
    >   
    >  Pokud vaši uživatelé změnit jejich požadavky, zakažte testy, které již nejsou správné. Zápis nových testů a jejich fungování jeden po druhém, stejným způsobem jako přírůstkové.  
  
2.  V Průzkumníku testu zvolte **spustit všechny**.  
  
3.  Test se nezdaří.  
  
     ![Selhání RangeTest](../test/media/ute_cpp_testexplorer_rangetest_fail.png "UTE_Cpp_TestExplorer_RangeTest_Fail")  
  
    > [!TIP]
    >  Ihned po jste napsali ho, ověřte, že každý test se nezdaří. To umožňuje vyhnout se snadno chybu zápisu testu, který nikdy selže.  
  
4.  Vylepšení testovaného kódu tak, aby nový test předá. Změna `SqareRoot` fungovat v **Rooter.cs** k tomuto:  
  
    ```csharp  
    public double SquareRoot(double x)  
    {  
        double estimate = x;  
        double diff = x;  
        while (diff > estimate / 1000)  
        {  
            double previousEstimate = estimate;  
            estimate = estimate - (estimate * estimate - x) / (2 * estimate);  
            diff = Math.Abs(previousEstimate - estimate);  
        }  
        return estimate;  
    }  
  
    ```  
  
5.  Sestavte řešení a potom vyberte v Průzkumníku Test **spustit všechny**.  
  
     Všechny tři testy teď předat.  
  
> [!TIP]
>  Vývoj kódu přidáním testy jeden najednou. Ujistěte se, že všechny testy byly úspěšné po každé iteraci.  
  
##  <a name="BKMK_Debug_a_failing_test"></a>Ladění selhání testu  
  
1.  Přidání jiného testu na **UnitTest1.cs**:  
  
    ```csharp  
    // Verify that negative inputs throw an exception.  
    [TestMethod]  
    public void NegativeRangeTest()  
    {  
        string message;  
        Rooter rooter = new Rooter();  
        for (double v = -0.1; v > -3.0; v = v - 0.5)  
        {  
            try  
            {  
                // Should raise an exception:  
                double actual = rooter.SquareRoot(v);  
  
                message = String.Format("No exception for input {0}", v);  
                Assert.Fail(message);  
            }  
            catch (ArgumentOutOfRangeException ex)  
            {  
                continue; // Correct exception.  
            }  
            catch (Exception e)  
            {  
                message = String.Format("Incorrect exception for {0}", v);  
                Assert.Fail(message);  
            }  
        }  
    }  
  
    ```  
  
2.  V Průzkumníku testu zvolte **spustit všechny**.  
  
     Test se nezdaří. Zvolte název testu v Průzkumníku otestovat. Je označený selhání kontrolního výrazu. Zpráva o neúspěšném zpracování je zobrazen v podokně podrobností Průzkumníka testů.  
  
     ![NegativeRangeTests se nezdařilo](../test/media/ute_cpp_testexplorer_negativerangetest_fail.png "UTE_Cpp_TestExplorer_NegativeRangeTest_Fail")  
  
3.  Chcete-li zjistit, proč test se nezdaří, kroku prostřednictvím funkce:  
  
    1.  Nastavit zarážky na začátku `SquareRoot` funkce.  
  
    2.  V místní nabídce selhání testu, zvolte **ladění vybrané testy**.  
  
         Při spuštění, zastavení u zarážky, projděte kód.  
  
    3.  Přidejte kód do metody Rooter k zachycení výjimky:  
  
        ```csharp  
        public double SquareRoot(double x)  
        {  
            if (x < 0.0)  
            {  
                throw new ArgumentOutOfRangeException();  
        }  
  
        ```  
  
    1.  V Průzkumníku otestovat, zvolte **spustit všechny** test opravené metody a ujistěte se, že nebyla zavedena regrese.  
  
 Všechny testy byly úspěšné teď.  
  
 ![Všechny testy byly úspěšné](../test/media/ute_ult_alltestspass.png "UTE_ULT_AllTestsPass")  
  
##  <a name="BKMK_Refactor_the_code_"></a>Refaktorovat kód  
 **Zjednodušení centrální výpočtu ve funkci SquareRoot.**  
  
1.  Změňte implementaci výsledek  
  
    ```csharp  
    // old code  
    //result = result - (result*result - v)/(2*result);  
    // new code  
    result = (result + v/result) / 2.0;  
  
    ```  
  
2.  Zvolte **spustit všechny** test refactored metody a ujistěte se, že nebyla zavedena regrese.  
  
> [!TIP]
>  Stabilní sadu testů pro funkční jednotku poskytuje jistotu, že nebyla zavedena chyby při změně kódu.  
  
 **Refaktorovat testovacího kódu eliminovat duplicitní kódu.**  
  
 Všimněte si, že `RangeTest` metoda pevný kódy jmenovatel tolerance proměnné, která se používá v `Assert` metoda. Pokud máte v plánu přidat další testy, které používají stejný výpočet tolerance, použití hodnotu pevně zakódovaná na více místech může vést k chyby.  
  
1.  Soukromá metoda přidejte do třídy Unit1Test vypočítat hodnotu proti chybám a místo toho volejte tuto metodu.  
  
    ```csharp  
    private double ToleranceHelper(double expected)  
    {  
        return expected / 1000;  
    }  
  
    ...  
  
    [TestMethod]  
    public void RangeTest()  
    {  
        ...  
        // old code  
        // double tolerance = expected/1000;  
        // new code  
        double tolerance = ToleranceHelper(expected);  
        Assert.AreEqual(expected, actual, tolerance);  
    }  
    ...  
  
    ```  
  
2.  Zvolte **spustit všechny** test refactored metody a ujistěte se, že nebyla zavedena k chybě.  
  
> [!NOTE]
>  Pokud chcete přidat do třídy testovací Pomocná metoda, nepřidávejte `[TestMethod]` atribut do metody. Průzkumníka testů nezaregistruje metodu ke spuštění.
