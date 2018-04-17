---
title: Vykreslení možnosti pro vytváření grafů čítače pro zátěžové testy v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, graphing counters
ms.assetid: 1969c20b-e0eb-48f6-a49f-a9090cd86008
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 5c52aefb731fdb1c858819d1c005d27000ad840e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-plot-options-for-graphing-counters"></a>Postupy: Určení možností grafu pro čítače grafů

**Vykreslení možnosti** dialogové okno umožňuje změnit styl barvy a řádku možná vykreslená čítače v grafu. Lze také nastavit rozsah na konkrétní hodnotu nebo nastavit to, aby byl rozsah automaticky upraven na základě vzorkovaných dat.

![Vykreslení dialogovém okně Možnosti](../test/media/ltest_plotoptions.png "LTest_PlotOptions")

## <a name="to-specify-plotting-options-for-graphs"></a>Určení možností zobrazování grafů

1.  V nástroje načíst testování Analyzer, zvolte **grafy** na panelu nástrojů testu zatížení.

     Výsledky zátěžového testu se zobrazí v zobrazení grafů.

2.  V legendě nebo v grafu, klikněte pravým tlačítkem na řádek nebo aktuálního řádku výkresu čítače výkonu, pro kterou chcete změnit výkresu možnost a potom vyberte **vykreslení možnosti**.

     **Vykreslení možnosti** zobrazí dialogové okno.

3.  Použít **barva** rozevíracího seznamu a vyberte barvu, kterou chcete použít pro vykreslení čítače výkonu.

4.  Použít **styl** rozevíracího seznamu a vyberte ten, který chcete použít pro vykreslení čítače výkonu.

5.  Proveďte jednu z těchto akcí:

     Vyberte **automaticky upravit rozsah** (výchozí)

     \- nebo –

     Zrušte **automaticky upravit rozsah** a použít **rozsah** rozevíracího seznamu k určení rozsahu, který chcete použít pro vykreslení čítače výkonu.

6.  Zvolte **OK**.

     Čítač výkonu, pro který jste změnili možnosti, se zobrazí v grafu se změnami, které jste zadali.

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Postupy: vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md)
- [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)