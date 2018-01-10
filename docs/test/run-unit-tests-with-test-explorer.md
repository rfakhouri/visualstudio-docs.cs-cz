---
title: "Spouštění testů jednotek pomocí Průzkumníka testů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.unittesting.testexplorer.overview
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: e25d450eee8b404819df152a759d7238363d1a78
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="run-unit-tests-with-test-explorer"></a>Spouštění testů jednotek pomocí Průzkumníka testů
Pomocí Průzkumníka testů spouštění testování částí v sadě Visual Studio nebo projektů testování částí třetích stran, seskupení testů do kategorií, filtrování seznamu testů a vytvořit, uložit a spustit seznamy stop testů. Můžete také ladění testy a analyzovat pokrytí test výkonu a kód.  
  
##  <a name="BKMK_Contents"></a>Obsah  
 [Systémů testování částí a projektů testů](#BKMK_Unit_test_frameworks_and_test_projects)  
  
 [Spuštění testů Průzkumníka testů](#BKMK_Run_tests_in_Test_Explorer)  
  
 [Zobrazení výsledků testu](#BKMK_View_test_results)  
  
 [Skupiny a filtrování seznamu testů](#BKMK_Group_and_filter_the_test_list)  
  
 [Vytvořit vlastní seznamy stop](#BKMK_Create_custom_playlists)  
  
 [Ladění a analýze testování částí](#BKMK_Debug_and_analyze_unit_tests)  
  
 [Externí zdroje](#BKMK_External_resources)  
  
##  <a name="BKMK_Unit_test_frameworks_and_test_projects"></a>Systémů testování částí a projektů testů  
 Visual Studio obsahuje rozhraní testování částí Microsoft pro spravovaná a nativní kód. Však Průzkumníka testů můžete také spouštět žádné jednotky test rozhraní, které implementovala testování Explorer adaptéru. Další informace týkající se instalace systémů testů jednotek třetích stran najdete v tématu [instalace systémů testů jednotek třetích stran](../test/install-third-party-unit-test-frameworks.md)  
  
 Testy můžete spustit Průzkumníka testů z více testovací projekty v řešení a testovací třídy, které jsou součástí projekty kód produkční. Projektů testů můžete použít rozhraní test jinou jednotku. Pokud testovaného kódu je napsán pro rozhraní .NET Framework, může být napsán k testovacímu projektu v libovolném jazyce, který také cílí na rozhraní .NET Framework, bez ohledu na jazyk kódu cíl. Nativní kód projekty C/C++ musí být testována pomocí rozhraní test jednotky C++. Další informace najdete v tématu [zápis testování částí pro C/C++](writing-unit-tests-for-c-cpp.md).
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Run_tests_in_Test_Explorer"></a>Spuštění testů Průzkumníka testů  
 [Spouštění testů](#BKMK_Run_tests) **&#124;** [Spuštění testů po každé sestavení](#BKMK_Run_tests_after_every_build)  
  
 Při sestavování testovacího projektu testů se zobrazí v Průzkumníku otestovat. Pokud není viditelná Průzkumníka testů, zvolte **Test** v sadě Visual Studio nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.  
  
 ![Průzkumníka testů jednotek](../ide/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")  
  
 Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v výchozí skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a  **Nejde spustit testy**. Můžete změnit způsob Průzkumníka testů skupiny testů.  
  
 Můžete provádět většinu práce hledání, uspořádání a spouštění testů z panelu nástrojů Průzkumníka testů.  
  
 ![Spouštění testů z panelu nástrojů Průzkumníka testů](../test/media/ute_toolbar.png "UTE_ToolBar")  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_Run_tests"></a>Spouštění testů  
 Můžete spustit všechny testy v řešení, všechny testy ve skupině nebo sadu testů, které jste vybrali. Proveďte jednu z těchto akcí:  
  
-   Pokud chcete spustit všechny testy v řešení, zvolte **spustit všechny**.  
  
-   Pokud chcete spustit všechny testy ve výchozí skupině, vyberte **spustit...**  a pak zvolte skupinu v nabídce.  
  
-   Vyberte jednotlivé testy, které chcete spustit, otevřete v místní nabídce pro vybrané test a zvolte **spustit vybrané testy**.  
  
-   Pokud jednotlivé testy žádné závislosti, které je zabránit spouštění v libovolném pořadí, zapnout spuštění testu paralelní s ![UTE &#95; parallelicon & č. 45; malá](../test/media/ute_parallelicon-small.png "UTE_parallelicon malá") přepínací tlačítko na panelu nástrojů. To může výrazně snížit čas potřebný k spustit všechny testy.  
  
 Na panelu průchodu nebo selže v horní části okna Průzkumníka testů je animované jako Spusťte testy. Při ukončení spustit test změní zelená panelu průchodu nebo selhání, pokud všechny testy byly splněny, nebo červenou, pokud žádné test se nezdařil.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_Run_tests_after_every_build"></a>Spouštění testů po každé sestavení  
  
> [!WARNING]
>  Po každé sestavení je podporováno v aplikaci Visual Studio Enterprise testů spuštěné jednotek.  
  
|||  
|-|-|  
|![Po sestavení spustit](../test/media/ute_runafterbuild_btn.png "UTE_RunAfterBuild_btn")|Spouštění testů jednotek po každé místní sestavení, zvolte **Test** v nabídce standardní a potom zvolte **spustit testy po sestavení** na panelu nástrojů Průzkumníka testů.|  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_View_test_results"></a>Zobrazení výsledků testu  
 [Zobrazení podrobností testovacího](#BKMK_View_test_details) **&#124;** [Zobrazit zdrojový kód metody testu](#BKMK_View_the_source_code_of_a_test_method)  
  
 Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a **nejde spustit Testy**. V podokně podrobností v dolní části testování Explorer zobrazí spustit souhrn testu.  
  
###  <a name="BKMK_View_test_details"></a>Zobrazit podrobnosti o testu  
 Chcete-li zobrazit podrobnosti o jednotlivé testy, vyberte test.  
  
 ![Podrobnosti o spuštění testu](../test/media/ute_testdetails.png "UTE_TestDetails")  
  
 V podokně podrobností testovací zobrazí následující informace:  
  
-   Název zdrojového souboru a číslo řádku zkušební metody.  
  
-   Stav testu.  
  
-   Uplynulý čas, který trvalo spuštění metody testu.  
  
 Pokud se test nezdaří, zobrazí se také v podokně podrobností:  
  
-   Zpráva, která vrácený částí unit test framework pro test.  
  
-   Trasování zásobníku v době testu se nezdařila.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_View_the_source_code_of_a_test_method"></a>Zobrazit zdrojový kód metody testu  
 Chcete-li zobrazit zdrojový kód pro zkušební metody v editoru Visual Studio, vyberte test a poté zvolte **otevřete testovací** v místní nabídce (klávesové: F12).  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Group_and_filter_the_test_list"></a>Skupiny a filtrování seznamu testů  
 [Seskupování seznamu testů](#BKMK_Grouping_the_test_list) **&#124;** [Seskupit podle vlastnosti](#BKMK_Group_by_traits) **&#124;** [Vyhledávání a filtrování seznamu testů](#BKMK_Search_and_filter_the_test_list)  
  
 Průzkumníka testů umožňuje seskupení testů do předdefinovaných kategorií. Většina systémů testů jednotek, které běží v testovací Explorer umožňují definovat vlastní kategorie a dvojice kategorie/hodnota pro seskupení testů. Seznam testů můžete také filtrovat podle porovnávání řetězců před testovacího vlastnosti.  
  
###  <a name="BKMK_Grouping_the_test_list"></a>Seskupování seznamu testů  
 A změnit tak, že jsou uspořádány testy, vyberte na šipku dolů vedle **Group By** tlačítko ![Průzkumníka testů skupiny tlačítko](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn") a vyberte nový seskupení kritéria.  
  
 ![Skupina testy podle kategorie ve Průzkumníka testů](../test/media/ute_groupbycategory.png "UTE_GroupByCategory")  
  
### <a name="test-explorer-groups"></a>Skupiny Průzkumníka testů  
  
|Skupina|Popis|  
|-----------|-----------------|  
|**Doba trvání**|Skupiny test čas spuštění: **Fast**, **střední**, a **pomalá**.|  
|**Výsledek**|Seskupí podle výsledků provedení testů: **testy se nezdařilo**, **přeskočen testy**, **předán testy**.|  
|**Vlastnosti**|Skupiny test dvojice kategorie/hodnota, že definujete. Přesvědčte se, zadejte znak kategorií a hodnoty je definována částí unit test framework.|  
|**Projekt**|Testovací skupiny podle názvu projektů.|  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_Group_by_traits"></a>Seskupit podle vlastnosti  
 Znak je obvykle dvojici název/hodnota kategorie, ale může být také jednu kategorii. Vlastnosti lze přiřadit k metody, které jsou určeny jako metodu testovací systém testování částí. Systém testování částí můžete definovat kategorie znak. Přidáním hodnoty do znak kategorie, které definují vlastní kategorie dvojice název/hodnota. Přesvědčte se, zadejte znak kategorií a hodnoty je definována částí unit test framework.  
  
 **Vlastnosti v jednotce Microsoft testování Framework pro spravovaný kód**  
  
 V Microsoft unit test framework pro spravované aplikace, definujte znak název / hodnota ve dvojici <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute> atribut. Test framework také obsahuje tyto předdefinované vlastnosti:  
  
|Znak|Popis|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.OwnerAttribute>|Kategorie vlastníka je určené systém testování částí a musíte zadat hodnotu řetězce vlastníka.|  
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>|Kategorie Priority je určené systém testování částí a vyžaduje, abyste zadejte celočíselnou hodnotu priority.|  
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>|Atribut TestCategory umožňuje zadat kategorii bez hodnoty. Kategorie definovaný v atributu TestCategory může být také kategorie TestProperty atributu.|  
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>|Atribut TestProperty umožňuje definovat dvojici znak kategorie/hodnota.|  
  
 **Vlastnosti v jednotce Microsoft testování Framework pro C++**  
  V tématu [jak používat Microsoft Unit Testing Framework pro C++](how-to-use-microsoft-test-framework-for-cpp.md).
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_Search_and_filter_the_test_list"></a>Hledání a filtrování seznamu testů  
 Filtry Průzkumníka testů můžete použít k omezení metody testovací ve svých projektech, které můžete zobrazit a spustit.  
  
 Zadejte řetězec v testovací Explorer vyhledávacího pole a zvolte ENTER, testovací seznam je filtrovaný pro zobrazení pouze testy, jejichž plně kvalifikované názvy obsahují řetězec.  
  
 Filtrovat podle různých kritérií:  
  
1.  Otevřete rozevírací seznam napravo od pole hledání.  
  
2.  Zvolte nové kritérium.  
  
3.  Zadejte hodnotu pro filtr mezi uvozovky.  
  
 ![Filtrovat testů v Průzkumníka testů](../test/media/ute_filtertestlist.png "UTE_FilterTestList")  
  
> [!NOTE]
>  Hledání se malá a velká písmena a odpovídat zadaný řetězec na libovolnou část hodnotu pro kritéria.  
  
|Kvalifikátor|Popis|  
|---------------|-----------------|  
|**Znak**|Vyhledá odpovídá znak kategorie a hodnotu. Přesvědčte se, zadejte znak kategorií a hodnoty jsou definovány částí unit test framework.|  
|**Projekt**|Vyhledá názvy projektů testů pro odpovídající položky.|  
|**Chybová zpráva**|Uživatelem definované chybové zprávy, které vrácený se nezdařilo hledání vyhodnotí pro odpovídající položky.|  
|**Cesta k souboru**|Plně kvalifikovaný název zdrojové soubory test vyhledá odpovídá.|  
|**Plně kvalifikovaný název**|Vyhledá soubor plně kvalifikovaný název testovací obory názvů, třídy a metody odpovídá.|  
|**Output**|Vyhledá uživatelem definované chybové zprávy, které jsou zapsány do standardního výstupního (stdout) nebo standardního chybového (stderr). Syntaxe k určení výstupní zprávy jsou definovány částí unit test framework.|  
|**Výsledek**|Vyhledá názvy kategorie Průzkumníka testů pro odpovídá: **se nezdařilo testy**, **přeskočen testy**, **předán testy**.|  
  
 K vyloučení podsady výsledků filtr, použijte následující syntaxi:  
  
```  
FilterName:"Criteria" -FilterName:"SubsetCriteria"  
```  
  
 Například  
  
```  
FullName:"MyClass" - FullName:"PerfTest"  
```  
  
 Vrátí všechny testy, které zahrnují "MyClass" v názvu s výjimkou tyto testy, které také obsahují "PerfTest" v názvu.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Create_custom_playlists"></a>Vytvořit vlastní seznamy stop  
 Můžete vytvořit a uložit seznam testy, které chcete spustit nebo zobrazit jako skupinu. Když vyberete seznam skladeb, testy v seznamu se zobrazí Průzkumníka testů. Test můžete přidat do více než jeden seznam stop, a všechny testy ve vašem projektu jsou k dispozici, když zvolíte výchozí **všechny testy** seznam stop.  
  
 ![Vyberte seznam stop](../test/media/ute_playlist.png "UTE_Playlist")  
  
 **Chcete-li vytvořit seznam stop**, zvolte jeden nebo více testů v Průzkumníka testů. V místní nabídce vyberte **přidat do seznamu stop**, **NewPlaylist**. Uložte soubor s názvem a umístění, které určíte v **vytvořit nový seznam stop** dialogové okno.  
  
 **Přidání testů do seznamu stop**, zvolte jeden nebo více testů v Průzkumníka testů. V místní nabídce vyberte **přidat do seznamu stop**a potom vyberte seznam skladeb, který chcete přidat testy, abyste se.  
  
 **Chcete-li otevřít seznam stop**, zvolte testovací, seznam stop v nabídce sady Visual Studio a buď ze seznamu naposledy použité seznamy stop, nebo zvolte otevřete seznam stop a zadat název a umístění seznamu stop.  
  
 Pokud jednotlivé testy žádné závislosti, které je zabránit spouštění v libovolném pořadí, zapnout spuštění testu paralelní s ![UTE &#95; parallelicon & č. 45; malá](../test/media/ute_parallelicon-small.png "UTE_parallelicon malá") přepínací tlačítko na panelu nástrojů. To může výrazně snížit čas potřebný k spustit všechny testy.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Debug_and_analyze_unit_tests"></a>Ladění a analýze testování částí  
 [Ladění testování částí](#BKMK_Debug_unit_tests) **&#124;** [Diagnostikovat problémy s výkonem metoda test](#BKMK_Diagnose_test_method_performance_issues) **&#124;** [Analýza pokrytí kódu testů jednotek](#BKMK_Analyzeunit_test_code_coverage)  
  
###  <a name="BKMK_Debug_unit_tests"></a>Ladění testování částí  
 Průzkumníka testů můžete spustit relaci ladění testů. Procházení kódu s ladicím programu sady Visual Studio bezproblémově přejdete oběma směry mezi testy částí a projekt v rámci testu. Spustit ladění:  
  
1.  V editoru Visual Studio nastavte zarážky v jedné nebo několika metod testovací, které chcete ladit.  
  
    > [!NOTE]
    >  Vzhledem k tomu, že testovací metody můžete spustit v libovolném pořadí, nastavte zarážky v všechny testovací metody, které chcete ladit.  
  
2.  V Průzkumníku testování vybrat metody testu a pak zvolte **ladění vybrané testy** v místní nabídce.  
  
 Další informace o ladicího programu, najdete v části [ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md).  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
###  <a name="BKMK_Diagnose_test_method_performance_issues"></a>Diagnostika problémů s výkonem test – metoda  
 Při diagnostice, proč test metoda trvá příliš dlouho, vyberte metodu v Průzkumníku otestovat a pak zvolte profil v místní nabídce. V tématu [prohlížeč výkonu](../profiling/performance-explorer.md).  
  
###  <a name="BKMK_Analyzeunit_test_code_coverage"></a>Analýza pokrytí kódu testů jednotek  
  
> [!NOTE]
>  Pokrytí kódu test jednotky je k dispozici pouze v aplikaci Visual Studio Enterprise.  
  
 Můžete určit dobu, ve skutečnosti je během testování testů jednotek pomocí nástroje Visual Studio code pokrytí kódu produktu. Pokrytí kódu můžete spustit na vybrané testy nebo na všechny testy v řešení.  
  
 Spouštění pokrytí kódu pro metody testu v řešení:  
  
1.  Zvolte **testy** v nabídce sady Visual Studio a zvolte **analýza pokrytí kódu**.  
  
2.  Vyberte jednu z následujících příkazů podnabídce:  
  
    -   **Vybrané testy** spouští test metody, které jste vybrali v testovací Explorer.  
  
    -   **Všechny testy** spouští všechny testovací metody v řešení.  
  
 Okno výsledků pokrytí kódu zobrazuje procento bloků kódu produktu, které byly vykonávají řádku, funkce, třída, obor názvů a modulu.  
  
 Další informace najdete v tématu [pomocí pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_External_resources"></a>Externí zdroje  
  
###  <a name="BKMK_Guidance"></a>Pokyny  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 2: testování částí: testování uvnitř](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
## <a name="see-also"></a>Viz také  
 [Testování částí kódu](../test/unit-test-your-code.md)   
 [Spuštění testování částí v podobě 64bitového procesu](../test/run-a-unit-test-as-a-64-bit-process.md)
