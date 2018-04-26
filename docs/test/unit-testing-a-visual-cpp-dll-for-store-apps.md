---
title: Postup testování knihovny DLL Visual C++ pro aplikace UWP v sadě Visual Studio
ms.date: 02/15/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: mblome
manager: douge
ms.workload:
- uwp
author: mikeblome
ms.openlocfilehash: 717786fea5d0ae355af5b8ea4993932a95d01196
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-test-a-visual-c-dll"></a>Postup testování knihovny DLL Visual C++

Toto téma popisuje jeden způsob, jak vytvářet testy částí pro knihovnu DLL C++ pro aplikace pro univerzální platformu Windows (UWP) pomocí Microsoft Test Framework pro C++. Knihovny DLL RooterLib ukazuje nepřesných vědomosti limit teoreticky z calculus implementací funkce pro výpočet odhad druhou odmocninu čísla na zadanou mocninu. Knihovny DLL pak může být součástí aplikace pro UPW, který ukazuje uživatele fun věcí, které lze provést pomocí matematické.

 Toto téma ukazuje, jak používat jako první krok při vývoji testování částí. V tento přístup napíšete testovací metodu, která ověřuje konkrétní chování v systému, která jsou testování a potom napíšete kód, který projde testem. Provedením změn v pořadí podle následujících postupů můžete nechat provést zpětnou Tato strategie prvním zápisu kód, který chcete otestovat a zapište si testování částí.

 Toto téma také vytvoří jeden řešení sady Visual Studio a samostatné projekty pro testy částí a knihovnu DLL, kterou chcete testovat. Testy jednotek můžete zahrnout taky přímo v projektu knihovny DLL, nebo můžete vytvořit samostatné řešení pro testování částí a. KNIHOVNY DLL. V tématu [přidání testů částí do stávajících aplikací C++](../test/unit-testing-existing-cpp-applications-with-test-explorer.md) tipy, které struktura používat.

##  <a name="Create_the_solution_and_the_unit_test_project"></a> Vytvoření řešení a projektu testování částí

1.  Na **soubor** nabídce zvolte **nový** > **nový projekt...** .

2.  V dialogovém okně Nový projekt rozbalte **nainstalovaná** > **Visual C++** a zvolte **univerzální pro Windows**. Zvolte **jednotky testování aplikace (univerzální pro Windows)** ze seznamu šablon projektu.

3.  Název projektu `RooterLibTests`, zadejte umístění, název řešení `RooterLib`; a zajistěte, aby **vytvořit adresář pro řešení** je zaškrtnuté.

     ![Zadejte název řešení a projektu a umístění](../test/media/ute_cpp_windows_unittestlib_createspecs.png "UTE_Cpp_windows_UnitTestLib_CreateSpecs")

4.  V novém projektu, otevřete **unittest1.cpp**.

     ![unittest1.cpp](../test/media/ute_cpp_windows_unittest1_cpp.png "UTE_Cpp_windows_unittest1_cpp")

     Všimněte si, že:

    -   Každý test se definuje pomocí `TEST_METHOD(YourTestName){...}`.

         Nemáte k zápisu podpis běžné funkce. Makro TEST_METHOD vytvoří podpis. Makro generuje instance funkce, který vrátí prázdnou hodnotu. Také vytváří statickou funkci, která vrací informace o metodě testu. Tyto informace umožňuje Průzkumníka testů najít metodu.

    -   Test metody jsou seskupené do třídy pomocí `TEST_CLASS(YourClassName){...}`.

         Když se testy spouštějí, se vytvoří instance třídy každého testu. Test metody jsou volány v neurčené pořadí. Můžete definovat speciální metody, které jsou vyvolány před a po každém modulu, třída nebo metoda. Další informace najdete v tématu [pomocí atributu Microsoft.VisualStudio.TestTools.CppUnitTestFramework](../test/using-microsoft-visualstudio-testtools-cppunittestframework.md) v knihovně MSDN.

##  <a name="Verify_that_the_tests_run_in_Test_Explorer"></a> Ověřte, zda spustit testy v Průzkumníka testů

1.  Vložte některá testovacího kódu:

    ```cpp
    TEST_METHOD(TestMethod1)
    {
        Assert::AreEqual(1,1);
    }
    ```

     Všimněte si, že `Assert` třída poskytuje několik statických metod, které můžete ověřit výsledky v testovací metody.

2.  Na **Test** nabídce zvolte **spustit** a potom zvolte **spustit všechny**.

     K testovacímu projektu vytvoří a spustí. Zobrazí se okno Průzkumníka testů a testovací je uveden v části **předán testy**. Souhrn panelu v dolní části okna poskytuje další informace o vybrané testu.

     ![Testování Explorer](../test/media/ute_cpp_testexplorer_testmethod1.png "UTE_Cpp_TestExplorer_TestMethod1")

##  <a name="Add_the_DLL_project_to_the_solution"></a> Do řešení přidat projektu knihovny DLL

1.  V Průzkumníku řešení vyberte název řešení. V místní nabídce vyberte příkaz **přidat**a potom **přidat nový projekt**.

     ![Vytvoření projektu RooterLib](../test/media/ute_cpp_windows_rooterlib_create.png "UTE_Cpp_windows_RooterLib_Create")

2.  V **přidat nový projekt** dialogovém okně vyberte **knihovny DLL (aplikace pro UPW)**.

3.  Přidejte následující kód, který **RooterLib.h** souboru:

    ```cpp
    // The following ifdef block is the standard way of creating macros which make exporting
    // from a DLL simpler. All files within this DLL are compiled with the ROOTERLIB_EXPORTS
    // symbol defined on the command line. This symbol should not be defined on any project
    // that uses this DLL. This way any other project whose source files include this file see
    // ROOTERLIB_API functions as being imported from a DLL, whereas this DLL sees symbols
    // defined with this macro as being exported.
    #ifdef ROOTERLIB_EXPORTS
    #define ROOTERLIB_API  __declspec(dllexport)
    #else
    #define ROOTERLIB_API __declspec(dllimport)
    #endif //ROOTERLIB_EXPORTS

    class ROOTERLIB_API CRooterLib {
    public:
        CRooterLib(void);
        double SquareRoot(double v);
    };
    ```

     Komentáře vysvětlují bloku ifdef – pouze pro vývojáře knihovnu dll, ale všem uživatelům, kteří odkazuje na knihovnu DLL v jejich projektu. ROOTERLIB_EXPORTS symbol přidáte do příkazového řádku pomocí vlastností projektu knihovny DLL.

     `CRooterLib` Třída deklaruje konstruktor a `SqareRoot` odhadu metoda.

4.  ROOTERLIB_EXPORTS symbol přidejte na příkazový řádek.

    1.  V Průzkumníku řešení, vyberte **RooterLib** projektu a potom vyberte **vlastnosti** z místní nabídky.

         ![Přidejte definici – symbol preprocesoru](../test/media/ute_cpp_windows_addpreprocessorsymbol.png "UTE_Cpp_windows_AddPreprocessorSymbol")

    2.  V dialogovém okně Stránka vlastností RooterLib rozbalte **vlastnosti konfigurace**, rozbalte položku **C++** a zvolte **preprocesor**.

    3.  Zvolte  **\<Upravit … >** z **Definice preprocesoru** seznamu a poté přidejte `ROOTERLIB_EXPORTS` v dialogovém okně Definice preprocesoru.

5.  Přidáte minimální implementace deklarované funkcí. Otevřete **RooterLib.cpp** a přidejte následující kód:

    ```
    // constructor
    CRooterLib::CRooterLib()
    {
    }

    // Find the square root of a number.
    double CRooterLib::SquareRoot(double v)
    {
        return 0.0;
    }

    ```

##  <a name="make_the_dll_functions_visible_to_the_test_code"></a> Zpřístupněte funkce dll testovacího kódu

1.  Přidejte do projektu RooterLibTests RooterLib.

    1.  V Průzkumníku řešení, vyberte **RooterLibTests** projektu a potom zvolte **odkazy...**  v místní nabídce.

    2.  V dialogovém okně Vlastnosti projektu RooterLib rozbalte **společných vlastností** a zvolte **Framework a odkazy na**.

    3.  Zvolte **přidat nový odkaz...**

    4.  V **přidat odkaz na** dialogové okno, rozbalte seznam **řešení** a potom zvolte **projekty**. Vyberte **RouterLib** položky.

2.  Zahrnout soubor hlaviček RooterLib v **unittest1.cpp**.

    1.  Otevřete **unittest1.cpp**.

    2.  Tento kód vložte do níže `#include "CppUnitTest.h"` řádku:

        ```cpp
        #include "..\RooterLib\RooterLib.h"
        ```

3.  Přidáte test, který používá importované funkce. Přidejte následující kód, který **unittest1.cpp**:

    ```
    TEST_METHOD(BasicTest)
    {
        CRooterLib rooter;
        Assert::AreEqual(
            // Expected value:
            0.0,
            // Actual value:
            rooter.SquareRoot(0.0),
            // Tolerance:
            0.01,
            // Message:
            L"Basic test failed",
            // Line number - used if there is no PDB file:
            LINE_INFO());
    }

    ```

4.  Sestavte řešení.

     Nový test se zobrazí v Průzkumníku testování v **není spuštění testů** uzlu.

5.  V Průzkumníku testu zvolte **spustit všechny**.

     ![Základní Test proběhl](../test/media/ute_cpp_testexplorer_basictest.png "UTE_Cpp_TestExplorer_BasicTest")

 Máte nastavení testu a projektů kód a ověřit, že můžete spustit testy, které běží funkce v projektu kódu. Teď můžete začít zapisovat skutečné testy a kódu.

##  <a name="Iteratively_augment_the_tests_and_make_them_pass"></a> Opakované posílení testy a ujistěte se, je předat

1.  Přidejte nový test:

    ```cpp
    TEST_METHOD(RangeTest)
    {
        CRooterLib rooter;
        for (double v = 1e-6; v < 1e6; v = v * 3.2)
        {
            double expected = v;
            double actual = rooter.SquareRoot(v*v);
            double tolerance = expected/1000;
            Assert::AreEqual(expected, actual, tolerance);
        }
    };
    ```

    > [!TIP]
    > Doporučujeme neměnit testy, které uplynuly. Místo toho přidejte nový test, aktualizujte kód tak, aby test bude provedeno úspěšně a poté přidejte jiného testu, a tak dále.
    >
    > Pokud vaši uživatelé změnit jejich požadavky, zakažte testy, které již nejsou správné. Zápis nových testů a jejich fungování jeden po druhém, stejným způsobem jako přírůstkové.

2.  V Průzkumníku testu zvolte **spustit všechny**.

3.  Test se nezdaří.

     ![Selhání RangeTest](../test/media/ute_cpp_testexplorer_rangetest_fail.png "UTE_Cpp_TestExplorer_RangeTest_Fail")

    > [!TIP]
    > Ověřte, že každý test se nezdaří, ihned po jeho jste napsali. To umožňuje vyhnout se snadno chybu zápisu testu, který nikdy selže.

4.  Vylepšení testovaného kódu tak, aby nový test předá. Přidejte následující **RooterLib.cpp**:

    ```cpp
    #include <math.h>
    ...
    // Find the square root of a number.
    double CRooterLib::SquareRoot(double v)
    {
        double result = v;
        double diff = v;
        while (diff > result/1000)
        {
            double oldResult = result;
            result = result - (result*result - v)/(2*result);
            diff = abs (oldResult - result);
        }
        return result;
    }

    ```

5.  Sestavte řešení a potom vyberte v Průzkumníku Test **spustit všechny**.

     Oba testy byly úspěšné.

> [!TIP]
> Vývoj kódu přidáním testy jeden najednou. Ujistěte se, že všechny testy byly úspěšné po každé iteraci.


##  <a name="Debug_a_failing_test"></a> Ladění selhání testu

1.  Přidání jiného testu na **unittest1.cpp**:

    ```
    // Verify that negative inputs throw an exception.
     TEST_METHOD(NegativeRangeTest)
     {
       wchar_t message[200];
       CRooterLib rooter;
       for (double v = -0.1; v > -3.0; v = v - 0.5)
       {
         try
         {
           // Should raise an exception:
           double result = rooter.SquareRoot(v);

           swprintf_s(message, L"No exception for input %g", v);
           Assert::Fail(message, LINE_INFO());
         }
         catch (std::out_of_range ex)
         {
           continue; // Correct exception.
         }
         catch (...)
         {
           swprintf_s(message, L"Incorrect exception for %g", v);
           Assert::Fail(message, LINE_INFO());
         }
       }
    };

    ```

2.  V Průzkumníku testu zvolte **spustit všechny**.

     Test se nezdaří. Zvolte název testu v Průzkumníku otestovat. Je označený selhání kontrolního výrazu. Zpráva o neúspěšném zpracování je zobrazen v podokně podrobností Průzkumníka testů.

     ![NegativeRangeTests se nezdařilo](../test/media/ute_cpp_testexplorer_negativerangetest_fail.png "UTE_Cpp_TestExplorer_NegativeRangeTest_Fail")

3.  Chcete-li zjistit, proč test se nezdaří, kroku prostřednictvím funkce:

    1.  Nastavit zarážky na začátku `SquareRoot` funkce.

    2.  V místní nabídce selhání testu, zvolte **ladění vybrané testy**.

         Při spuštění, zastavení u zarážky, projděte kód.

    3.  Přidejte kód, který **RooterLib.cpp** k zachycení výjimky:

        ```
        #include <stdexcept>
        ...
        double CRooterLib::SquareRoot(double v)
        {
            //Validate the input parameter:
            if (v < 0.0)
            {
              throw std::out_of_range("Can't do square roots of negatives");
            }
        ...

        ```

    1.  V Průzkumníku otestovat, zvolte **spustit všechny** test opravené metody a ujistěte se, že nebyla zavedena regrese.

 Všechny testy byly úspěšné teď.

 ![Všechny testy byly úspěšné](../test/media/ute_ult_alltestspass.png "UTE_ULT_AllTestsPass")

##  <a name="Refactor_the_code_without_changing_tests"></a> Refaktorovat kód beze změny testů

1.  Zjednodušení centrální výpočtu v `SquareRoot` funkce:

    ```csharp
    // old code
    //result = result - (result*result - v)/(2*result);
    // new code
    result = (result + v/result) / 2.0;
    ```

2.  Zvolte **spustit všechny** test refactored metody a ujistěte se, že nebyla zavedena regrese.

    > [!TIP]
    > Stabilní sadu testů pro funkční jednotku poskytuje jistotu, že nebyla zavedena chyby při změně kódu.
    >
    > Zachovat refaktoring oddělené od dalších změn.
