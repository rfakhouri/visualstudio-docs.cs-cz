---
title: Analýza výsledků zátěžových testů a chyb v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.pageresult
- vs.test.load.dialog.column
- vs.test.load.monitor.requestresult
- vs.test.load.monitor.testresult
- vs.test.load.monitor.table.view
- vs.test.load.monitor.agentresult
- vs.test.load.monitor.transactionresult
helpviewer_keywords:
- tables, Load Test Viewer options
- load test results, tables
- load tests, Load Test Viewer
- data [Visual Studio ALM], load test tables
- Load Test Viewer, tables
- load tests, results tables
ms.assetid: 0a84bda3-6051-45eb-9c7f-d57419e1f97d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 2599968aad98339014182edf21282a4e5e26fbcf
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234517"
---
# <a name="analyze-load-test-results-and-errors-in-the-tables-view-of-the-load-test-analyzer"></a>Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení analyzéru spouštění testů

Při zobrazení výsledků zátěžového testu, spuštění, můžete zobrazit různých podoken, které poskytují různé způsoby, jak analyzovat data. Můžete zobrazit data jako graf, pokud chcete zobrazit, jak změny v čase, nebo můžete zobrazit data jako podrobné tabulky.

Chcete-li přepnout do zobrazení tabulky, zvolte **tabulky** na **zátěžový test** panelu nástrojů. Přepínat mezi různých tabulek, použijte **tabulky** rozevíracího seznamu na panelu nástrojů nad mřížky tabulky. V zobrazení tabulky můžete zobrazit až čtyři tabulky najednou. Další informace najdete v tématu [dlaždice zatížení testovací tabulky](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#tile-load-test-tables) v tomto tématu.

Většina číselných hodnot, které se zobrazují v tabulce pro čítače výkonu jsou kumulativní přes celou zátěžový test, spustit. Sloupce s názvem **poslední** představují výjimku a představují hodnotu od poslední intervalu vzorkování.

> [!NOTE]
> Sloupce s názvem **poslední** jsou k dispozici pouze tehdy, když je prováděna zátěžový test. Po dokončení testu zatížení tyto sloupce nejsou k dispozici.

 Většina tabulky lze řadit tak, že zvolíte název sloupce, který chcete seřadit. Ve výchozím nastavení nezobrazují některé tabulky všechny dostupné sloupce. Přidáním sloupce do tabulky, pokud jsou k dispozici sloupce. Chcete-li přidat sloupce, klikněte pravým tlačítkem na tabulky a poté zvolte **přidat nebo odebrat sloupce**.

> [!NOTE]
> Můžete zkopírovat data z tabulky do jiných aplikací, jako je například aplikace Excel pro další analýzu.

## <a name="the-load-test-tables"></a>V tabulkách testu zatížení

 Následující tabulka uvádí tabulky, které jsou k dispozici k analýze testovacích bězích zatížení.

|Název tabulky|Popis|
|----------------|-----------------|
|Chyby|Zobrazí seznam chyb, ke kterým došlo během spuštění zátěžového testu. Další informace najdete v tématu [chyby tabulce](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-errors-table) v tomto tématu a [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md).|
|Stránky|Zobrazí seznam stránek přístup během spuštění zátěžového testu. Některá data v této tabulce je k dispozici až po dokončení testu zatížení. Další informace najdete v tématu [postupy: zobrazení webové stránky odpovědi](../test/how-to-view-web-page-response-time-in-a-load-test.md).|
|požadavky|Zobrazí podrobnosti pro jednotlivé požadavky vydané během zátěžového testu. To zahrnuje všechny požadavky HTTP a závislé požadavky, například bitové kopie. Další informace najdete v tématu [tabulky žádosti o](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-requests-table) v tomto tématu.|
|Trasování SQL|Zobrazí výsledky trasování SQL. Tato tabulka je k dispozici až po dokončení testu zatížení, a pouze v případě, že trasování SQL se používá během testu. Další informace najdete v tématu [tabulky dat trasování SQL se](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-sql-trace-data-table) v tomto tématu.|
|Testy|Zobrazí podrobnosti pro jednotlivé testy spustit během zátěžového testu. Další informace najdete v tématu [testy tabulce](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-tests-table) v tomto tématu.|
|Prahové hodnoty|Zobrazí seznam mezních pravidel, ke kterým došlo během spuštění zátěžového testu. Další informace najdete v tématu [analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md).|
|Transakce|Zobrazí seznam transakcí, které došlo k chybě během spuštění zátěžového testu. Další informace najdete v tématu [transakce tabulce](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-transactions-table) v tomto tématu.|
|Agenti|Zobrazí jenom v případě, že je zátěžový test pomocí testovacího kontroléru a testovacích agentů. Zobrazí seznam agentů, které byly použity během spuštění zátěžového testu. Agenti tabulka obsahuje, kolik požadavků agenta otestovány a těchto požadavků, kolik se nezdařilo. Kromě toho agenty tabulka obsahuje počet testů v poměru testů zatížení testy, které agent otestovali a z nich, kolik se nezdařilo.|
|Podrobnosti o testu|Zobrazí podrobnosti pro testy v poměru testů pro zátěžový test. Podrobnosti jsou název testu, scénář, který byl test, při spuštění testu, délka doba trvání testu, spuštění a testovací výsledek, která znamená, pokud test předán nebo se nezdařilo. Pokud test se nezdařil, odkaz se nachází v **podrobnosti** sloupce. Můžete použít odkaz, kterým se dostanete k Editor testu výkonnosti webu se zvýrazněnou chybných požadavků.|

## <a name="collect-percentile-data"></a>Shromažďování dat percentilu

 Některé tabulky testu zatížení může obsahovat další sloupce, které zahrnují percentilu data a časy odezvy rozdělen do skupiny založené na emulace sítě. Ve výchozím nastavení nejsou shromažďovány tato data. Percentil dat je k dispozici pouze při ukládání výsledků do databáze, a ne v případě, že můžete uložit místně. Další informace najdete v tématu [v úložišti testovací výsledky načíst výsledky testu zatížení Správa](../test/manage-load-test-results-in-the-load-test-results-repository.md). Kromě toho shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte konkrétní spuštění uzlu nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **StatisticsOnly** nebo **AllIndividualDetails**. Další informace najdete v tématu [postupy: zobrazení webové stránky odpovědi](../test/how-to-view-web-page-response-time-in-a-load-test.md).

## <a name="the-requests-table"></a>Tabulka požadavků

 **Požadavky** tabulky zobrazí podrobnosti pro jednotlivé požadavky vydané během zátěžového testu. To zahrnuje všechny požadavky HTTP a závislé požadavky, například bitové kopie. V tabulce jsou uvedeny požadavky test a scénář, protože jeden požadavek můžou být součástí mnoha testy a scénáře.

 V následující tabulce jsou uvedeny ve sloupcích v **požadavky** tabulky:

|Sloupec|Popis|Ve výchozím nastavení viditelné|
|------------|-----------------|------------------------|
|**Požadavek**|Adresa URL požadavku. Například *home.html*, nebo *oranžová arrow.gif*.|Ano|
|**Scénář**|Název tohoto scénáře.|Ano|
|**Test**|Název testu.|Ano|
|**Celkový počet**|Celkový počet tento webový požadavek test výkonu vydán během zátěžového testu spustit. Celkový počet zahrnuje předaný a k selhání požadavků, ale nezahrnuje požadavky uložené v mezipaměti, protože nejsou vydány na webový server.|Ano|
|**Předaný**|Počet přístupů žádosti byl vydán a předán.|Ne|
|**Se nezdařilo**|Počet přístupů žádosti byl vydán a se nezdařilo. Položky v tomto sloupci se zobrazí jako hypertextové odkazy. Můžete vybrat libovolný hypertextový odkaz zobrazíte seznam jednotlivé chyby v **chyby testu zatížení** dialogové okno. Další informace najdete v tématu [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md).|Ano|
|**V mezipaměti**|Celkový počet časy, kdy již do mezipaměti žádosti.|Ne|
|**Počet požadavků za sekundu**|Rychlost za sekundu požadavku během spuštění zátěžového testu.|Ne|
|**Předaný za sekundu**|Rychlost za sekundu během zátěžového testu, spuštění pro instance této žádosti, který předává této žádosti.|Ne|
|**Za sekundu**|Rychlost, jakou za sekundu tohoto požadavku během zátěžového testu spusťte pro instance této žádosti, která se nezdařila.|Ne|
|**Prvním bajtů**|Průměrný čas pro přijetí první bajt odpovědi, měřená od okamžiku, kdy požadavek byl odeslán na webový server. Jednotky jsou sekund.|Ne|
|**Doba odezvy**|Průměrný čas pro přijetí celé odpovědi na žádost, měřená od okamžiku, kdy požadavek byl odeslán na webový server. Jednotky jsou sekund.|Ano|
|**Délka obsahu**|Průměrná délka obsahu odpovědi na požadavek. Jednotky jsou bajtů.|Ano|

## <a name="the-tests-table"></a>V tabulce testů

 **Testy** tabulky zobrazí podrobnosti pro jednotlivé testy spustit během zátěžového testu. V tabulce je přehled testů test a scénář, protože jeden test můžou být součástí mnoho scénářů.

 V následující tabulce jsou uvedeny ve sloupcích v **testy** tabulky.

|Sloupec|Popis|Ve výchozím nastavení viditelné|
|------------|-----------------|------------------------|
|**Test**|Název testu.|Ano|
|**Scénář**|Název tohoto scénáře.|Ano|
|**Celkový počet**|Celkový počet spuštění testu ve scénáři. To zahrnuje kolikrát test předán a se nezdařilo.|Ano|
|**Předaný**|Počet přístupů test byl spuštění ve scénáři s.|Ano|
|**Se nezdařilo**|Počet přístupů test byl spustit v tomto scénáři a selhal. Položky v tomto sloupci se zobrazí jako hypertextové odkazy. Můžete vybrat libovolný hypertextový odkaz zobrazíte seznam jednotlivé chyby v **chyby testu zatížení** dialogové okno. Další informace najdete v tématu [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md).|Ano|
|**Testy za sekundu**|Rychlost za sekundu během zátěžového testu, spuštění testu.|Ano|
|**Předaný za sekundu**|Rychlost za sekundu během zátěžového testu, spuštění pro instance tohoto testu, který předává tento test.|Ne|
|**Za sekundu**|Rychlost, jakou za sekundu tento test během zátěžového testu spusťte pro instance tohoto testu, který selhal.|Ne|
|**Testovacího času**|Průměrná doba k provedení testu během spuštění zátěžového testu. Jednotky jsou sekund.|Ano|
|**90 % testovacího času**|90 percentilu hodnota testovacího času.|Ne|
|**95 % testovacího času**|95. percentil hodnota testovacího času.|Ano|
|**Požadavky a testovací**|Průměrný počet požadavků v testu, pokud je výkonu webových testů.|Ne|

## <a name="the-transactions-table"></a>V tabulce transakce

 **Transakce** tabulka uvádí seznam transakcí, které nastaly během spuštění zátěžového testu. Transakce znamenají transakce definované v testu výkonnosti webu nebo časovače definované v testování částí. Transakce není odkaz na databázové transakce.

 V následující tabulce jsou uvedeny ve sloupcích v **transakce** tabulky.

> [!NOTE]
> Chcete-li zobrazit všechny sloupce, je nutné povolit úložiště podrobností časování vlastnost, která je spojena s aktivní spustit nastavení. Další informace najdete v tématu [postupy: určení vlastnosti úložiště podrobností časování](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).

|Sloupec|Popis|Viditelné bez podrobností časování|
|------------|-----------------|------------------------------------|
|**Transakce**|Název transakce.|Ano|
|**Scénář**|Název tohoto scénáře.|Ano|
|**Test**|Název testu.|Ano|
|**Celkový počet**|Celkový počet transakcí vydán během spuštění zátěžového testu.|Ano|
|**Čas transakce**|Čas spuštění transakce během spuštění zátěžového testu. Pro testy výkonnosti webu, vezměte v úvahu dobu je zahrnutých do výpočtu. Jednotky jsou sekund.|Ne|
|**Doba odezvy**|Doba odezvy pro webové transakce test výkonu v zátěžovém testu spustit. Doba odezvy se liší od doby transakce v tom, že doba odezvy neobsahuje žádné Považujte dobu, po kterou během transakce došlo k chybě. Jednotky jsou sekund.|Ne|
|**Prům. Čas transakce**|Transakce průměrný čas. Tentokrát zahrnuje časů přemýšlení. Například pokud máte tři požadavky a každá z nich má Představte si, že čas, tentokrát bude obsahovat ty časy přemýšlení a požadavky skutečný čas spuštění.|Ne|
|**Prům. Doba odezvy**|Průměrná doba odezvy pro test transakci webové výkonu v zátěžovém testu spustit. Doba odezvy se liší od doby transakce v tom, že doba odezvy neobsahuje žádné Považujte dobu, po kterou během transakce došlo k chybě. Jednotky jsou sekund.|Ne|
|**Minimální doba odezvy**|Nezahrnuje časů přemýšlení.|Ne|
|**Doba odezvy maximální**|Nezahrnuje časů přemýšlení.|Ne|
|**Doba odezvy střední**|Nezahrnuje časů přemýšlení.|Ne|
|**Doba odezvy 90 %**|Hodnota 90 percentilu čas transakce. Nezahrnuje časů přemýšlení. **Poznámka:** se to neliší od Visual Studio Team System 2008 testu zatížení agenta, který používá **90 % doby transakce** hodnotu.|Ne|
|**Doba odezvy 95 %**|Hodnota 95. percentil čas transakce. Nezahrnuje časů přemýšlení. **Poznámka:** se to neliší od Visual Studio Team System 2008 testu zatížení agenta, který používá **95 % doby transakce** hodnotu.|Ne|
|**Doba odezvy 99 %**|99th hodnota percentilu čas transakce. Nezahrnuje časů přemýšlení.|Ne|
|**Doba odezvy směrodatné odchylky**|Nezahrnuje časů přemýšlení.|Ne|

## <a name="the-errors-table"></a>Tabulka chyby

 Při spuštění zátěžového testu můžete analyzovat chyby, ke kterým dochází. Analýza chyb a úpravě testů jsou důležitou součástí procesu testu zatížení. Pokud došlo k chybám, **chyby** hypertextový odkaz se zobrazí na panelu Stav testu zatížení a určuje počet chyb, které došlo k chybě. Zobrazit tabulku chyby, zvolte hypertextový odkaz.

 Chyby tabulky skupiny chybách, ke kterým došlo během zatížení testovací typ a podtyp chyby. K dispozici je také **celkový** řádek v tabulce, která určuje celkový počet všech chyb, které došlo k chybě.

 Chyby tabulka obsahuje následující sloupce:

|Sloupec|Popis|Ve výchozím nastavení viditelné|
|------------|-----------------|------------------------|
|Typ|Typ chyby. Například HttpError.|Ano|
|SubType|Podtyp chyby. Například LoadTestException.|Ano|
|Počet|Počet chyb typu, k níž došlo během zátěžového testu. Položky v tomto sloupci se zobrazí jako hypertextové odkazy. Můžete vybrat libovolný hypertextový odkaz zobrazíte seznam jednotlivé chyby.|Ano|
|Poslední zprávy|Zpráva popisující chybu Například 404 - NotFound.|Ano|

 Další informace najdete v tématu [práce s tabulkami testu zatížení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

### <a name="drill-down-to-the-error-list"></a>Přejít k podrobnostem a v seznamu chyb

Chyby tabulky skupiny chyb podle typ a podtyp chyby. Chcete-li zobrazit tabulku jednotlivé chyby, je zobrazit **chyby testu zatížení** dialogové okno. Chcete-li zobrazit dialogové okno, zvolte hypertextový odkaz v **počet** sloupec tabulky chyb. Můžete také zobrazit dialogové okno pravým tlačítkem myši na řádek v tabulce chyb, který je vyplněný a zvolením **chyby**.

> [!NOTE]
> Se shromažďují pouze prvních 1000 instance libovolnou kombinaci typ a podtyp chyby. Při zobrazení **chyby testu zatížení** dialogové okno, zobrazí se maximálně 1000 první instance této chyby.

**Chyby testu zatížení** tabulka obsahuje následující sloupce:

|Sloupec|Popis|
|------------|-----------------|
|**Čas**|Době zatížení otestujte na které se stala chyba.|
|**Agent**|Název počítače agenta, na kterém došlo k chybě. To je důležité, když spustíte zátěžových testů pomocí testovacích kontrolérů a testovacích agentů. Další informace najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).|
|**Test**|Název výkon webové otestovat ve kterém se stala chyba.|
|**Scénář**|Název tohoto scénáře, ve kterém došlo k chybě.|
|**Požadavek**|Adresa URL požadavku, ve kterém došlo k chybě.|
|**Typ**|Typ chyby. Například HttpError.|
|**Podtyp**|Podtyp chyby. Například LoadTestException.|
|**Text**|Text chybové zprávy. Například 404 - NotFound.|
|**Zásobníku**|Položky v tomto sloupci jsou prázdné nebo slovo **zásobníku** formátována jako hypertextový odkaz. Můžete zvolit hypertextového odkazu pro zobrazení trasování zásobníku chyby.|
|**Podrobnosti**|Položky v tomto sloupci jsou prázdné nebo slovo **TestLog** formátována jako hypertextový odkaz. Tento odkaz vám může pomoci identifikovat chyby v zátěžovém testu. Například výběr **TestLog** odkaz chyby žádost o test výkonu webů se otevře výsledky pro test výkonnosti Web v prohlížeč pro výsledky testů výkonnosti webu a zvýraznit chybu požadavku.|

> [!NOTE]
> V tabulce můžete řadit výběrem záhlaví sloupců.

## <a name="the-sql-trace-data-table"></a>V tabulce dat trasování SQL

Můžete shromáždit data trasování SQL během zátěžového testu spusťte k analýze později. Shromažďování dat trasování umožňuje identifikovat slowest spuštěné dotazy a uložené procedury v databázi systému SQL Server během testování.

Pokud je povolené trasování SQL, soubor se vytvoří během zátěžového testu spuštění, který obsahuje data trasování. Tato data se automaticky uloží do uložení výsledků zátěžového testu na konci testu, spuštění a trasovací soubor se odstraní. Analýza dat trasování v **trasování SQL** tabulky po dokončení zátěžový test.

### <a name="to-view-sql-trace-data"></a>K zobrazení dat trasování SQL

1. V Analyzéru zátěžového testu zvolte **tabulky** na panelu nástrojů a ujistěte se, že se zobrazí mřížku tabulky.

2. V **tabulky** rozevíracím seznamu vyberte **trasování SQL**.

3. Data trasování, která nebyla shromážděna při spuštění se zobrazí v mřížce. V tabulce jsou uvedeny slowest běžící operace SQL, které jsou seřazené podle doby trvání, s nejpomalejší v horní části. Obvykle **doba trvání** sloupec je první sloupec prozkoumat. Data se zobrazí v milisekundách.

   Zobrazení sloupců jsou následující:

    - **Event – třída**

    - **Doba trvání**

    - **CPU**

    - **Čtení**

    - **Zapíše**

    - **textData**

    - **Čas spuštění**

    - **čas ukončení**

   Pokud chcete trasovat události SQL než data v těchto sloupcích identifikovat, můžete nastavit vlastní vlastní trasování SQL pomocí nástroje SQL Profiler samostatné ze sady Visual Studio.

## <a name="tile-load-test-tables"></a>Dlaždice zatížení testovací tabulky

Při zobrazení výsledků zátěžového testu, spuštění, můžete zobrazit data jako podrobné tabulky. Chcete-li přepnout do zobrazení tabulky, zvolte **tabulky** na **zátěžový test** panelu nástrojů. Tabulky, které jsou k dispozici jsou **chyby**, **stránky**, **požadavky**, **trasování SQL**, **testy**,  **Prahové hodnoty**, a **transakce**. Další informace najdete v tématu [práce s tabulkami testu zatížení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

V zobrazení tabulky můžete zobrazit až čtyři tabulky v čase bez tabulky překrývající se.

### <a name="to-tile-tables"></a>Na dlaždici tabulky

1. Na **Analyzéru zátěžového testu** nástrojů vyberte **tabulky**.

     Otevře zobrazení tabulky. Výchozí rozložení je dva vodorovné panely.

2. Na **Analyzéru zátěžového testu** nástrojů, vyberte **rozložení** tlačítko a pak vyberte jednu z následujících možností:

    - **Jeden panely**

    - **Dva vodorovné panelů**

    - **Tři vodorovné panely**

    - **Čtyři vodorovné panelů**

3. Přepínat mezi různých tabulek, pomocí rozevíracího seznamu výše mřížky tabulky v jednotlivých panelech.

    > [!NOTE]
    > Více než jeden panel nelze zobrazit stejné tabulky. Pokud změníte v tabulce zobrazí jeden panelu již zobrazen panelu jinou tabulku, přepínač tabulky panelů.

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Postupy: přístup k analýze výsledků zátěžového testu](../test/how-to-access-load-test-results-for-analysis.md)
- [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Analýza překročení mezních hodnot pravidlo](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Správa výsledků zátěžových testů v úložišti testovací výsledky načíst](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Přehled souhrnu výsledků testu zatížení](../test/load-test-results-summary-overview.md)