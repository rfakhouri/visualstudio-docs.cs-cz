---
title: Panel čítačů pro analýza zátěžových testů v sadě Visual Studio
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
ms.openlocfilehash: fd87cdb912b7e2dcf13476bab610935db5ca4fd7
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36304778"
---
# <a name="use-the-counters-panel-in-graphs-view-and-tables-view"></a>Použití panelu čítačů v zobrazení grafů a tabulek zobrazení

**Čítače** panel je viditelné v zobrazení grafů a tabulek zobrazení v analyzátoru načíst testování běhu zátěžového testu nebo při analýze výsledků testů zatížení. Další informace najdete v tématu [výsledky testu zatížení analyzovat v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md), [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) a [postupy: přístup k analýzevýsledkůzátěžovéhotestu](../test/how-to-access-load-test-results-for-analysis.md).

**Čítače** panelu zobrazí strukturovaných zobrazení všech čítačů výkonu, které byly shromážděny během zátěžového testu. Můžete zobrazit nebo skrýt **čítače** panely tak, že zvolíte **zobrazit Panel čítačů** na **Analyzéru zátěžového testu** panelu nástrojů.

Čítače jsou uspořádány do stromové struktury, kde uzlů listu jsou instance čítače výkonu, které může být proto vytvořen.

Panel čítačů poskytuje následující funkce:

-   Komunikuje informace porušení prahové hodnoty.

-   Výběr čítače pro vytváření grafů.

-   Strukturované stromovou strukturu všech čítačů výkonu shromážděných během zátěžového testu spusťte s následující primární větve:

    -   **Celkové:** obsahuje souhrn data čítače výkonu pro každého agenta test a pro celý zátěžový test.

    -   **Název scénáře:** větví označený verzí zatížení testovací scénář názvy ve stromu čítače výkonu obsahovat všechny zatížení testovací čítač instance přidružené scénáře konkrétní zátěžového testu. Většina čítačů testu zatížení jsou vnořené ve scénáři větev.

         Scénář větve obsahuje webové výkonu testovací uzly. Obsahovat uzly test výkonu webové stránky, požadavky a transakce uzly. Libovolný uzel typu list v této struktuře je čítačů výkonu, které lze přidat do grafu.

    -   **Počítače:** obsahuje všechny instance čítače bez zátěžový test seskupené podle počítače. Větví počítače obsahuje uzel pro každý počítač, který je spojena s řadičem testu zatížení zadaná v části role aktuálně vybrané testovací nastavení. Další informace najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

         Každý uzel počítače obsahuje sadu kategorie čítače výkonu shromážděné z tohoto počítače. Kategorie obsahovat čítače a čítače obsahovat názvy instancí čítače výkonu.

    -   **Chyby:** obsahuje všechny chyb zjištěných během zátěžového testu. Uzel chyby obsahuje několik uzlů chyba podkategorie. Podkategorie jsou specifické pro různé druhy chyb, například výjimek a chyb protokolu HTTP.

### <a name="scenario-name-node-in-counters-panel"></a>Název uzlu scénář panelu čítačů

|Panel čítačů|Popis|
|-|-|
|![Čítač panelu scénář název uzlu](../test/media/ltest__namenode.png)|1. V rámci tohoto uzlu se zobrazují všechny čítače výkonu související s Scenario1 zátěžový test.<br />2. Všechny testy scénáře jsou umístěny pod jeho uzlem. Popisek označuje název testu.<br />3. Uzlů listu uzlu testovací jsou čítače testovacího případu testu zatížení, kde je název instance čítače název testu.<br />4. Všechny načtení testovací stránka čítač instance přidružené větev test výkonu webové. V tomto uzlu jsou zde uvedené zátěžového testu se stimulací podle instance čítače, které jsou přidružené stránku přihlášení získat (název Reporting) testu výkonnosti webu IBuyBrowse v Scenario1 zátěžový test.<br />5. Testovací stránka čítače jsou načíst uzlů listu uzlu stránky.<br />6. Čítač Požadavky test, který instance přidružené k testu výkonnosti webu jsou obsaženy v větev test výkonu webové se všechny načíst. V tomto uzlu všechna žádosti instance čítače, které jsou přidružené k žádosti přihlášení získat testu výkonnosti webu IBuyBrowse v Scenario1 o zátěžový test součástí zde (název Reporting).<br />7. Uzlů listu uzlu žádosti jsou načíst testovací žádost čítače.<br />8. Všechny zatížení testovací transakce čítač instance přidružené k testu výkonnosti webu jsou obsaženy v větev test výkonu Web. V tomto uzlu všechny instance čítače transakce přidružit transakce s názvem Transaction1 testu výkonnosti webu IBuyBrowse v Scenraio1 zátěžového testu jsou obsažené v tomto poli.<br />9. Uzlů listu uzlu transakce jsou načíst testovací transakce čítače.<br />10. Uzel test jednotky.|

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Přidat další čítače výkonu do grafu v zobrazení grafu:** v **čítače** panelu, můžete přidat různé druhy dat do grafu testu zatížení přidáním další čítače výkonu v grafu.|-   [Postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)|
|**Analýza prahy jste zadali v zátěžovém testu, které byla porušena:** **čítače** panelu zobrazí ikony představující překročení mezních hodnot, které poté můžete přidat do tabulky a grafy pro další analýzu.|-   [Postupy: Analýza překročení mezních hodnot s použitím panelu čítačů](../test/analyze-threshold-rule-violations-in-load-tests.md)|
|**Analýza všechny chyby, které byly zjištěny během spuštění zátěžového testu:** **čítače** panel zahrnuje k chyby uzlu, který obsahuje chyby kategorií a podkategorií například chyby protokolu HTTP, které můžete použít k přidání chyb do grafy pro další analýze.|-   [Postupy: Analýza chyb s použitím panelu čítačů](../test/how-to-analyze-errors-using-the-counters-panel.md)|

## <a name="performance-counter-sampling-interval-considerations"></a>Aspekty Interval vzorkování čítače výkonu

Vyberte hodnotu pro **vzorkovací frekvence** vlastnost v zátěžovém testu spusťte nastavení na základě délky zátěžový test. Menší vzorkovací frekvence, jako je například na výchozí hodnotu pět sekund, vyžaduje více místa v databázi výsledky testu zatížení. Pro delší zátěžové testy zvýšení vzorkovací frekvence sníží množství dat, které shromažďujete. Další informace najdete v tématu [postupy: určení vzorkovací frekvence](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Zde jsou uvedeny pokyny pro vzorkovací frekvence:

|Doba trvání testu zatížení|Doporučená vzorkovací frekvence|
|------------------------|-----------------------------|
|\< 1 hodina|5 sekund|
|1 - 8 hodin|15 sekund|
|8 – 24 hodin|30 sekund|
|> 24 hodin|60 sekund|

## <a name="considerations-for-including-timing-details-to-collect-percentile-data"></a>Důležité informace týkající se včetně podrobností časování pro shromažďování dat percentilu

V nastavení spuštění v editoru zátěžových testů s názvem je vlastnost **úložiště podrobností časování**. Pokud **úložiště podrobností časování** je povolena vlastnost a potom čas spuštění každé jednotlivé testy, transakce a stránku během zátěžového testu je uložen v úložiště výsledků zátěžového testu. To umožňuje data 90 a 95. percentil zobrazený v Analyzéru zátěžového testu v tabulkách testy, transakce a stránky.

Existují dvě možnosti pro povolení **úložiště podrobností časování** vlastnost vlastností parametrů běhu: **StatisticsOnly** a **AllIndividualDetails**. U obou možností jednotlivých testů, stránky a transakce jsou vypršel časový limit a percentilu dat se počítá z dat jednotlivých časování. Rozdíl je, že se **StatisticsOnly** také data percentilu je vypočítána, možnost jednotlivých načasování data se odstraní z úložiště. Tím se snižuje množství volné místo v úložišti použijete časování podrobnosti. Pokročilí uživatelé však chtít ke zpracování dat podrobností časování jinými způsoby, pomocí nástrojů SQL. Pokud ano, **AllIndividualDetails** by měl být použit, aby byla dostupná pro toto zpracování podrobných dat časování. Kromě toho pokud nastavíte vlastnost na **AllIndividualDetails**, pak můžete analyzovat aktivity virtuálního uživatele pomocí **aktivity virtuálních uživatelů** grafu v nástroje načíst testování Analyzer po zátěžového testu Konec běhu. Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

Množství místa, která je vyžadována ve úložiště výsledků zátěžového testu pro ukládání dat časování podrobnosti může být velký, zejména pro již spouštění zátěžových testů. Čas potřebný k uložení dat této v úložiště výsledků zátěžového testu na konci zátěžového testu je také déle, protože tato data jsou ukládána v testovacích agentů zatížení, dokud zátěžového testu dokončil provádění. Po dokončení zátěžový test, jsou data uložena do úložiště. Ve výchozím nastavení **úložiště podrobností časování** vlastnost povolena. Pokud je problém pro testovací prostředí, můžete chtít nastavit **úložiště podrobností časování** k **žádné**.

Další informace najdete v tématu [postupy: určení vlastnosti úložiště podrobností časování](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)