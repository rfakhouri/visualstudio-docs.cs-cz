---
title: Panel čítačů k analýze zátěžových testů v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, counters panel
ms.assetid: e1a388d7-5d33-4631-931a-5653ac4aefdc
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 229097b12e5b32e6be6af6b9614a628346780063
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49921480"
---
# <a name="use-the-counters-panel-in-graphs-view-and-tables-view"></a>Použití panelu čítačů v zobrazení grafů a zobrazení tabulek

**Čítače** panel je v zobrazení grafů a zobrazení tabulek v Analyzéru zátěžového testu zobrazen během zátěžového testu nebo během analýzy výsledku zátěžového testu. Další informace najdete v tématu [výsledků zátěžového testu analyzovat v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md), [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) a [postupy: přístup k analýzevýsledkyzátěžovéhotestu](../test/how-to-access-load-test-results-for-analysis.md).

**Čítače** panel zobrazuje strukturovaných zobrazení všech čítačů výkonu, které byly shromážděny během zátěžového testu. Můžete zobrazit nebo skrýt **čítače** panel výběrem **zobrazit Panel čítačů** na **Analyzéru zátěžového testu** nástrojů.

Čítačů jsou uspořádány do stromové struktury, ve kterém listové uzly jsou instance čítačů výkonu, které mohou být zaneseny do grafu.

Panel čítačů obsahuje následující funkce:

-   Komunikuje se informace o porušení prahové hodnoty.

-   Výběr čítače pro vykreslování do grafu.

-   Strukturovaného stromové zobrazení všechny čítače výkonu shromážděné při spuštění následující primární větví zátěžového testu:

    -   **Celkové:** obsahuje souhrn dat čítače výkonu pro každý testovací agent a pro celý zátěžový test.

    -   **Název scénáře:** větve označené názvy scénářů zátěžových testů ve stromu čítačů výkonu obsahují všechny instance čítačů zátěžového testu přidružené konkrétnímu scénáři zátěžového testu. Většina počítadla testu zatížení jsou vnořeny do větve scénář.

         Scénář větev obsahuje uzly test webového výkonu. Uzly test webového výkonu obsahovat stránky, požadavků a transakce uzly. Libovolný uzel typu list v této struktuře je čítač výkonu, které mohou být přidány do grafu.

    -   **Počítače:** obsahuje všechny čítače nezátěžových testů seskupené dle počítače. Na počítačích větev obsahuje uzel pro každý počítač, který je spojen s kontrolerem testů zatížení zadané v části role aktuálně vybraná nastavení testu. Další informace najdete v tématu [testovací kontrolery a testovací agenty](configure-test-agents-and-controllers-for-load-tests.md).

         Každý uzel počítače obsahuje sadu kategorií čítačů výkonu shromážděná z tohoto počítače. Kategorie obsahovat čítače a čítače obsahovat názvy instancí čítačů výkonu.

    -   **Chyby:** obsahuje všechny chyby zjištěné během zátěžového testu. Uzel chyby obsahuje několik uzlů podkategorie chyb. Podkategorií jsou specifické pro různé druhy chyb, třeba výjimky a chyby protokolu HTTP.

### <a name="scenario-name-node-in-counters-panel"></a>Scénář název uzlu na panelu čítačů

|Panel čítačů|Popis|
|-|-|
|![Čítač panelu scénář název uzlu](../test/media/ltest__namenode.png)|1. V tomto uzlu se zobrazí všechny čítače výkonu přidružený k Scenario1 zátěžového testu.<br />2. Všechny testy scénáře jsou umístěny pod jeho uzlem. Popisek označuje název testu.<br />3. Listové uzly pod uzlem testu jsou testovací případ počítadla testu zatížení, kde je název instance čítače název testu.<br />4. Načíst všechny čítače nezátěžových testů stránky spojené s větví test webového výkonu. V tomto uzlu jsou zde uvedené zátěžový test tempem instance čítače přidružené ke stránce přihlášení (název sestavy) získat z testu výkonnosti webu IBuyBrowse v Scenario1 zátěžového testu.<br />5. Listové uzly pod uzlem stránky se načíst testovací stránce čítače.<br />6. Načíst všechny čítače požadavky testu, které instance přidružené k testu výkonnosti webu jsou obsaženy v rámci větve test webového výkonu. V tomto uzlu požadavku všechny čítače nezátěžových přidružené k žádosti o přihlášení PŘINESE IBuyBrowse testu výkonnosti webu Scenario1 o zátěžový test obsahoval tady (název sestavy).<br />7. Listových uzlů uzlu požadavku se načíst testovací požadavek čítače.<br />8. Všechny transakce instance čítačů zátěžového testu přidružené k testu výkonnosti webu jsou obsaženy v rámci větve test webového výkonu. V tomto uzlu všechny čítače nezátěžových transakce přidružit transakce jsou zde uvedené pojmenované Transaction1 testu výkonnosti webu IBuyBrowse v Scenraio1 zátěžového testu.<br />9. Listové uzly pod uzlem transakce se načíst testovací transakce čítače.<br />10. Uzel testu jednotek.|

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-|-----------------------|
|**Přidání více čítačů výkonu do grafu v zobrazení grafu:** v **čítače** panelu, můžete přidat různé druhy dat do grafu zátěžového testu přidáním dalších čítačů výkonu v grafu.|-   [Postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)|
|**Analýza mezních hodnot zadaných v zátěžovém testu, které byly překročeny:** **čítače** panel zobrazuje ikony reprezentující překročení mezních hodnot, které poté můžete přidat do tabulek a grafů pro další analýzu.|-   [Postupy: Analýza překročení mezních použitím panelu čítačů](../test/analyze-threshold-rule-violations-in-load-tests.md)|
|**Analýza všech chyb, které byly zjištěny během zátěžového testu:** **čítače** panel obsahuje uzel chyb, který obsahuje chyby kategorií a podkategorií, jako je například chyby protokolu HTTP, které můžete použít k přidání chyb do grafů pro Další analýzu.|-   [Postupy: Analýza chyb s použitím panelu čítačů](../test/how-to-analyze-errors-using-the-counters-panel.md)|

## <a name="performance-counter-sampling-interval-considerations"></a>Aspekty Interval vzorkování čítače výkonu

Zvolte hodnotu **vzorkovací frekvence** vlastnost v zátěžovém testu běhu na základě délky zátěžového testu. Menší vzorkovací frekvence, jako je například výchozí hodnota pěti sekund, vyžaduje více místa v databázi výsledků zátěžového testu. Pro delší zátěžové testy vzorkovací frekvence snižuje množství dat, která shromažďujete. Další informace najdete v tématu [postupy: určení vzorkovací frekvence](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Zde jsou uvedeny pokyny pro vzorkovací frekvence:

|Doba trvání zátěžového testu|Doporučená frekvence vzorkování|
|-|-----------------------------|
|\< 1 hodina|5 sekund|
|1 - 8 hodin|15 sekund|
|8 - 24 hodin|30 sekund|
|> 24 hodin|60 sekund|

## <a name="considerations-for-including-timing-details-to-collect-percentile-data"></a>Důležité informace týkající se včetně podrobnosti časování ke shromažďování dat

V nastavení testu v editoru zátěžových testů s názvem existuje vlastnost **úložiště podrobností časování**. Pokud **úložiště podrobností časování** vlastnost je povolená, pak čas ke spuštění každé jednotlivé testy, transakce a stránky během zátěžového testu je uložen v úložišti výsledků zátěžového testu. To umožňuje zobrazení dat 90. a 95. percentilu v Analyzéru zátěžového testu v tabulkách testy, transakce a stránky.

Existují dvě volby pro povolení **úložiště podrobností časování** vlastnost vlastností parametrů spuštění: **StatisticsOnly** a **AllIndividualDetails**. Obě možnosti všechny individuální testy, stránky a transakce jsou časovány a data percentilu se vypočtou z jednotlivých dat časování. Rozdíl je, že u **StatisticsOnly** ihned poté, co byla vypočtena data pro percentil, možnost jednotlivá časová data odstraněna z úložiště. To snižuje množství místa potřebné v úložišti použijete podrobnosti časování. Pokročilí uživatelé mohou však chtít zpracovat podrobná data časování jiným způsobem, pomocí nástroje SQL. Pokud tomu tak, **AllIndividualDetails** by měl být použit, tak, aby podrobná data časování byla k dispozici pro zpracování. Navíc pokud nastavíte vlastnost na **AllIndividualDetails**, pak lze analyzovat aktivity virtuálního uživatele pomocí **aktivity virtuálního uživatele** grafu v Analyzéru zátěžového testu po zátěžový test Konec běhu. Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

Množství místa potřebné v úložišti výsledků zátěžového testu k ukládání dat s podrobnosti časování může být velký, zejména pro delší zkoušky zatížení. Také čas pro ukládání těchto dat v úložišti výsledků zátěžového testu na konci zátěžového testu je delší, protože tato data jsou uložena v agentech zátěžového testu, dokud zátěžový test neskončí. Po dokončení zátěžového testu jsou data uložena do úložiště. Ve výchozím nastavení **úložiště podrobností časování** je povolena vlastnost. Pokud je to problém pro testovací prostředí, můžete chtít nastavit **úložiště podrobností časování** k **žádný**.

Další informace najdete v tématu [postupy: určení vlastnosti úložiště podrobností časování](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)