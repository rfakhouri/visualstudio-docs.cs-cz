---
title: Spouštění testů jednotek pomocí Průzkumníka testů | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.unittesting.testexplorer.overview
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: eda6a63b8d6e10b3eec3139ffa29143b0b5733ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="run-unit-tests-with-test-explorer"></a>Spouštění testů jednotek pomocí Průzkumníka testů

Použití **testování Explorer** ke spuštění testů jednotek v sadě Visual Studio nebo projektů testování částí třetích stran. Můžete také použít **testování Explorer** seskupení testů do kategorií, filtrování seznamu testů a vytvořit, uložit a spustit seznamy stop testů. Můžete ladit testy a analyzovat pokrytí test výkonu a kód.

Visual Studio obsahuje rozhraní testování částí Microsoft pro spravovaná a nativní kód. Však **testování Explorer** můžete také spouštět žádné jednotky test rozhraní, které implementovala testování Explorer adaptéru. Další informace týkající se instalace systémů testů jednotek třetích stran najdete v tématu [instalace systémů testů jednotek třetích stran](../test/install-third-party-unit-test-frameworks.md)

**Testování Explorer** testy můžete spustit z více testovací projekty v řešení a testovací třídy, které jsou součástí projekty kód produkční. Projektů testů můžete použít rozhraní test jinou jednotku. Pokud testovaného kódu je napsán pro rozhraní .NET Framework, může být napsán k testovacímu projektu v libovolném jazyce, který také cílí na rozhraní .NET Framework, bez ohledu na jazyk kódu cíl. Nativní kód projekty C/C++ musí být testována pomocí rozhraní test jednotky C++. Další informace najdete v tématu [zápis testování částí pro C/C++](writing-unit-tests-for-c-cpp.md).

## <a name="run-tests-in-test-explorer"></a>Spuštění testů Průzkumníka testů

Při sestavování testovacího projektu testů se zobrazí v Průzkumníku otestovat. Pokud není viditelná Průzkumníka testů, zvolte **Test** v sadě Visual Studio nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.

![Průzkumníka testů jednotek](../test/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")

Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v výchozí skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a  **Nejde spustit testy**. Můžete změnit způsob Průzkumníka testů skupiny testů.

Můžete provádět většinu práce hledání, uspořádání a spouštění testů z panelu nástrojů Průzkumníka testů.

![Spouštění testů z panelu nástrojů Průzkumníka testů](../test/media/ute_toolbar.png "UTE_ToolBar")

### <a name="run-tests"></a>Spouštění testů

Můžete spustit všechny testy v řešení, všechny testy ve skupině nebo sadu testů, které jste vybrali. Proveďte jednu z těchto akcí:

- Pokud chcete spustit všechny testy v řešení, zvolte **spustit všechny**.

- Pokud chcete spustit všechny testy ve výchozí skupině, vyberte **spustit...**  a pak zvolte skupinu v nabídce.

- Vyberte jednotlivé testy, které chcete spustit, otevřete v místní nabídce pro vybrané test a zvolte **spustit vybrané testy**.

- Pokud jednotlivé testy žádné závislosti, které je zabránit spouštění v libovolném pořadí, zapnout spuštění testu paralelní s ![UTE&#95;parallelicon&#45;malé](../test/media/ute_parallelicon-small.png "UTE_parallelicon malé") přepínací tlačítko na panelu nástrojů. To může výrazně snížit čas potřebný k spustit všechny testy.

Na panelu průchodu nebo selže v horní části okna Průzkumníka testů je animované jako Spusťte testy. Při ukončení spustit test změní zelená panelu průchodu nebo selhání, pokud všechny testy byly splněny, nebo červenou, pokud žádné test se nezdařil.

### <a name="run-tests-after-every-build"></a>Spouštění testů po každé sestavení

|||
|-|-|
|![Spustit po sestavení](../test/media/ute_runafterbuild_btn.png)|Spouštění testů jednotek po každé místní sestavení, zvolte **Test** v nabídce standardní a potom zvolte **spustit testy po sestavení** na panelu nástrojů Průzkumníka testů.|

## <a name="view-test-results"></a>Zobrazení výsledků testu

Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a **nejde spustit Testy**. V podokně podrobností v dolní části testování Explorer zobrazí spustit souhrn testu.

### <a name="view-test-details"></a>Zobrazit podrobnosti o testu

Chcete-li zobrazit podrobnosti o jednotlivé testy, vyberte test.

![Podrobnosti o spuštění testu](../test/media/ute_testdetails.png "UTE_TestDetails")

V podokně podrobností testovací zobrazí následující informace:

- Název zdrojového souboru a číslo řádku zkušební metody.

- Stav testu.

- Uplynulý čas, který trvalo spuštění metody testu.

Pokud se test nezdaří, zobrazí se také v podokně podrobností:

- Zpráva, která vrácený částí unit test framework pro test.

- Trasování zásobníku v době testu se nezdařila.

### <a name="view-the-source-code-of-a-test-method"></a>Zobrazit zdrojový kód metody testu

 Chcete-li zobrazit zdrojový kód pro zkušební metody v editoru Visual Studio, vyberte test a poté zvolte **otevřete testovací** v místní nabídce (klávesové: **F12**).

## <a name="group-and-filter-the-test-list"></a>Skupiny a filtrování seznamu testů

Průzkumníka testů umožňuje seskupení testů do předdefinovaných kategorií. Většina systémů testů jednotek, které běží v testovací Explorer umožňují definovat vlastní kategorie a dvojice kategorie/hodnota pro seskupení testů. Seznam testů můžete také filtrovat podle porovnávání řetězců před testovacího vlastnosti.

### <a name="group-tests-in-the-test-list"></a>Testy skupiny v seznamu testů

 A změnit tak, že jsou uspořádány testy, vyberte na šipku dolů vedle **Group By** tlačítko ![Průzkumníka testů skupiny tlačítko](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn") a vyberte nový seskupení kritéria.

 ![Skupina testy podle kategorie ve Průzkumníka testů](../test/media/ute_groupbycategory.png "UTE_GroupByCategory")

### <a name="test-explorer-groups"></a>Skupiny Průzkumníka testů

|Skupina|Popis|
|-----------|-----------------|
|**Doba trvání**|Skupiny test čas spuštění: **Fast**, **střední**, a **pomalá**.|
|**Výsledek**|Seskupí podle výsledků provedení testů: **testy se nezdařilo**, **přeskočen testy**, **předán testy**.|
|**Vlastnosti**|Skupiny test dvojice kategorie/hodnota, že definujete. Přesvědčte se, zadejte znak kategorií a hodnoty je definována částí unit test framework.|
|**Projekt**|Testovací skupiny podle názvu projektů.|

### <a name="group-by-traits"></a>Seskupit podle vlastnosti

 Znak je obvykle dvojici název/hodnota kategorie, ale může být také jednu kategorii. Vlastnosti lze přiřadit k metody, které jsou určeny jako metodu testovací systém testování částí. Systém testování částí můžete definovat kategorie znak. Přidáním hodnoty do znak kategorie, které definují vlastní kategorie dvojice název/hodnota. Přesvědčte se, zadejte znak kategorií a hodnoty je definována částí unit test framework.

 **Vlastnosti v jednotce Microsoft testování Framework pro spravovaný kód**

 V Microsoft unit test framework pro spravované aplikace, definujte znak název / hodnota ve dvojici <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute> atribut. Test framework také obsahuje tyto předdefinované vlastnosti:

|Znak|Popis|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.OwnerAttribute>|Kategorie vlastníka je určené systém testování částí a musíte zadat hodnotu řetězce vlastníka.|
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>|Kategorie Priority je určené systém testování částí a vyžaduje, abyste zadejte celočíselnou hodnotu priority.|
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>|Atribut TestCategory umožňuje zadat kategorii bez hodnoty. Kategorie definovaný v atributu TestCategory může být také kategorie TestProperty atributu.|
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>|Atribut TestProperty umožňuje definovat dvojici znak kategorie/hodnota.|

 **Vlastnosti v Microsoft Unit Testing Framework pro C++** najdete v části [jak používat Microsoft Unit Testing Framework pro C++](how-to-use-microsoft-test-framework-for-cpp.md).

### <a name="search-and-filter-the-test-list"></a>Hledání a filtrování seznamu testů

Filtry Průzkumníka testů můžete použít k omezení metody testovací ve svých projektech, které můžete zobrazit a spustit.

Zadejte řetězec v testovací Explorer vyhledávacího pole a zvolte ENTER, testovací seznam je filtrovaný pro zobrazení pouze testy, jejichž plně kvalifikované názvy obsahují řetězec.

Filtrovat podle různých kritérií:

1. Otevřete rozevírací seznam napravo od pole hledání.

2. Zvolte nové kritérium.

3. Zadejte hodnotu pro filtr mezi uvozovky.

![Filtrovat testů v Průzkumníka testů](../test/media/ute_filtertestlist.png "UTE_FilterTestList")

> [!NOTE]
> Hledání se malá a velká písmena a odpovídat zadaný řetězec na libovolnou část hodnotu pro kritéria.

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

Například `FullName:"MyClass" - FullName:"PerfTest"` vrátí všechny testy, které zahrnují "MyClass" v názvu, s výjimkou testy, které také obsahují "PerfTest" v názvu.

## <a name="create-custom-playlists"></a>Vytvořit vlastní seznamy stop

 Můžete vytvořit a uložit seznam testy, které chcete spustit nebo zobrazit jako skupinu. Když vyberete seznam skladeb, testy v seznamu se zobrazí Průzkumníka testů. Test můžete přidat do více než jeden seznam stop, a všechny testy ve vašem projektu jsou k dispozici, když zvolíte výchozí **všechny testy** seznam stop.

 ![Vyberte seznam stop](../test/media/ute_playlist.png "UTE_Playlist")

 **Chcete-li vytvořit seznam stop**, zvolte jeden nebo více testů v Průzkumníka testů. V místní nabídce vyberte **přidat do seznamu stop**, **NewPlaylist**. Uložte soubor s názvem a umístění, které určíte v **vytvořit nový seznam stop** dialogové okno.

 **Přidání testů do seznamu stop**, zvolte jeden nebo více testů v Průzkumníka testů. V místní nabídce vyberte **přidat do seznamu stop**a potom vyberte seznam skladeb, který chcete přidat testy, abyste se.

 **Chcete-li otevřít seznam stop**, zvolte testovací, seznam stop v nabídce sady Visual Studio a buď ze seznamu naposledy použité seznamy stop, nebo zvolte otevřete seznam stop a zadat název a umístění seznamu stop.

 Pokud jednotlivé testy žádné závislosti, které je zabránit spouštění v libovolném pořadí, zapnout spuštění testu paralelní s ![UTE&#95;parallelicon&#45;malé](../test/media/ute_parallelicon-small.png "UTE_parallelicon malé") přepínací tlačítko na panelu nástrojů. To může výrazně snížit čas potřebný k spustit všechny testy.

## <a name="debug-and-analyze-unit-tests"></a>Ladění a analýze testování částí

### <a name="debug-unit-tests"></a>Ladění testování částí

Průzkumníka testů můžete spustit relaci ladění testů. Procházení kódu s ladicím programu sady Visual Studio bezproblémově přejdete oběma směry mezi testy částí a projekt v rámci testu. Spustit ladění:

1. V editoru Visual Studio nastavte zarážky v jedné nebo několika metod testovací, které chcete ladit.

    > [!NOTE]
    > Vzhledem k tomu, že testovací metody můžete spustit v libovolném pořadí, nastavte zarážky v všechny testovací metody, které chcete ladit.

2. V Průzkumníku testování vybrat metody testu a pak zvolte **ladění vybrané testy** v místní nabídce.

 Další informace o ladicího programu, najdete v části [ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md).

### <a name="diagnose-test-method-performance-issues"></a>Diagnostika problémů s výkonem test – metoda

 Při diagnostice, proč test metoda trvá příliš dlouho, vyberte metodu v Průzkumníku otestovat a pak zvolte profil v místní nabídce. V tématu [prohlížeč výkonu](../profiling/performance-explorer.md).

### <a name="analyze-unit-test-code-coverage"></a>Analýza pokrytí kódu testů jednotek

Můžete určit dobu, ve skutečnosti je během testování testů jednotek pomocí nástroje Visual Studio code pokrytí kódu produktu. Pokrytí kódu můžete spustit na vybrané testy nebo na všechny testy v řešení.

Spouštění pokrytí kódu pro metody testu v řešení:

1. Zvolte **testy** v nabídce sady Visual Studio a zvolte **analýza pokrytí kódu**.

2. Vyberte jednu z následujících příkazů podnabídce:

    - **Vybrané testy** spouští test metody, které jste vybrali v testovací Explorer.

    - **Všechny testy** spouští všechny testovací metody v řešení.

Okno výsledků pokrytí kódu zobrazuje procento bloků kódu produktu, které byly vykonávají řádku, funkce, třída, obor názvů a modulu.

Další informace najdete v tématu [pomocí pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

## <a name="test-shortcuts"></a>Test zástupců

Testy můžete spustit z **testování Explorer**, kliknutím pravým tlačítkem myši v editoru kódu na test a výběrem **spuštění testu**, nebo pomocí výchozí [zkratek testování Exploreru](../ide/default-keyboard-shortcuts-in-visual-studio.md#bkmk_testexplorerGLOBAL) v Visual Studio. Některé zkratky jsou založené na kontextu. To znamená, že spustit nebo ladění testy podle toho, kde kurzor v editoru kódu. Pokud kurzor uvnitř metody test, který testovací metoda spustí. Kurzor je na úrovni třídy, pak spusťte všechny testy v dané třídě. Toto je stejný pro úroveň oboru názvů.

|Časté příkazy| Klávesové zkratky|
|--------------|------------------------|
|TestExplorer.DebugAllTestsInContext|Ctrl+R, Ctrl+T|
|TestExplorer.RunAllTestsInContext|Ctrl+R, T|

> [!NOTE]
> V abstraktní třídu, nelze spustit test, protože testy jsou definována pouze v abstraktní třídy a není vytvořena instance. Ke spuštění testů v abstraktní třídy, vytvořte třídu, která je odvozena z abstraktní třídy.

## <a name="see-also"></a>Viz také

- [Testování částí kódu](../test/unit-test-your-code.md)
- [Spuštění testování částí v podobě 64bitového procesu](../test/run-a-unit-test-as-a-64-bit-process.md)
