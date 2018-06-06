---
title: Analýza mezních pravidel v zátěžových testů v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.threshholdresult
helpviewer_keywords:
- load tests, thresholds
- threshold violations
- threshold counts
- load tests, threshold violations
- load test results, analyzing threshold violations
- thresholds in load tests
ms.assetid: 969ed346-cf2e-4d48-82b3-edb3e075e1c0
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 753cf038cf6d8129aa9a4691b0f88c046aadf640
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750906"
---
# <a name="analyzing-threshold-rule-violations-in-load-tests-using-the-load-test-analyzer"></a>Analýza překročení mezních pravidel v zátěžových testech pomocí analyzéru zátěžových testů

Prahová hodnota pravidel jsou přidružena konkrétních čítačích výkonu a narušení naznačují, že čítač výkonu překročil nebo klesl níže nastavte hodnotu. Při spuštění zátěžového testu můžete analyzovat porušení pro pravidla prahovou hodnotu, která jste dřív nastavili.

Pokud došlo k chybě veškerá porušení zásad, **mezních hodnot** hypertextový odkaz se zobrazí na stavovém řádku Analyzéru zátěžového testu a určuje počet porušení zásad, která došlo k chybě. Zvolíte hypertextový odkaz na tabulku porušení prahové hodnoty zobrazení. Můžete také zobrazit mezních hodnot v **čítače** okno a v grafu.

## <a name="view-threshold-violations-in-the-table"></a>Zobrazení mezních hodnot v tabulce

 V tabulce porušení prahové hodnoty zobrazí prvních 1000 porušení zásad. Následující tabulka obsahuje tyto sloupce:

|Sloupec|Popis|Ve výchozím nastavení viditelné|
|------------|-----------------|------------------------|
|Čas|Době zatížení otestujte na kterém došlo k porušení zásady.|Ano|
|Počítače|Název počítače v rámci testu, na kterém došlo k porušení zásady. **Poznámka:** to je důležité při spouštění zátěžových testů na skupin počítačů.|Ano|
|Kategorie|Kategorie čítače výkonu, na kterém došlo k porušení zásady.|Ano|
|Čítač|Název čítače výkonu, na kterém došlo k porušení zásady.|Ano|
|instance|Instance čítače výkonu, na kterém došlo k porušení zásady.|Ano|
|Zpráva|Zpráva, která popisuje porušení prahové hodnoty. Například **hodnotu 5 překročí prahovou hodnotu kritického hodnotu 0**.|Ano|

> [!NOTE]
> V tabulce můžete řadit výběrem záhlaví sloupců.

 Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="view-threshold-violations-in-the-counters-panel"></a>Zobrazení mezních hodnot v panelu čítačů

 Můžete zobrazit mezních hodnot v **čítače** panelu v stromové struktury, která uvádí čítače výkonu pro zátěžový test. Ikony v **čítače** panely komunikovat mezních hodnot. Ikona bude jeden z následujících akcí:

 Ikona bude jeden z následujících akcí:

 ![Žádná porušení prahové hodnoty](../test/media/icon_ltest_1.gif) Žádná porušení prahové hodnoty.

 ![Porušení kritické prahové hodnoty na posledního intervalu](../test/media/icon_ltest_2.gif) Na poslední intervalu, došlo k porušení kritické prahové hodnoty.

 ![Porušení kritické prahové hodnoty na předchozí interval](../test/media/icon_ltest_3.gif) V předchozí intervalu došlo k porušení kritické prahové hodnoty.

 ![Porušení výstražné prahové hodnoty na posledního intervalu](../test/media/icon_ltest_4.gif) Na poslední intervalu, došlo k porušení výstražné prahové hodnoty.

 ![Porušení výstražné prahové hodnoty na předchozí interval](../test/media/icon_ltest_5.gif) V předchozí intervalu došlo k porušení výstražné prahové hodnoty.

 Volitelně mezních hodnot lze zobrazit v grafu také. Ikona prahová hodnota se zobrazí v grafu vedle datového bodu, kde došlo k porušení prahové hodnoty.

 Ve stromu čítač na ikonu porušení prahové hodnoty rozšířena z uzlu konkrétní čítač až do kořenového uzlu. Výstrahy k narušení u čítačů, které nemusí být vidět ve stromu, protože nebyl rozšířila stromu.

 Další informace najdete v tématu [použitím panelu čítačů v zobrazení grafů a tabulek zobrazení](../test/counters-panel-in-load-test-analyzer.md).

## <a name="view-threshold-violations-on-the-graph"></a>Zobrazení mezních v grafu

 Překročení mezních hodnot můžete zobrazit v grafu. Podobně jako **čítače** panelech ikony komunikovat mezních hodnot v grafu. Ikony se zobrazí v grafu vedle datového bodu, kde došlo k porušení prahové hodnoty. Pokud dojde k porušení prahové hodnoty čítače, který se nenachází v grafu, můžete ho přidat do grafu, tak, že přetáhnete z **čítače** panelů do grafu.

 Další informace najdete v tématu [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md).

## <a name="see-also"></a>Viz také:

- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)