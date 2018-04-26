---
title: Načíst přehled souhrnu výsledků testů v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.summary.view
helpviewer_keywords:
- load test results, summary
- load tests, summary in analyzer
- load tests, results summary
- Load Test Viewer, summary
- load tests, summary in Load Test Viewer
ms.assetid: 326b6c3c-5378-452b-8ca3-ba5a06ab3d41
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 989ebc629e79194fb6cd4c900b032cb93a090977
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="load-test-results-summary-overview"></a>Přehled souhrnu výsledků zátěžového testu

Po spuštění zátěžového testu, můžete zobrazit souhrn testu zatížení rychle pochopit výsledky. Souhrn testu zatížení poskytuje klíče výsledky compact a easy číst formátu. Můžete také vytisknout souhrn testu zatížení. Díky tomu je vhodnější použít při komunikaci výsledky zúčastněným stranám. Souhrn testu zatížení je také výchozí zobrazení při otevření výsledků testů zatížení z dříve spuštění zátěžového testu. Další informace najdete v tématu [postupy: přístup výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md).

 ![Souhrnné zobrazení](../test/media/ltest_summaryview.png "LTest_SummaryView")

## <a name="the-load-test-summary"></a>Souhrn testu zatížení

Souhrn testu zatížení je rozdělen na oddíly. Počáteční části se zobrazí v horní části Shrnutí a jsou vždy viditelné. Při zobrazení souhrnu testu zatížení jsou první následující položky:

- Informace o běhu testu

- Celkové výsledky

- Klíče statistiky: Top 5 nejpomalejší stránky

- Klíče statistiky: Top 5 nejpomalejší testy

- Klíče statistiky: Top 5 nejpomalejší operace SQL

    > [!NOTE]
    > V části operace SQL se zobrazí jenom v případě, že je povolené trasování SQL v zátěžovém testu.

Části ukončovací se zobrazují na konci tohoto přehledu a lze sbalit ušetřit místo. Na konci souhrn testu zatížení se zobrazí následující položky:

- Výsledky testů

- Stránka výsledků

- Výsledky transakce

- V části prostředky testovacího systému

- Řadiče a prostředky agenta

- Chyby

## <a name="test-run-information"></a>Informace o běhu testu

Testovacím běhu informace oddíl obsahuje obecné informace o spuštění, včetně jména testu, spuštění a čas ukončení a kontroler, který byl spuštěn test. Tato část také obsahuje volitelný popis spuštění, které přidáte při spuštění zátěžového testu.

## <a name="overall-results"></a>Celkové výsledky

Celkové výsledky oddíl obsahuje souhrn výsledků testu včetně počet požadavků za sekundu, celkový počet chybných požadavků, Průměrná doba odezvy a čas průměrná stránky.

## <a name="key-statistic-top-5-slowest-pages"></a>Klíče statistiky: Top 5 nejpomalejší stránky

Nejpomalejší stránky obsahuje top 5 nejpomalejší stránky v zátěžovém testu. Adresa URL a čas načítání stránky průměrná se zobrazují pro jednotlivé stránky. Na stránkách jsou uvedeny v sestupném pořadí. Můžete adresu URL stránky otevřete **stránky** tabulky a zkontrolujte další podrobnosti o této stránce. Další informace najdete v tématu [postupy: zobrazení webové stránky odpovědi](../test/how-to-view-web-page-response-time-in-a-load-test.md).

Hodnota percentilu **95 % čas stránky (s)** ohlásit že 95 % stránek dokončit za méně než tuto dobu v sekundách.

## <a name="key-statistic-top-5-slowest-tests"></a>Klíče statistiky: Top 5 nejpomalejší testy

Nejpomalejší testy oddíl obsahuje top 5 nejpomalejší testů v zátěžovém testu. Název testu a průměrná testovacího času jsou zobrazené všechny testy. Testy jsou uvedeny v sestupném pořadí. Název testu otevřete můžete **testy** tabulky a zkontrolujte další podrobnosti o testu. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

Hodnota percentilu **95 % testovací čas (s)** ohlásit že 95 % testů dokončit za méně než tuto dobu v sekundách.

## <a name="key-statistic-top-5-slowest-sql-operations"></a>Klíče statistiky: Top 5 nejpomalejší operace SQL

Pokud je povolené trasování SQL v zátěžovém testu, nejpomalejší dotazy oddíl obsahuje top 5 nejpomalejší dotazy v zátěžovém testu. Zobrazí se název operaci a dobu trvání pro každý test. Doba trvání se zobrazí v mikrosekundách systému SQL Server 2005 nebo v milisekundách (SQL Server 2000 a starší). Testy jsou uvedeny v sestupném pořadí podle doby trvání. Můžete název určité operace, otevřete **trasování SQL** tabulky a zkontrolujte další podrobnosti o této operaci. Další informace najdete v tématu [Table dat trasování SQL](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-sql-trace-data-table).

## <a name="test-results"></a>Výsledky testů

Výsledky testu obsahuje seznam všech testů a scénáře v zátěžovém testu. Zobrazí se název testu, tento scénář, počet, který byl spuštěn, počet, kolikrát se nezdařilo a průměrné testovacího času. Název testu otevřete můžete **testy** tabulky a zkontrolujte další podrobnosti o testu. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

> [!NOTE]
> Můžete sbalit a rozbalením tohoto oddílu tak, že zvolíte na šipku nalevo od názvu oddílu.

## <a name="page-results"></a>Stránka výsledků

Výsledky stránka obsahuje seznam všech webové stránky v zátěžovém testu. Zobrazí se adresa URL, tento scénář, název testu, čas průměrná stránky a počet. Můžete adresu URL stránky otevřete **stránky** tabulky a zkontrolujte další podrobnosti o této stránce. Další informace najdete v tématu [postupy: zobrazení webové stránky odpovědi](../test/how-to-view-web-page-response-time-in-a-load-test.md).

> [!NOTE]
> Můžete sbalit a rozbalením tohoto oddílu tak, že zvolíte na šipku nalevo od názvu oddílu.

## <a name="transaction-results"></a>Výsledky transakce

V části výsledky transakce obsahuje seznam všech transakcí v zátěžovém testu. Zobrazí se název transakce, tento scénář, test, doby odezvy, uplynulý čas a počet. Název transakce. Chcete-li otevřít můžete **transakce** tabulky a zkontrolujte další podrobnosti o této transakce. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

> [!NOTE]
> Můžete sbalit a rozbalením tohoto oddílu tak, že zvolíte na šipku nalevo od názvu oddílu.

Hodnoty percentilu sestav transakce následující informace:

-   90 % celkový počet transakcí, byly dokončeny v menší než \<čas > sekund.

-   95 % celkový počet transakcí, byly dokončeny v menší než \<čas > sekund.

## <a name="system-under-test-resources"></a>V části prostředky testovacího systému

Systém části testovací prostředků obsahuje seznam počítačů, které jsou sadu cílových počítačů, pro které má být vygenerován zatížení. To zahrnuje jakýkoli počítač, ze kterého shromažďovat sad čítačů než agenta nebo Kontroleru. Zobrazí se název počítače, % času procesoru a paměti k dispozici. Můžete otevřít názvu počítače **systému testovaného** graf a zobrazení využití prostředků v průběhu času. Další informace najdete v tématu [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md).

> [!NOTE]
> Můžete sbalit a rozbalením tohoto oddílu tak, že zvolíte na šipku nalevo od názvu oddílu.

## <a name="controller-and-agent-resources"></a>Řadiče a prostředky agenta

V části prostředky řadiče a agent obsahuje seznam počítačů, které se používají ke spuštění testu. Zobrazí se název počítače, % času procesoru a paměti k dispozici. Můžete otevřít názvu počítače **Kontroléru a agentů** graf a zobrazení využití prostředků v průběhu času. Další informace najdete v tématu [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md).

> [!NOTE]
> Můžete sbalit a rozbalením tohoto oddílu tak, že zvolíte na šipku nalevo od názvu oddílu.

## <a name="errors"></a>Chyby

V části chyby obsahuje seznam všech chyb, ke kterým došlo během zátěžového testu. Zobrazí se typ a podtyp chyba, počet a poslední zprávy. Můžete zvolit chybu otevřete **chyby** tabulky a zkontrolujte další podrobnosti o této chybě. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) a [postupy: Analýza chyb s použitím panelu čítačů](../test/how-to-analyze-errors-using-the-counters-panel.md).

> [!NOTE]
> Můžete sbalit a rozbalením tohoto oddílu tak, že zvolíte na šipku nalevo od názvu oddílu.

## <a name="printing-a-summary"></a>Tisk souhrn

Souhrn testu zatížení můžete vytisknout tak, že zvolíte **tisku** v místní nabídce v souhrnu. Náhled tisku první můžete zobrazit výběrem **Náhled** v místní nabídce v souhrnu. Můžete také vytisknout přímo z obrazovky preview.

## <a name="see-also"></a>Viz také

- [Analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)