---
title: "Spuštění, organizovat a ladění testů jednotek v sadě Visual Studio | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d99b0ab4ce0b10a4a03f80c95a004df0a9facef5
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="run-organize-and-debug-unit-tests"></a>Spuštění, organizovat a ladění testování částí

Toto téma popisuje postup spouštění testů jednotek pomocí Průzkumníka testů v sadě Microsoft Visual Studio.

## <a name="unit-test-frameworks-and-test-projects"></a>Systémů testování částí a projektů testů

Visual Studio obsahuje Microsoft jednotky testování rozhraní pro spravovaný kód a nativní kód jazyka C++. Testy můžete spustit Průzkumníka testů z více testovací projekty v řešení a z testovací tříd, které jsou součástí projekty kód produkční. Projektů testování může být libovolnou kombinací Visual c++ nebo Visual C# a Visual Basic jednotkové testování architektury. Pokud testovaného kódu je napsán pro rozhraní .NET Framework, může být napsán k testovacímu projektu v libovolném jazyce rozhraní .NET Framework, bez ohledu na jazyk kódu cíl. Nativní kód projekty C/C++ musí být testována pomocí rozhraní test jednotky C++.

## <a name="run-tests-in-test-explorer"></a>Spuštění testů Průzkumníka testů

Při sestavování testovacího projektu testů se zobrazí v Průzkumníku otestovat. Pokud není viditelná Průzkumníka testů, zvolte **Test** v sadě Visual Studio nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.

![Jednotky Průzkumníka testů](../test/media/ute_failedpassednotrunsummary.png)

Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v výchozí skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a  **Nejde spustit testy**. Můžete změnit způsob Průzkumníka testů skupiny testů.

Můžete provádět většinu práce hledání, uspořádání a spouštění testů z panelu nástrojů Průzkumníka testů.

![Spouštění testů z panelu nástrojů Průzkumníka testů](../test/media/ute_toolbar.png)

### <a name="run-tests"></a>Spouštění testů

Můžete spustit všechny testy v řešení, všechny testy ve skupině nebo sadu testů, které jste vybrali. Proveďte jednu z těchto akcí:

- Pokud chcete spustit všechny testy v řešení, zvolte **spustit všechny**.

- Pokud chcete spustit všechny testy ve výchozí skupině, vyberte **spustit...**  a pak zvolte skupinu v nabídce.

- Vyberte jednotlivé testy, které chcete spustit, otevřete místní nabídku pro vybrané testu a pak zvolte **spustit vybrané testy**.

Na panelu průchodu nebo selže v horní části okna Průzkumníka testů je animované jako Spusťte testy. Při ukončení spustit test změní zelená panelu průchodu nebo selhání, pokud všechny testy byly splněny, nebo červenou, pokud žádné test se nezdařil.

## <a name="view-test-results"></a>Zobrazení výsledků testu

Při spuštění, zápisu a znovu spusťte testy Průzkumníka testů zobrazí výsledky v skupiny **testy se nezdařilo**, **předán testy**, **přeskočen testy** a **nejde spustit Testy**. V podokně podrobností v dolní části testování Explorer zobrazí spustit souhrn testu.

### <a name="view-test-details"></a>Zobrazit podrobnosti o testu

Chcete-li zobrazit podrobnosti o jednotlivé testy, vyberte test.

V podokně podrobností testovací zobrazí následující informace:

- Název zdrojového souboru a číslo řádku zkušební metody.

- Stav testu.

- Uplynulý čas, který trvalo spuštění metody testu.

Pokud se test nezdaří, zobrazí se také v podokně podrobností:

- Zpráva, která vrácený částí unit test framework pro test.

- Trasování zásobníku v době testu se nezdařila.

### <a name="view-the-source-code-of-a-test-method"></a>Zobrazit zdrojový kód metody testu

Chcete-li zobrazit zdrojový kód pro zkušební metody v editoru Visual Studio, vyberte test a poté zvolte **otevřete testovací** v místní nabídce nebo stiskněte klávesu **F12**.

## <a name="organize-the-test-list"></a>Uspořádání seznamu testů

### <a name="group-tests"></a>Testy skupiny

Ve výchozím nastavení, zobrazí Průzkumníka testů testy jako uzly podřízené **se nezdařilo testy**, **předán testy**, **přeskočen testy** a **není spuštění testů**.

|||
|-|-|
|![Tlačítko Testovat Explorer skupiny](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn")|Pro seskupení testů podle doby potřebné k jejich provedení, otevřete **Group By** seznam a vyberte **doba trvání**. Zvolte **výsledek testu** přepnout na původní seskupení.|

### <a name="search-and-filter-the-test-list"></a>Hledání a filtrování seznamu testů

Když máte velký počet testů, můžete zadat do pole Hledat Průzkumníka testů pro filtrování seznamu podle zadaného řetězce. Filtr můžete omezit na konkrétní typy řetězců výběrem ze seznamu filtru před zadejte hledaný řetězec.

![Vyhledávací filtr kategorií](../test/media/ute_searchfilter.png)

## <a name="debug-unit-tests"></a>Ladění testování částí

Průzkumníka testů můžete spustit relaci ladění testů. Procházení kódu s ladicím programu sady Visual Studio bezproblémově přejdete oběma směry mezi testy částí a projekt v rámci testu. Spustit ladění:

1. V editoru Visual Studio nastavte zarážky v jedné nebo několika metod testovací, které chcete ladit.

    > [!NOTE]
    > Vzhledem k tomu, že testovací metody můžete spustit v libovolném pořadí, nastavte zarážky v všechny testovací metody, které chcete ladit.

1. V Průzkumníku testování vybrat metody testu a pak zvolte **ladění vybrané testy** v místní nabídce.

Další informace o ladicího programu najdete v tématu [ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md).
