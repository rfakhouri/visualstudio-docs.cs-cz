---
title: "Rychlé zahájení: Testování vývoj řízený testy pomocí Průzkumníka testů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 0dce2cfd041b3fe0be3ecd4061e3447190d5e448
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="quick-start-test-driven-development-with-test-explorer"></a>Rychlý začátek: Vývoj řízený testy s použitím Průzkumníka testů
Doporučujeme vytvořit testování částí zajistit, aby byl váš kód funguje prostřednictvím mnoho kroků přírůstkové vývoje. Existuje několik rozhraní, které můžete použít k zápisu testy jednotek, včetně některých vyvinuté třetími stranami. Některé testovací rozhraní se specializují na testování v různých jazycích nebo platformy. Průzkumníka testů poskytuje jednotné rozhraní pro testování částí v některém z těchto rozhraní. Jsou k dispozici pro rozhraní nejčastěji používaných adaptéry a můžete napsat vlastní adaptéry pro ostatní platformy.  
  
 Průzkumníka testů nahrazuje windows test jednotky najít v dřívějších vydání sady Visual Studio. Jeho výhody patří:  
  
-   Spuštění rozhraní .NET, nespravované, databáze a jinými druhy testů pomocí jediného rozhraní.  
  
-   Použití jednotka test framework podle vaší volby, jako je například NUnit nebo Mstestu architektury.  
  
-   Najdete v jednom okně veškeré informace, které potřebujete.  
  
## <a name="using-test-explorer"></a>Pomocí Průzkumníka testů  
 ![Tlačítko Spustit všechny zobrazuje Průzkumníka testů jednotek](../test/media/unittestexplorer-beta-.png "UnitTestExplorer(beta)")  
  
#### <a name="to-run-unit-tests-by-using-test-explorer"></a>Pro spuštění testů jednotek pomocí Průzkumníka testů  
  
1.  Vytvořte testy částí, využívající rozhraní test podle svého výběru.  
  
     Například vytvoření testu, který používá rozhraní Mstestu:  
  
    1.  Vytvoření projektu testů.  
  
         V **nový projekt** dialogové okno, rozbalte seznam **jazyka Visual Basic**, **Visual C#**, nebo **Visual C++**a potom zvolte **Test**.  
  
         Vyberte **projektu testování částí**.  
  
    2.  Každý test jednotky jako metody zápisu Předpony každá metoda test s `[TestMethod]` atribut.  
  
2.  Pokud jednotlivé testy žádné závislosti, které je zabránit spouštění v libovolném pořadí, zapnout spuštění testu paralelní s ![UTE &#95; parallelicon & č. 45; malá](../test/media/ute_parallelicon-small.png "UTE_parallelicon malá") přepínací tlačítko na panelu nástrojů. To může výrazně snížit čas potřebný k spustit všechny testy.  
  
3.  Na řádku nabídek zvolte **Test**, **spuštění testů jednotek**, **všechny testy**.  
  
     Sestavení řešení a spusťte testy.  
  
     Průzkumníka testů se zobrazí souhrn výsledků.  
  
 **Pokud chcete zobrazit úplný seznam testů:** zvolte **Zobrazit vše** žádné kategorie.  
  
 **Chcete-li zobrazit podrobnosti výsledků testů:** v Průzkumníku otestovat, chcete-li zobrazit podrobnosti, například zprávy o výjimkách v podokně podrobností vyberte test.  
  
 **Přejděte na kód testu:** klikněte dvakrát na test v Průzkumníku otestovat, nebo zvolte **otevřete testovací** v místní nabídce.  
  
 **Chcete-li ladit testu:** otevřete místní nabídku pro jeden nebo více testů a zvolte **ladění vybrané testy**.  
  
> [!IMPORTANT]
>  Výsledky, které se zobrazují pro nejnovější spouštějí. Panelu barevnou výsledků zobrazuje jenom výsledky testů, které byly spuštěny. Například pokud spustíte několik testů a některá z nich nezdaří a poté spusťte pouze ty testy úspěšné, pak na panelu výsledků se zobrazí všechny zelená.  
  
> [!NOTE]
>  Pokud žádné testů se zobrazí, ujistěte se, nainstalovaný adaptér pro připojení k rozhraní test, který používáte testovací Explorer. Další informace najdete v tématu [pomocí různých systémů testů pomocí Průzkumníka testů](#frameworks).  
  
##  <a name="walkthrough"></a>Návod: Použití testování částí pro vývoj – metoda  
 Tento návod ukazuje, jak vyvíjet otestované metoda v C# s použitím rozhraní testování částí Microsoft. Můžete snadno upravit ho pro jiné jazyky a použití jiných systémů testování například NUnit. Další informace najdete v tématu [pomocí různých systémů testování](#frameworks).  
  
#### <a name="creating-the-test-and-method"></a>Vytváření testovacích a – metoda  
  
1.  Vytvoření projektu knihovny tříd Visual C#. Tento projekt bude obsahovat kód, který chcete poskytovat. V tomto příkladu je pojmenována `MyMath`.  
  
2.  Vytvoření projektu testů.  
  
    -   V **nový projekt** dialogovém okně, vyberte **Visual C#**, **Test** a potom zvolte **projektu testování částí**.  
  
         ![Nové projekty kódu a testování](../test/media/unittestexplorerwalk1.png "UnitTestExplorerWalk1")  
  
3.  Write – metoda základní test. Ověřte výsledek pro specifický vstup:  
  
    ```csharp  
  
    [TestMethod]  
    public void BasicRooterTest()  
    {  
      // Create an instance to test:  
      Rooter rooter = new Rooter();  
      // Define a test input and output value:  
      double expectedResult = 2.0;  
      double input = expectedResult * expectedResult;  
      // Run the method under test:  
      double actualResult = rooter.SquareRoot(input);  
      // Verify the result:  
      Assert.AreEqual(expectedResult, actualResult,  
          delta: expectedResult / 100);  
    }  
    ```  
  
4.  Vygenerujte metodu z testu.  
  
    1.  Umístěte kurzor na `Rooter`a potom v místní nabídce vyberte **generování**, **nový typ**.  
  
    2.  V **vygenerovat nový typ** dialogové okno, sada **projektu** do projektu knihovny tříd. V tomto příkladu je `MyMath`.  
  
    3.  Umístěte kurzor na `SquareRoot`a potom v místní nabídce vyberte **generování**, **se zakázaným inzerováním metoda**.  
  
5.  Spuštění testování částí.  
  
    1.  Na **Test** nabídce zvolte **spuštění testů jednotek**, **všechny testy**.  
  
         Řešení vytvoří a spustí.  
  
         Průzkumníka testů se zobrazí výsledky.  
  
         Test se zobrazí pod **se nezdařilo testy**.  
  
6.  Vyberte název testu.  
  
     V dolní části Průzkumníka testů zobrazují podrobnosti, které testu.  
  
7.  Vyberte položky v rámci **trasování zásobníku** zobrazíte, kde test se nezdařil.  
  
 ![Testování jednotky testování Explorer zobrazující se nezdařilo. ] (../test/media/unittestexplorerwalkthrough2.png "UnitTestExplorerWalkthrough2")  
  
 V tomto okamžiku jste vytvořili testovací a kódu, který upravíte tak, aby test byl úspěšný.  
  
#### <a name="after-every-change-make-all-the-tests-pass"></a>Po každé změně zkontrolujte všechny testy předat  
  
1.  V `MyMath\Rooter.cs`, zlepšení kódu `SquareRoot`:  
  
    ```csharp  
    public double SquareRoot(double input)  
     {  
       return input / 2;  
     }  
    ```  
  
2.  V Průzkumníku testu zvolte **spustit všechny**.  
  
     Kód vytvoří a spustí test.  
  
     Test byl úspěšný.  
  
     ![Průzkumník testování částí zobrazující testu předávání. ] (../test/media/unittestexplorerwalkthrough3.png "UnitTestExplorerWalkthrough3")  
  
#### <a name="add-tests-to-extend-the-range-of-inputs"></a>Přidávat testy rozšířit rozsah vstupy  
  
1.  Chcete-li zvýšit vaši důvěry, že váš kód funguje ve všech případech, přidejte testy, které se pokusí mnohem širší škále vstupních hodnot.  
  
    > [!TIP]
    >  Vyhněte se změna existující testy, které předat. Místo toho přidejte nové testy. Změníte existující testy jenom v případě, že požadavky na uživatele změnit. Tato zásada pomáhá zajistit, aby neztratili stávající funkce při práci rozšířit kód.  
  
     Ve třídě testovací přidáte následující test, který pokusí řadu vstupní hodnoty:  
  
    ```csharp  
    [TestMethod]  
    public void RooterValueRange()  
    {  
      // Create an instance to test:  
      Rooter rooter = new Rooter();  
      // Try a range of values:  
      for (double expectedResult = 1e-8;  
          expectedResult < 1e+8;  
          expectedResult = expectedResult * 3.2)  
      {  
        RooterOneValue(rooter, expectedResult);  
      }  
    }  
  
    private void RooterOneValue(Rooter rooter, double expectedResult)  
    {  
      double input = expectedResult * expectedResult;  
      double actualResult = rooter.SquareRoot(input);  
      Assert.AreEqual(expectedResult, actualResult,  
          delta: expectedResult / 1000);  
    }  
    ```  
  
2.  V Průzkumníku testu zvolte **spustit všechny**.  
  
     Nový test se nezdaří, i když stále předá prvního testu.  
  
     Najít bodem selhání, vyberte selhání testu a pak v dolní části testování Explorer, vyberte horní položku z **trasování zásobníku**.  
  
3.  Zkontrolujte metodu pod test ke zjištění toho, co mohou být další potíže. V `MyMath.Rooter` třídy, přepište kód:  
  
    ```  
    public double SquareRoot(double input)  
    {  
      double result = input;  
      double previousResult = -input;  
      while (Math.Abs(previousResult - result) > result / 1000)  
      {  
        previousResult = result;  
        result = result - (result * result - input) / (2 * result);  
      }  
      return result;  
    }  
    ```  
  
4.  V Průzkumníku testu zvolte **spustit všechny**.  
  
     Oba testy teď předat.  
  
#### <a name="add-tests-for-exceptional-cases"></a>Přidání testů pro výjimečných případů  
  
1.  Přidejte testu pro vstupní záporné hodnoty:  
  
    ```csharp  
    [TestMethod]  
     public void RooterTestNegativeInputx()  
     {  
         Rooter rooter = new Rooter();  
         try  
         {  
             rooter.SquareRoot(-10);  
         }  
         catch (ArgumentOutOfRangeException e)  
         {  
             return;  
         }  
         Assert.Fail();  
     }  
    ```  
  
2.  V Průzkumníku testu zvolte **spustit všechny**.  
  
     Metoda pod testování smyčky a musí být zrušeno ručně.  
  
3.  Zvolte **zrušit**.  
  
     Test zastaví po 10 sekundách.  
  
4.  Odstranit kód metody:  
  
    ```csharp  
  
    public double SquareRoot(double input)  
    {  
      if (input <= 0.0)   
      {  
        throw new ArgumentOutOfRangeException();  
      }   
    ...  
    ```  
  
5.  V Průzkumníku testu zvolte **spustit všechny**.  
  
     Všechny testy byly úspěšné.  
  
#### <a name="refactor-without-changing-tests"></a>Refaktorovat beze změny testů  
  
1.  Zjednodušit kód, ale neměňte testy.  
  
    > [!TIP]
    >  A *refaktoring* je změna, která je určená kód poskytují lepší výkon a snadněji pochopili kód. Rozhraní není určeno ke změně chování kód, a proto nebudou změněna testy.  
    >   
    >  Doporučujeme provést refaktoringu kroky samostatně z kroků, které rozšiřují funkce. Zachování testy beze změny získáte jistotu, že nebyla zavedena omylem chyby při refaktoring.  
  
    ```csharp  
    public class Rooter  
    {  
      public double SquareRoot(double input)  
      {  
        if (input <= 0.0)   
        {  
          throw new ArgumentOutOfRangeException();  
        }  
        double result = input;  
        double previousResult = -input;  
        while (Math.Abs(previousResult - result) > result / 1000)  
        {  
          previousResult = result;  
          result = (result + input / result) / 2;  
          //was: result = result - (result * result - input) / (2*result);  
        }  
        return result;  
      }  
    }  
    ```  
  
2.  Zvolte **spustit všechny**.  
  
     Všechny testy byly stále úspěšné.  
  
     ![Zobrazuje 3 předaný testy Průzkumníka testů jednotek. ] (../test/media/unittestexplorerwalkthrough4.png "UnitTestExplorerWalkthrough4")
