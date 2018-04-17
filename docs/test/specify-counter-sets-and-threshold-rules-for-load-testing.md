---
title: Čítač sady a mezních pravidel pro zatížení testování v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- counters, counter sets
- load tests, thresholds
- counter sets
- load tests, performance
- load tests, counter sets
- load tests, threshold rules
ms.assetid: 9e14d955-f3a4-4717-bbfe-7f08cdda5678
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: d2b80ab1aaed9f5f59399a02026c9334f38701c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="specify-counter-sets-and-threshold-rules-for-computers-in-a-load-test"></a>Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu

Zátěžové testy zadat sady s názvem čítačů, které jsou užitečné při analýze dat čítačů výkonu. Sady čítačů jsou uspořádané podle technologie a zahrnují aplikace, ASP.NET, aplikace .NET, služby IIS a SQL. Když vytvoříte zátěžový test pomocí **načíst testování Průvodce novým**, přidáte počáteční sadu čítačů. Tyto nabízí sadu předdefinovaných a důležité čítače sady pro zátěžový test. Spravovat vaše čítače v **editoru zátěžových testů**.

> [!NOTE]
> Pokud jsou zátěžové testy distribuovány napříč vzdálenými počítači, jsou čítače kontroléru a agentů namapovány na sady čítačů kontrolérů a agentů. Další informace o tom, jak používat vzdáleného počítače v zátěžovém testu najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

Sady čítačů jsou shromážděná na počítačích, zda jste zadali. Přidružení mezi sady čítačů a počítač, který se používá během zátěžového testu je *sada čítačů mapy*. Například webový server, který zkoušíte může mít ASP.NET, služby IIS, a mapování sady čítačů aplikace .NET.

Ve výchozím nastavení jsou čítače výkonu shromažďují na kontroléru a agentů. Další informace najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

Je důležité, přidat servery testovaného do seznamu počítačů, na které se mají shromažďovat čítače. Potom všechny důležité systém data jsou shromažďována a monitorovat během zátěžového testu.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Správa sad čítačů pro zátěžový test:** poté, co vytvoříte zátěžový test, můžete upravit sady čítačů v editoru načíst testování. Správa sad čítačů zahrnuje výběr sadu počítačů, z nichž chcete shromažďovat data o výkonu a přiřazení sadu sad čítačů ke shromažďování z jednotlivých počítačů. Můžete spravovat vaše čítače v editoru zátěžových testů.|-   [Postupy: Správa sad čítačů](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)|
|**Přidat čítač nastaví zátěžového testu:** při načtení testování Průvodce novým vytvoříte zátěžový test, můžete přidat počáteční sadu čítačů. Ty nabízejí sadu předdefinovaných sad čítačů pro zátěžové testy. Jakmile vytvoříte zátěžový test, můžete přidat nové čítače do existujících sad čítačů pomocí editoru načíst otestovat.|-   [Postupy: přidání čítačů do sad čítačů](../test/how-to-add-counters-to-counter-sets-using-the-load-test-editor.md)<br />-   [Postupy: Přidání vlastních sad čítačů](../test/how-to-add-custom-counter-sets-using-the-load-test-editor.md)|
|**Zadejte prahovou hodnotu pravidlo pro zátěžový test pomocí čítačů:** mezního pravidla je pravidlo, které jsou nastavené v čítače výkonu jednotlivých monitorování využití systémových prostředků během zátěžového testu. Definice sady čítač obsahují předdefinované mezních pravidel pro mnoho klíčových čítačů výkonu. Mezní pravidla v zátěžových testech porovnávají hodnotu čítače výkonu s konstantní hodnotou nebo jinou hodnotou čítače výkonu.|-   [Postupy: Přidání mezního pravidla](../test/how-to-add-a-threshold-rule-using-the-load-test-editor.md)|
|**Do počítačů, na které čítače jsou namapované sady přiřadit popisné názvy:** můžete přidat značky počítače, které vám umožní použít popisným názvem do počítače. Zadané značky jsou zobrazeny v **čítač nastavit mapování** uzel pro strom v editoru zátěžových testů. Důležitější, značky se zobrazí v sestavách aplikace Excel, které pomáhají identifikovat jakou roli zúčastněným stranám má počítač v zátěžový test, například "Web Server1 v lab2" nebo "Server2 SQL v Phoenix office".<br /><br /> Další informace najdete v tématu [Reporting výsledků zátěžových testů pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).|-   [Postupy: Přidání značek počítače do čítač mapování sad](../test/how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor.md)|

## <a name="use-counter-sets"></a>Použití sad čítačů

Testovací nástroje zatížení shromažďovat a graf údaje o výkonu pomocí čítačů v čase. Čítač data jsou shromažďována v intervalech zadán uživatel během spuštění zátěžového testu. Další informace najdete v tématu [postupy: určení vzorkovací frekvence](../test/how-to-specify-the-sample-rate-for-a-load-test.md). Čítače můžete zobrazit v době běhu nebo je lze zobrazit po zátěžový test pomocí spustíte *načíst testování analyzátor*.

Čítač shromáždění dat na serveru a na každém počítači kde spuštění testu. Pokud jste nastavili skupinu počítačů agenta, na který se má spustit testy, čítače jsou také shromážděná v těchto počítačích.

Existují tři kategorie čítače: procent, počty a průměry. Některé příklady jsou % využití procesoru, počtu uzamčení systému SQL Server a služby IIS požadavků za sekundu.

![Načtení sady čítačů testovací](../test/media/loadtestcountersets.png "LoadTestCounterSets")

Údaje o výkonu pro jednotlivé požadavky HTTP je hlášen počítači, který spouští test. například počítači agenta. Pro žádosti může sledovat data, jako jsou Průměrná doba do prvního bajtu, doba odezvy a počet požadavků za sekundu.

K usnadnění kolekce dat výkonu na webový server, Visual Studio Enterprise taky poskytuje sady předdefinovaných, s názvem čítačů, založené na technologii pro použití v zátěžových testech. Tyto sady jsou užitečné při analýze server, který běží služby IIS, ASP.NET nebo SQL Server. Není zadaný v sadě výchozí čítače čítače lze přidat pomocí editoru zátěžových testů. Je důležité, přidat počítače nebo servery testovaného do vaší zátěžový test, abyste měli jistotu, že můžete monitorovat využití prostředků v těchto počítačích. Další informace najdete v tématu [postupy: Správa sad čítačů](../test/how-to-manage-counter-sets-using-the-load-test-editor.md).

Výsledky analýzy zatížení spustí často vyžaduje znalosti specifické pro doménu konkrétní oblasti vědět, jaká data shromažďovat, kde k sady mezních pravidel a jak zjistit, kdy měření odráží určitý problém v aplikaci. Další informace najdete v tématu [mezních pravidel](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md#SpecifyingCounterSetsThresholdRulesAboutThresholdRules).

### <a name="performance-counter-sampling-interval-considerations"></a>Aspekty Interval vzorkování čítače výkonu

Vyberte hodnotu odpovídající **vzorkovací frekvence** vlastnost v zátěžovém testu spusťte nastavení na základě délky zátěžový test. Menší vzorkovací frekvence, jako je například na výchozí hodnotu pět sekund, vyžaduje více místa v databázi výsledky testu zatížení. Pro delší zátěžové testy zvýšení vzorkovací frekvence sníží množství dat shromažďovaných. Další informace najdete v tématu [postupy: určení vzorkovací frekvence](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Následující části jsou uvedeny pokyny pro vzorkovací frekvence.

|Doba trvání testu zatížení|Doporučené vzorkovací frekvence|
|------------------------|-----------------------------|
|\< 1 hodina|5 sekund|
|1−8 hodin|15 sekund|
|8−24 hodin|30 sekund|
|> 24 hodin|60 sekund|

## <a name="store-performance-data"></a>Ukládání dat výkonu

Během spuštění zátěžového testu, se data čítače výkonu shromážděných a uložených v *zatížení úložiště výsledků testů*. Další informace najdete v tématu [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md).

## <a name="about-threshold-rules"></a>O pravidlech prahová hodnota

A *mezního pravidla* je pravidlo, které jsou nastavené v čítače výkonu jednotlivých monitorování využití systémových prostředků během zátěžového testu. Definice sady čítač obsahují předdefinované mezních pravidel pro mnoho klíčových čítačů výkonu. Další informace najdete v tématu [pomocí sad čítačů pro pomáhají analyzovat Data čítače výkonu v zátěžových testech](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

## <a name="threshold-rules-and-levels"></a>Pravidla mezních hodnot a úrovně

Vytváříte-li v zátěžových testech mezních pravidel, můžete si vybrat mezi dvěma typy pravidel:

Porovnání konstanta&mdash;porovnat hodnotu počítadla výkonu s konstantní hodnotou.

Porovnání čítače&mdash;porovnání hodnota čítače výkonu s jinou hodnotou čítače výkonu.

Když vytvoříte mezních pravidel, můžete také nastavit úrovně pro pravidlo. Úrovně jsou prahovou hodnotu upozornění a kritickou prahovou hodnotu. Při zobrazení zátěžový test spusťte mezních hodnot upozornění úrovně jsou označená žlutou symbol a porušení kritické prahové hodnoty úrovně jsou označeny červenou symbol.

## <a name="the-alert-if-over-property"></a>Výstrahu v případě přes vlastnost

Nastavte **výstrahy Pokud přes** vlastnost **True** k označení, což představuje překročení prahové hodnoty je problém. Například, pokud je prahová hodnota pravidlo nastavené na **% času procesoru**, a vy chcete být upozorněni, pokud hodnota je větší než 90, použijte **porovnat konstantní** typ pravidla, nastavte **kritická prahová hodnota Hodnota** do 90 a nastavte **výstrahy Pokud přes** k **True**.

Nastavte **výstrahy Pokud přes** vlastnost **False** k označení, které spadají pod prahovou hodnotu je problém. Například, pokud je prahová hodnota pravidlo nastavené na **požadavků za sekundu**, a vy chcete být upozorněni, pokud hodnota je menší než 50, použijte **porovnat konstantní** typ pravidla, nastavte **kritickou prahovou hodnotu** do 50 a nastavte **výstrahy Pokud přes** k **False**.

## <a name="see-also"></a>Viz také

- [Postupy: Přidání mezního pravidla](../test/how-to-add-a-threshold-rule-using-the-load-test-editor.md)
- [Analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)