---
title: Analýza výsledků zátěžových testů v grafu zobrazení analyzátoru zátěžového testu
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.graph.view
helpviewer_keywords:
- graphs, analyzing load tests
- load tests, graphs in Load Test Viewer
- Load Test Viewer, graphs
- load tests, results graphs
- load tests, using graphs
- load test results, graphs
ms.assetid: 4a919cd8-541c-40ee-be3b-352fabc56140
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8a0c9ca6f195640e3c356e9288300255570b196c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926471"
---
# <a name="analyze-load-test-results-in-the-graphs-view-of-the-load-test-analyzer"></a>Analýza výsledků zátěžových testů v zobrazení grafů analyzátoru zátěžového testu

Výsledky zátěžového testu se zobrazí jako data v několika různých podoknech.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Chcete-li zobrazit výsledky testů jako grafy, klikněte na tlačítko **grafy** na panelu nástrojů **zátěžového testu** . Každý jednotlivý graf se zobrazí na panelu s názvem grafu zobrazeným nahoře v rozevíracím seznamu. Chcete-li zobrazit jiný graf na panelu, v seznamu vyberte jiný název grafu.

Současně lze zobrazit až čtyři panely grafu. Můžete přepínat mezi různými rozloženími panelů pomocí tlačítka panelu nástrojů **rozložení panelu** .

K dispozici je několik integrovaných grafů. Předdefinované grafy můžete použít tak, jak jsou, nebo je můžete přizpůsobit. Navíc můžete vytvořit vlastní grafy. Další informace najdete v tématu [jak: Přidejte a odstraňte čítače v](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md) grafech [a postupy: Vytvořte vlastní grafy](../test/how-to-create-custom-graphs-in-load-test-results.md).

## <a name="built-in-graphs"></a>Předdefinované grafy

V následující tabulce je uveden seznam integrovaných grafů, které jsou k dispozici pro analýzu výsledků zátěžového testu.

|Název grafu|Popis|
|-|-|
|Klíčové ukazatele|Čítače, které popisují základní aspekty testovacího výkonu, jako je například uživatelské zatížení, propustnost a doba odezvy.|
|Doba odezvy testu|Data o množství časových testů, které se mají spustit.|
|Doba odezvy stránky|Průměrná doba odezvy webových stránek, které jsou k dispozici během zátěžového testu.|
|Testovaný systém|Informace o počítačích, ve kterých se aplikace testuje. To zahrnuje data o využití paměti, procesoru, fyzickém disku a procesech.<br /><br /> Ve výchozím nastavení jsou shromažďovány pouze čítače dostupné MB a čas procesoru.|
|Kontrolér a agenti|Informace o počítačích, na kterých běží zátěžové testy. To zahrnuje data o využití paměti, procesoru, fyzickém disku a procesech.<br /><br /> Ve výchozím nastavení se shromažďují jenom dostupné MB a čítače času procesoru.|
|Doba odezvy transakce|Průměrná doba odezvy pro transakce, ke kterým dojde během zátěžového testu.|

V grafu můžete zobrazit různé čítače v době běhu i po spuštění testu.

> [!NOTE]
> Do grafu automaticky generované doby odezvy lze přidat pouze čítače výkonu doby odezvy.

Informace čítače zobrazuje v grafu i v legendě pod grafy. Můžete také přiblížit část grafu. Další informace najdete v tématu [jak: Přiblížení v oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)

## <a name="counters-displayed-in-graphs"></a>Čítače zobrazené v grafech

Grafy zobrazují *čítače*. Čítače odkazují na data získaná během zátěžového testu, například testy za sekundu nebo Průměrná doba testování. Další informace o čítačích naleznete v tématu [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

Legenda k čítačům, které jsou zobrazeny v grafech, zobrazuje několik sloupců užitečných dat o běhu zátěžového testu. Chcete-li zobrazení dat v grafu vypnout, zrušte zaškrtnutí políčka v řádku legendy.

Legenda obsahuje následující sloupce:

|Čítač|Název čítače|
|-|-|
|instance|Název instance čítače.|
|Kategorie|Název kategorie čítače.|
|Computer|Název počítače, do kterého se má čítač shromažďovat|
|Barva|Barva čáry v grafu|
|Rozsah|Označuje číslo reprezentované 100em v grafu pro daný čítač. Například pro rozsah, jehož horní hodnota je 10 000, jmenovka 100 v horní části grafu představuje 10 000.|
|Minimum|Určuje minimální hodnotu čítače v milisekundách.|
|Maximum|Určuje maximální hodnotu čítače v milisekundách.|
|Volání|Určuje průměrnou hodnotu čítače v milisekundách.|
|Poslední|Zobrazuje hodnotu čítače během posledního intervalu vzorkování v milisekundách.|

## <a name="tasks"></a>Úkoly

|Úlohy|Související témata|
|-|-|
|**Přizpůsobte grafy pomocí legendy:** Legenda zobrazení grafů zobrazuje informace pro každý čítač výkonu, který je přidružen k grafu. Pomocí legendy můžete odebrat čítače výkonu, zvýraznit čítače výkonu v grafu a přizpůsobit možnosti vykreslování.|-   [Použití legendy zobrazení grafů k analýze zátěžových testů](../test/use-the-graphs-view-legend-to-analyze-load-tests.md)|
|**Zobrazit čítače v grafech:** Do grafu výsledků zátěžového testu můžete přidat různé druhy dat tak, že do grafu umístíte čítače.|-   [Jak: Přidávání a odstraňování čítačů v grafech](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)|
|**Přiblížit grafy:** Po dokončení zátěžového testu můžete přiblížit a přejděte do oblasti grafu pruhy přiblížení. Podle přiblížit, můžete zkoumat data, která byla vygenerována během spuštění jemnější podrobně zátěžového testu.|-   [Jak: Přiblížení v oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)|
|**Grafy dlaždic:** Grafy výsledků zátěžového testu lze uspořádat v některém z několika vzorů. Můžete uspořádat až čtyři grafy.||
|**Vytvořit vlastní grafy:** Můžete navrhovat grafy, které zobrazí konkrétní informace o výsledcích zátěžového testu. Navrhněte vlastní graf tak, že zadáte počítadla testu zatížení, které se zobrazí grafu.|-   [Jak: Vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md)|
|**Exportujte data čítačů výkonu v grafu:** Data grafu můžete exportovat do aplikace Microsoft Excel pomocí tlačítka **exportovat data grafu do aplikace Excel** na panelu nástrojů **analyzátoru zátěžového testu** , když jste v zobrazení **grafů** .||

## <a name="related-tasks"></a>Související úlohy

[Analýza výsledků zátěžových testů a chyb v zobrazení tabulky](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)

[Postupy: Přístup k výsledkům zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md)

[Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)

## <a name="see-also"></a>Viz také:

- [Postupy: Přidávání a odstraňování čítačů v grafech](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)
- [Postupy: Vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md)
- [Postupy: Přiblížení v oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)