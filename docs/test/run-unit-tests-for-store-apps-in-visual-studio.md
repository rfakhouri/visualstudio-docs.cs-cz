---
title: "Spouštění testů jednotek pro aplikace UWP v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: uwp
author: gewarren
ms.openlocfilehash: c9610360c0ea6d32c4825b1e2768f3eaaa06a6fa
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="run-unit-tests-for-uwp-apps-in-visual-studio"></a>Spouštění testů jednotek pro aplikace UWP v sadě Visual Studio
Toto téma popisuje postup spouštění testů jednotek pomocí Průzkumníka testů v sadě Microsoft Visual Studio  
  
> [!NOTE]
>  Témata v této části popisují funkci Visual Studio Express pro Windows 8. Visual Studio Community, Enterprise a Professional poskytnutí dodatečných funkcí pro testování jednotky.  
>   
>  -   Použijte libovolnou architekturu test jednotky třetích stran nebo otevřený zdroj vytvořený adaptér rozšíření pro Microsoft testování Explorer. Můžete také analyzovat a zobrazit informace o pokrytí kódu pro testy.  
> -   Spouštění testů po každé sestavení. Můžete také použít Microsoft Fakes, představuje izolace rozhraní pro spravovaný kód a testy zaměřit se na vlastní kód nahrazením testovacího kódu pro systém a funkce třetích stran.  
>   
>  Další informace najdete v tématu [si kód Test jednotky](../test/unit-test-your-code.md) v knihovně MSDN.  
  
##  <a name="BKMK_In_this_topic"></a>V tomto tématu  
 [Systémů testování částí a projektů testů](#BKMK_Unit_test_frameworks_and_test_projects)  
  
 [Spouštění testů v Průzkumníka testů](#BKMK_Running_tests_in_Test_Explorer)  
  
-   [Spouštění testů](#BKMK_Running_tests)  
  
 [Zobrazení výsledků testu](#BKMK_Viewing_test_results)  
  
-   [Podrobnosti testovacího zobrazení](#BKMK_Viewing_test_details)  
  
-   [Zobrazení zdrojového kódu metody testu](#BKMK_Viewing_the_source_code_of_a_test_method)  
  
 [Uspořádání seznamu testů](#BKMK_Organizing_the_test_list)  
  
-   [Seskupení testů](#BKMK_Grouping_tests)  
  
-   [Vyhledávání a filtrování seznamu testů](#BKMK_Searching_and_filtering_the_test_list)  
  
 [Ladění testování částí](#BKMK_Debugging_unit_tests)  
  
##  <a name="BKMK_Unit_test_frameworks_and_test_projects"></a>Systémů testování částí a projektů testů  
 Rozhraní testování částí Microsoft Visual Studio Express pro aplikace UWP zahrnuje, pro spravované a pro nativní kód C++. Testy můžete spustit Průzkumníka testů z více testovací projekty v řešení a testovací třídy, které jsou součástí projekty kód produkční. Projektů testování může být libovolnou kombinací Visual c++ nebo Visual C# a Visual Basic jednotkové testování architektury. Pokud testovaného kódu je napsán pro rozhraní .NET Framework, může být napsán k testovacímu projektu v libovolném jazyce rozhraní .NET Framework, bez ohledu na jazyk kódu cíl. Nativní kód projekty C/C++ musí být testována pomocí rozhraní test jednotky C++.  
  
##  <a name="BKMK_Running_tests_in_Test_Explorer"></a>Spouštění testů v Průzkumníka testů  
 Při sestavování testovacího projektu testů se zobrazí v Průzkumníku otestovat. Pokud není viditelná Průzkumníka testů, zvolte **Test** v sadě Visual Studio nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.  
  
 ![Průzkumníka testů jednotek](../test/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")  
  
 Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v výchozí skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a  **Nejde spustit testy**. Můžete změnit způsob Průzkumníka testů skupiny testů.  
  
 Můžete provádět většinu práce hledání, uspořádání a spouštění testů z panelu nástrojů Průzkumníka testů.  
  
 ![Spouštění testů z panelu nástrojů Průzkumníka testů](../test/media/ute_toolbar.png "UTE_ToolBar")  
  
###  <a name="BKMK_Running_tests"></a>Spouštění testů  
 Můžete spustit všechny testy v řešení, všechny testy ve skupině nebo sadu testů, které jste vybrali. Proveďte jednu z těchto akcí:  
  
-   Pokud chcete spustit všechny testy v řešení, zvolte **spustit všechny**.  
  
-   Pokud chcete spustit všechny testy ve výchozí skupině, vyberte **spustit...**  a pak zvolte skupinu v nabídce.  
  
-   Vyberte jednotlivé testy, které chcete spustit, otevřete místní nabídku pro vybrané testu a pak zvolte **spustit vybrané testy**.  
  
 Na panelu průchodu nebo selže v horní části okna Průzkumníka testů je animované jako Spusťte testy. Při ukončení spustit test změní zelená panelu průchodu nebo selhání, pokud všechny testy byly splněny, nebo červenou, pokud žádné test se nezdařil.  
  
##  <a name="BKMK_Viewing_test_results"></a>Zobrazení výsledků testu  
 Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a **nejde spustit Testy**. V podokně podrobností v dolní části testování Explorer zobrazí spustit souhrn testu.  
  
###  <a name="BKMK_Viewing_test_details"></a>Podrobnosti testovacího zobrazení  
 Chcete-li zobrazit podrobnosti o jednotlivé testy, vyberte test.  
  
 V podokně podrobností testovací zobrazí následující informace:  
  
-   Název zdrojového souboru a číslo řádku zkušební metody.  
  
-   Stav testu.  
  
-   Uplynulý čas, který trvalo spuštění metody testu.  
  
 Pokud se test nezdaří, zobrazí se také v podokně podrobností:  
  
-   Zpráva, která vrácený částí unit test framework pro test.  
  
-   Trasování zásobníku v době testu se nezdařila.  
  
###  <a name="BKMK_Viewing_the_source_code_of_a_test_method"></a>Zobrazení zdrojového kódu metody testu  
 Chcete-li zobrazit zdrojový kód pro zkušební metody v editoru Visual Studio, vyberte test a poté zvolte **otevřete testovací** v místní nabídce (klávesové: F12).  
  
##  <a name="BKMK_Organizing_the_test_list"></a>Uspořádání seznamu testů  
  
###  <a name="BKMK_Grouping_tests"></a>Seskupení testů  
 Ve výchozím nastavení, zobrazí Průzkumníka testů testy jako uzly podřízené **se nezdařilo testy**, **předán testy**, **přeskočen testy** a **není spuštění testů**.  
  
|||  
|-|-|  
|![Tlačítko Testovat Explorer skupiny](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn")|Pro seskupení testů podle doby potřebné k jejich provedení, otevřete **Group By** seznam a vyberte **doba trvání**. Zvolte **výsledek testu** přepnout na původní seskupení.|  
  
###  <a name="BKMK_Searching_and_filtering_the_test_list"></a>Vyhledávání a filtrování seznamu testů  
 Když máte velký počet testů, můžete zadat do pole Hledat Průzkumníka testů pro filtrování seznamu podle zadaného řetězce. Filtr můžete omezit na konkrétní typy řetězců výběrem ze seznamu filtru před zadejte hledaný řetězec.  
  
 ![Prohledat kategorie filtru](../test/media/ute_searchfilter.png "UTE_SearchFilter")  
  
##  <a name="BKMK_Debugging_unit_tests"></a>Ladění testování částí  
 Průzkumníka testů můžete spustit relaci ladění testů. Procházení kódu s ladicím programu sady Visual Studio bezproblémově přejdete oběma směry mezi testy částí a projekt v rámci testu. Spustit ladění:  
  
1.  V editoru Visual Studio nastavte zarážky v jedné nebo několika metod testovací, které chcete ladit.  
  
    > [!NOTE]
    >  Vzhledem k tomu, že testovací metody můžete spustit v libovolném pořadí, nastavte zarážky v všechny testovací metody, které chcete ladit.  
  
2.  V Průzkumníku testování vybrat metody testu a pak zvolte **ladění vybrané testy** v místní nabídce.  
  
 Další informace o ladicího programu, najdete v části [ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md).
