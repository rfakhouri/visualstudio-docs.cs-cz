---
title: "Analýza výsledků zátěžových testů v zobrazení grafů Analyzéru zátěžového testu | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
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
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 5087415c22d9fa772dbe4d2a742ac369b44149ed
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="analyze-load-test-results-in-the-graphs-view-of-the-load-test-analyzer"></a>Analýza výsledků zátěžových testů v zobrazení grafů Analyzéru zátěžového testu

Výsledky zátěžového testu se zobrazují jako data v několika různých podoken.

Chcete-li zobrazit výsledky testů jako grafy, zvolte **grafy** na panelu nástrojů testu zatížení. Každé jednotlivé grafu se zobrazí panelu s názvem grafu zobrazí v horní v rozevíracím seznamu. Do jiného grafu se zobrazí v panelu, vyberte ze seznamu název jiného grafu.

Až čtyři grafu panelů lze zobrazit najednou. Můžete přepínat mezi různé panely rozložení pomocí tlačítka panelu nástrojů panely rozložení.

Jsou k dispozici několik předdefinovaných grafy. Můžete použít integrované grafů, jako je nebo je můžete přizpůsobit. Kromě toho můžete vytvořit vlastní grafy. Další informace najdete v tématu [postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md) a [postupy: vytvoření vlastní grafy](../test/how-to-create-custom-graphs-in-load-test-results.md).

## <a name="built-in-graphs"></a>Předdefinované grafy

Následující tabulka uvádí předdefinované grafy, které jsou k dispozici pro Analýza výsledků zátěžových testů.

|Název grafu|Popis|
|----------------|-----------------|
|Klíčové ukazatele|Čítače, které popisují základní aspekty testování výkonu například čas zatížení, propustnosti a odpověď uživatele.|
|Doba odezvy pro test|Data o množství času testy provést, aby spustil.|
|Doba odezvy stránky|Průměrná doba odezvy pro webové stránky, které jsou přístupné během zátěžového testu.|
|Systém za testu|Informace o počítačích, na kterých aplikace testuje spustí. To zahrnuje data o využití paměti, procesor fyzického disku, procesy.<br /><br /> Ve výchozím nastavení se shromažďují pouze čítače Počet MB k dispozici a času procesoru.|
|Kontroléru a agentů|Informace o počítačích, na kterých zátěžové testy spustit. To zahrnuje data o využití paměti, procesor fyzického disku, procesy.<br /><br /> Ve výchozím nastavení pouze počet MB k dispozici a jsou shromažďovány čítače času procesoru.|
|Doba odezvy transakce|Průměrná doba odezvy pro transakce, ke kterým došlo během zátěžového testu.|

 Různé čítače lze zobrazit v grafu v době běhu a po spuštění testu.

> [!NOTE]
> Do grafu čas automaticky generovaný odpovědi lze přidat pouze odpovědi čítače výkonu času.

 Informace z čítače zobrazí v grafu i v legendě pod v grafech. Můžete také Přiblížit na oddíl grafu. Další informace najdete v tématu [postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

## <a name="counters-displayed-in-graphs"></a>Zobrazí v grafech čítače

 Grafech zobrazení *čítače*. Čítače odkazovat na data shromážděná během zátěžového testu, jako je například testy za sekundu nebo Průměrná testovacího času. Další informace o čítačích najdete v tématu [určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

 Legendu pro čítače, které se zobrazí v grafech obsahuje několik sloupců užitečné dat o spuštění zátěžového testu. Chcete-li vypnout zobrazení všechna data v grafu, zrušte zaškrtnutí políčka v řádku v legendě.

 Legendu obsahuje následující sloupce:

|Čítač|Název čítače|
|-------------|-----------------------------|
|instance|Název instance čítače.|
|Kategorie|Název kategorie čítače.|
|Počítače|Název počítače, do které se shromažďují čítač.|
|Barva|Barva čáry v grafu.|
|Rozsah|Označuje číslo, která je reprezentována 100 na graf pro tento čítač. Například pro rozsah, jehož horní hodnota je 10 000, 100 popisek v horní části grafu představuje 10 000.|
|Min.|Určuje minimální hodnotu pro čítač v milisekundách.|
|Max|Určuje maximální hodnotu pro čítač v milisekundách.|
|průměr|Určuje průměrnou hodnotu pro čítač v milisekundách.|
|poslední|Zobrazí hodnotu čítače během intervalu vzorkování nejnovější v milisekundách.|

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Přizpůsobení v grafech pomocí legendu:** zobrazení grafů legendy zobrazí informace o jednotlivých čítačů výkonu, který je přidružen graf. Legendu můžete použít k odebrání čítače výkonu, zvýrazněte čítače výkonu v grafu a přizpůsobit výkresu možnosti.|-   [Použití legendy zobrazení grafů k analýze zátěžových testů](../test/use-the-graphs-view-legend-to-analyze-load-tests.md)|
|**Zobrazení čítačů pro grafy:** můžete přidat různé druhy dat do testu zatížení výsledků grafu umístěním čítače v grafu.|-   [Postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)|
|**Přiblížení grafy:** po dokončení testu zatížení můžete použít přiblížení řádky přiblížení a přejděte do oblasti grafu. Pomocí zvětšení, můžete zkontrolovat data, která byla vygenerována během zátěžového testu spusťte jemnějšího podrobně.|-   [Postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)|
|**Rozložení grafů vedle sebe:** můžete uspořádat grafy výsledků testu zatížení v některém z několika vzory. Můžete dlaždici až čtyři grafy.||
|**Upravit vzhled pozemků čítače výkonu v grafech:** můžete změnit možnosti výkresu řádků pro čítače výkonu v grafech. To zahrnuje styl barvy a řádku. Kromě toho můžete určit, zda chcete automaticky nebo ručně zadat rozsah, který chcete použít pro vykreslení čítače výkonu.|-   [Postupy: určení možností grafu pro čítače grafů](../test/how-to-specify-plot-options-for-graphing-counters.md)|
|**Vytváření vlastních grafů:** můžete navrhnout grafy zobrazují konkrétní informace o výsledcích zátěžového testu. Navrhnete vlastní graf zadáním čítače testu zatížení, které se zobrazí graf.|-   [Postupy: vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md)|
|**Exportovat data čítače výkonu v tomto grafu:** exportem dat grafu do aplikace Microsoft Excel pomocí Export dat grafu do aplikace Excel na panelu nástrojů Analyzéru zátěžového testu, když jste v zobrazení grafů.||

## <a name="related-tasks"></a>Související úlohy

 [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)

 [Postupy: přístup k výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md)

 [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)

## <a name="see-also"></a>Viz také

- [Postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)
- [Postupy: vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md)
- [Postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)