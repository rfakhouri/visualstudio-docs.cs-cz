---
title: "Postupy: zápis testů částí pro knihovny DLL C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
author: mikeblome
ms.openlocfilehash: 0e3852687b837c99bf92b73a65be9a5d139bc0cc
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="how-to-write-unit-tests-for-c-dlls"></a>Postupy: zápis testů částí pro C++ – knihovny DLL
Tento návod popisuje, jak vyvíjet nativní knihovny DLL C++ pomocí metody včasného testování. Základní kroky jsou následující:  
  
1.  [Vytvoření projektu testování nativní](#create_test_project). K testovacímu projektu nachází ve stejném řešení jako projektu knihovny DLL.  
  
2.  [Vytvoření projektu knihovny DLL](#create_dll_project). Tento návod vytvoří nová knihovna DLL, ale je podobný postup testování existující knihovnu DLL.  
  
3.  [Zviditelnit funkcí knihovny DLL pro testy](#make_functions_visible).  
  
4.  [Opakované posílení testy](#iterate). Doporučujeme, abyste cyklus "red refactor zelená", ve kterém vývoj kódu zobrazí Průvodce testy.  
  
5.  [Ladění selhání testy](#debug). Testy můžete spustit v režimu ladění.  
  
6.  [Refaktorovat při zachování testy beze změny](#refactor). Refaktoring znamená zlepšení strukturu kód beze změny jeho externí chování. Můžete to provést pro zlepšení výkonu, rozšiřitelnost nebo čitelnost kód. Protože záměrem je nechcete změnit chování, se nezmění testy při vytváření kódu refaktoringu změnu. Testy pomoci, ujistěte se, že nepoužijete chyby při jsou refaktoring.
  
7.  [Zkontrolujte pokrytí](using-code-coverage-to-determine-how-much-code-is-being-tested.md). Testy jednotek je více užitečný v případě využijí informace z vašeho kódu. Je-li zjistit, jaké části kódu použil testy.  
  
8.  [Izolovat jednotky z externích zdrojů](using-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing.md). Obvykle je závislé na dalších komponentách systému, který vyvíjíte, například jiné knihovny DLL, databáze nebo vzdálené subsystémy knihovny DLL. Je užitečné pro testování jednotlivých jednotek izolovaně od jeho závislé součásti. Externí součásti provádět testy pracovat pomalu. Během vývoje ostatní součásti nemusí být kompletní.  
  
##  <a name="create_test_project"></a>Vytvoření projektu testování částí nativní  
  
1.  Na **soubor** nabídce zvolte **nový | Projekt**.  
  
     V dialogovém okně rozbalte **nainstalovaná | Šablony | Visual C++ | Test**.  
  
     Vyberte **nativní projektu testování částí** šablony, nebo ať nainstalovat vámi preferované rozhraní. Pokud zvolíte jinou šablonu, jako je například Google testu nebo Boost.Test, základní principy jsou stejné, i když některé podrobnosti se budou lišit.
  
     V tomto návodu k testovacímu projektu jmenuje `NativeRooterTest`.  
  
     ![Vytvoření projektu testování částí C++](../test/media/utecpp01.png "UteCpp01")  
  
2.  V novém projektu, zkontrolujte **unittest1.cpp**  
  
     ![Testování projektu s testovací &#95; Třída a testovací &#95; Metoda](../test/media/utecpp2.png "UteCpp2")  
  
     Všimněte si, že:  
  
    -   Každý test se definuje pomocí `TEST_METHOD(YourTestName){...}`.  
  
         Nemáte k zápisu podpis běžné funkce. Makro TEST_METHOD vytvoří podpis. Makro generuje instance funkce, který vrátí prázdnou hodnotu. Také vytváří statickou funkci, která vrací informace o metodě testu. Tyto informace umožňuje Průzkumníka testů najít metodu.  
  
    -   Test metody jsou seskupené do třídy pomocí `TEST_CLASS(YourClassName){...}`.  
  
         Když se testy spouštějí, se vytvoří instance třídy každého testu. Test metody jsou volány v neurčené pořadí. Můžete definovat speciální metody, které jsou vyvolány před a po každém modulu, třída nebo metoda.  
  
3.  Ověřte, zda testy spustit v Průzkumníka testů:  
  
    1.  Vložte některá testovacího kódu:  
  
        ```cpp  
        TEST_METHOD(TestMethod1)  
        {  
            Assert::AreEqual(1,1);  
        }  
        ```  
  
         Všimněte si, že `Assert` třída poskytuje několik statických metod, které můžete ověřit výsledky v testovací metody.  
  
    2.  Na **Test** nabídce zvolte **spustit | Všechny testy**.  
  
         Test vytvoří a spustí.  
  
         Zobrazí se Průzkumníka testů.  
  
         Test se zobrazí pod **předán testy**.  
  
         ![Jednotka testování Explorer se jeden předaný test](../test/media/utecpp04.png "UteCpp04")  
  
##  <a name="create_dll_project"></a>Vytvoření projektu knihovny DLL  
  
1.  Vytvoření **Visual C++** projektu pomocí **projektu Win32** šablony.  
  
     V tomto návodu je projekt s názvem `RootFinder`.  
  
     ![Vytvoření projektu C++ Win32](../test/media/utecpp05.png "UteCpp05")  
  
2.  Vyberte **DLL** a **exportovat symboly** v Průvodci aplikace Win32.  
  
     **Exportovat symboly** možnost generuje pohodlný makro, které můžete použít k deklaraci exportovaný metody.  
  
     ![C++ – Průvodce projektem nastavení pro knihovnu DLL a exportovat symboly](../test/media/utecpp06.png "UteCpp06")  
  
3.  Deklarujte exportované funkce v souboru hlavní h:  
  
     ![Nový kód projektu a .h souboru DLL pomocí rozhraní API makra](../test/media/utecpp07.png "UteCpp07")  
  
     Deklarátor `__declspec(dllexport)` způsobí, že veřejné a chráněné členy třídy viditelné mimo knihovnu DLL. Další informace najdete v tématu [používání příkazů dllimport a dllexport ve třídách jazyka C++](/cpp/cpp/using-dllimport-and-dllexport-in-cpp-classes).  
  
4.  V souboru hlavní sada přidejte minimální textu, funkce:  
  
    ```cpp  
        // Find the square root of a number.  
        double CRootFinder::SquareRoot(double v)  
        {  
            return 0.0;  
        }  
    ```  
  
##  <a name="make_functions_visible"></a>Několik k testovacímu projektu do projektu knihovny DLL  
  
1.  Přidejte projektu knihovny DLL do odkazů projektu testovacího projektu:  
  
    1.  Otevřete vlastnosti k testovacímu projektu a zvolte **společných vlastností**, **Framework a odkazy na**.  
  
         ![Vlastnosti projektu C++ | Architektura a odkazy na](../test/media/utecpp08.png "UteCpp08")  
  
    2.  Zvolte **přidat nový odkaz**.  
  
         V **přidat odkaz na** dialogovém okně vyberte projektu knihovny DLL a zvolte **přidat**.  
  
         ![Vlastnosti projektu C++ | Přidat nový odkaz](../test/media/utecpp09.png "UteCpp09")  
  
2.  V souboru hlavní jednotky testovací sada zahrňte soubor hlaviček kód knihovny DLL:  
  
    ```cpp  
    #include "..\RootFinder\RootFinder.h"  
    ```  
  
3.  Přidáte základní test, který používá exportované funkce:  
  
    ```cpp  
    TEST_METHOD(BasicTest)  
    {  
       CRootFinder rooter;  
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
  
     V Průzkumníku testů se zobrazí nový test.  
  
5.  V Průzkumníku testu zvolte **spustit všechny**.  
  
     ![Průzkumníka testů jednotek & č. 45; Základní Test proběhl](../test/media/utecpp10.png "UteCpp10")  
  
 Máte nastavení testu a projektů kód a ověřit, že můžete spustit testy, které běží funkce v projektu kódu. Teď můžete začít zapisovat skutečné testy a kódu.  
  
##  <a name="iterate"></a>Opakované posílení testy a ujistěte se, je předat  
  
1.  Přidejte nový test:  
  
    ```cpp  
    TEST_METHOD(RangeTest)  
    {  
      CRootFinder rooter;  
      for (double v = 1e-6; v < 1e6; v = v * 3.2)  
      {  
        double actual = rooter.SquareRoot(v*v);  
        Assert::AreEqual(v, actual, v/1000);  
      }  
    }  
    ```  
  
    > [!TIP]
    >  Doporučujeme neměnit testy, které uplynuly. Místo toho přidejte nový test, aktualizujte kód tak, aby test bude provedeno úspěšně a poté přidejte jiného testu, a tak dále.  
    >   
    >  Pokud vaši uživatelé změnit jejich požadavky, zakažte testy, které již nejsou správné. Zápis nových testů a jejich fungování jeden po druhém, stejným způsobem jako přírůstkové.  
  
2.  Sestavte řešení a potom vyberte v Průzkumníku Test **spustit všechny**.  
  
     Nový test se nezdaří.  
  
     ![Selhání RangeTest](../test/media/ute_cpp_testexplorer_rangetest_fail.png "UTE_Cpp_TestExplorer_RangeTest_Fail")  
  
    > [!TIP]
    >  Ověřte, že každý test se nezdaří, ihned po jeho jste napsali. To umožňuje vyhnout se snadno chybu zápisu testu, který nikdy selže.  
  
3.  Vylepšení kódu knihovnu DLL tak, aby nový test předá:  
  
    ```cpp  
    #include <math.h>  
    ...  
    double CRootFinder::SquareRoot(double v)  
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
  
4.  Sestavte řešení a potom vyberte v Průzkumníku Test **spustit všechny**.  
  
     Oba testy byly úspěšné.  
  
     ![Průzkumníka testů jednotek & č. 45; Rozsah Test proběhl](../test/media/utecpp12.png "UteCpp12")  
  
    > [!TIP]
    >  Vývoj kódu přidáním testy jeden najednou. Ujistěte se, že všechny testy byly úspěšné po každé iteraci.  
  
##  <a name="debug"></a>Ladění selhání testu  
  
1.  Přidání jiného testu:  
  
    ```cpp    
    #include <stdexcept>  
    ...  
    // Verify that negative inputs throw an exception.  
    TEST_METHOD(NegativeRangeTest)  
    {  
      wchar_t message[200];  
      CRootFinder rooter;  
      for (double v = -0.1; v > -3.0; v = v - 0.5)  
      {  
        try   
        {  
          // Should raise an exception:  
          double result = rooter.SquareRoot(v);  
  
          _swprintf(message, L"No exception for input %g", v);  
          Assert::Fail(message, LINE_INFO());  
        }  
        catch (std::out_of_range ex)  
        {  
          continue; // Correct exception.  
        }  
        catch (...)  
        {  
          _swprintf(message, L"Incorrect exception for %g", v);  
          Assert::Fail(message, LINE_INFO());  
        }  
      }  
    }  
    ```  
  
2.  Sestavte řešení a zvolte **spustit všechny**.  
  
3.  Otevřete (nebo dvakrát kliknout na) neúspěšných testů.  
  
     Je označený selhání kontrolního výrazu. Zpráva o neúspěšném zpracování je zobrazen v podokně podrobností Průzkumníka testů.  
  
     ![NegativeRangeTests se nezdařilo](../test/media/ute_cpp_testexplorer_negativerangetest_fail.png "UTE_Cpp_TestExplorer_NegativeRangeTest_Fail")  
  
4.  Chcete-li zjistit, proč test se nezdaří, kroku prostřednictvím funkce:  
  
    1.  Na začátku funkce SquareRoot nastavte zarážky.  
  
    2.  V místní nabídce selhání testu, zvolte **ladění vybrané testy**.  
  
         Při spuštění, zastavení u zarážky, projděte kód.  
  
5.  Vložení kódu ve funkci při vývoji:  
  
    ```cpp  
  
    #include <stdexcept>  
    ...  
    double CRootFinder::SquareRoot(double v)  
    {  
        // Validate parameter:  
        if (v < 0.0)   
        {  
          throw std::out_of_range("Can't do square roots of negatives");  
        }  
  
    ```  
  
6.  Všechny testy byly úspěšné teď.  
  
     ![Všechny testy byly úspěšné](../test/media/ute_ult_alltestspass.png "UTE_ULT_AllTestsPass")  
  
> [!TIP]
>  Pokud jednotlivé testy žádné závislosti, které je zabránit spouštění v libovolném pořadí, zapnout spuštění testu paralelní s ![UTE &#95; parallelicon & č. 45; malá](../test/media/ute_parallelicon-small.png "UTE_parallelicon malá") přepínací tlačítko na panelu nástrojů. To může výrazně snížit čas potřebný k spustit všechny testy.  
  
##  <a name="refactor"></a>Refaktorovat kód beze změny testů  
  
1.  Zjednodušení centrální výpočtu ve funkci SquareRoot:  
  
    ```  
    // old code:  
    //   result = result - (result*result - v)/(2*result);  
    // new code:  
         result = (result + v/result)/2.0;  
  
    ```  
  
2.  Sestavte řešení a zvolte **spustit všechny**, abyste měli jistotu, že nebyla zavedena k chybě.  
  
    > [!TIP]
    >  Dobrý sadu testů jednotek poskytuje jistotu, že nebyla zavedena chyby při změně kódu.  
    >   
    >  Zachovat refaktoring oddělené od dalších změn.  
  
## <a name="next-steps"></a>Další kroky  
  
-   **Izolace.** Většina knihovny DLL jsou závislá na jiných subsystémy, jako jsou databáze a další knihovny DLL. Tyto součásti jsou často vyvinuté paralelně. Pokud chcete povolit, zatímco ostatní součásti dosud nejsou k dispozici testování částí, budete muset nahraďte mock nebo  
  
-   **Sestavení testech pro ověření.** Můžete mít testy na váš tým sestavení serveru ve stanovených intervalech. Tím se zajistí, že nejsou chyby vniklých při práci při několik členů týmu je integrovaný.  
  
-   **Testy vrácení se změnami.** Můžete vyžádá, aby některé testy byly provedeny před každý člen týmu kontroluje kód do správy zdrojového kódu. To je obvykle podmnožinu kompletní sadu testů pro ověření sestavení.  
  
     Můžete také vyžádá minimální úroveň pokrytí kódu.  
  
## <a name="see-also"></a>Viz také  
 [Přidání testů částí do stávajících aplikací C++](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)   
 [Používání atributu Microsoft.VisualStudio.TestTools.CppUnitTestFramework](../test/using-microsoft-visualstudio-testtools-cppunittestframework.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Návod: Vytvoření a použití dynamické knihovny (C++)](/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp)   
 [Import a export](/cpp/build/importing-and-exporting)
