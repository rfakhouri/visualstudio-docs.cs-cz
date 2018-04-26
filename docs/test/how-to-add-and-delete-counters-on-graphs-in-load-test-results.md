---
title: Přidání a odstranění čítačů pro grafy ve výsledcích zátěžového testu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load test results graphs, adding counters
- load test results graph
- load test, results graph
- load test results, graphs
ms.assetid: 81536233-1962-40d9-9511-0b4633814d90
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 110aa964c6163f508ba9cd5f26409d0a9912a17e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-and-delete-counters-on-graphs-in-load-test-results"></a>Postupy: Přidání a odstranění čítačů pro grafy ve výsledcích zátěžového testu

Panel čítačů můžete použít k přidání čítačů výkonu do grafu.

 ![Přidání čítačů do grafu](../test/media/ltest_selectcounter.png "LTest_SelectCounter")

 **Aspekty Interval vzorkování čítače výkonu**

 Vyberte hodnotu pro **vzorkovací frekvence** vlastnost v zátěžovém testu spusťte nastavení na základě délky zátěžový test. Menší vzorkovací frekvence, jako je například na výchozí hodnotu pět sekund, vyžaduje více místa v databázi výsledky testu zatížení. Pro delší zátěžové testy zvýšení vzorkovací frekvence sníží množství dat, které shromažďujete. Další informace najdete v tématu [postupy: určení vzorkovací frekvence](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

 Zde jsou uvedeny pokyny pro vzorkovací frekvence:

|Doba trvání testu zatížení|Doporučená vzorkovací frekvence|
|------------------------|-----------------------------|
|\< 1 hodina|5 sekund|
|1 - 8 hodin|15 sekund|
|8 – 24 hodin|30 sekund|
|> 24 hodin|60 sekund|

 **Důležité informace týkající se včetně podrobností časování pro shromáždění dat percentilu**

 V nastavení spuštění v editoru zátěžových testů s názvem je vlastnost **úložiště podrobností časování**. Pokud **úložiště podrobností časování** je povolena vlastnost a potom čas spuštění každé jednotlivé testy, transakce a stránku během zátěžového testu se budou ukládat do úložiště výsledků zátěžového testu. To umožňuje data 90 a 95. percentil zobrazený v Analyzéru zátěžového testu v tabulkách testy, transakce a stránky.

 Existují dvě možnosti pro povolení **úložiště podrobností časování** s názvem vlastnosti v vlastností parametrů běhu **StatisticsOnly** a **AllIndividualDetails**. U obou možností jednotlivých testů, stránky a transakce jsou vypršel časový limit a percentilu dat se počítá z dat jednotlivých časování. Rozdíl je, že se **StatisticsOnly** také data percentilu je vypočítána, možnost jednotlivých načasování data se odstraní z úložiště. Tím se snižuje množství volné místo v úložišti použijete časování podrobnosti. Pokročilí uživatelé však chtít ke zpracování dat podrobností časování jinými způsoby, pomocí nástrojů SQL. Pokud ano, **AllIndividualDetails** by měl být použit, aby byla dostupná pro toto zpracování podrobných dat časování. Kromě toho pokud nastavíte vlastnost na **AllIndividualDetails**, pak můžete analyzovat aktivity virtuálních uživatelů po dokončení spuštění zátěžového testu pomocí grafu aktivity virtuálních uživatelů v analyzátoru načíst otestovat. Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

Množství místa, která je vyžadována ve úložiště výsledků zátěžového testu pro ukládání dat časování podrobnosti může být velký, zejména pro již spouštění zátěžových testů. Čas potřebný k uložení dat této v úložiště výsledků zátěžového testu na konci zátěžového testu je také déle, protože tato data jsou ukládána v testovacích agentů zatížení, dokud zátěžového testu dokončil provádění. Po dokončení zátěžový test, jsou data uložena do úložiště. Ve výchozím nastavení **úložiště podrobností časování** vlastnost povolena. Pokud je problém pro testovací prostředí, můžete chtít nastavit **úložiště podrobností časování** k **žádné**.

Další informace najdete v tématu [postupy: určení vlastnosti úložiště podrobností časování](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).

## <a name="to-display-a-particular-performance-counter-on-a-load-test-graph"></a>Chcete-li zobrazit konkrétního čítače výkonu na graf testu zatížení

1.  Po dokončení testu zatížení, nebo po načtení výsledků testů, v panelu nástrojů nástroje načíst testování Analyzer společnosti, zvolte **grafy**.

     **Čítače** panelu se zobrazí v zobrazení grafů.

    > [!NOTE]
    > Pokud není viditelná panelu čítačů, zvolte **zobrazit Panel čítačů** na panelu nástrojů.

2.  V panelu čítačů rozbalte uzly v hierarchii, vyhledejte čítače výkonu, který chcete zobrazit graficky zobrazit.

     Například pokud chcete zobrazit dostupné paměti v počítači se spuštěným testy, rozbalte položku **počítače**, rozbalte uzel pro počítač a potom rozbalte **paměti**. Zobrazí se **počet MB k dispozici** čítače.

3.  Vyberte graf, na kterém chcete zobrazit čítače výkonu.

4.  Čítač výkonu v klikněte pravým tlačítkem myši **čítače** panelu a vyberte **zobrazit čítače v grafu**.

    > [!TIP]
    > Chcete-li dočasně pozastavit zobrazení data čítače výkonu v grafu, zrušte zaškrtnutí políčka pro čítač výkonu v legendě. To umožňuje statistiky min, max a průměr bude stále analyzovaný bez zobrazení trendovou linii na graf. To může být užitečné, pokud graf obsahuje několik překrývající se pozemků čítače výkonu, při analýze problémy. Další informace najdete v tématu [použití legendy zobrazení grafů k analýze zátěžových testů](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

5.  Chcete-li odebrat data čítače výkonu z grafu, klikněte pravým tlačítkem čítače výkonu v **čítač** sloupce legendy a vyberte **odstranit**.

     \- nebo –

     Klikněte pravým tlačítkem na řádek dat v grafu a vyberte **odstranit**.

     \- nebo –

     Vyberte čítač výkonu v **čítač** sloupce legendy nebo data v grafu a stisknete klávesu **odstranit** klíč.

    > [!NOTE]
    > Můžete také umístit čítače výkonu v legendě, ale nejsou v grafu pomocí **přidat čítače v legendě** příkaz.

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Postupy: vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md)