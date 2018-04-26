---
title: Použití legendy zobrazení grafů k analýze zátěžových testů v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Load Test Analyzer, graphs view legend
- load tests, graphs view legend
ms.assetid: 0f6ba8e4-1343-419c-8a9f-240cf50efed7
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 55d38dcb87081ea7fc0b16d7d500d13e72f77269
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="using-the-graphs-view-legend-to-analyze-load-tests"></a>Použití legendy zobrazení grafů k analýze zátěžových testů

Zobrazení grafů Analyzéru zátěžového testu obsahuje panel legendy, jenž zobrazuje informace pro každý čítač výkonu, který je přidružen k aktuálně vybranému grafu.

![Legenda zobrazení grafů](../test/media/load_viewlegend.png "Load_ViewLegend")

Legenda obsahuje následující informace:

-   **Zobrazit v grafu:** pomocí zaškrtávacích políček k určení zda řádek pro konkrétní čítač, jako například **zatížení uživatele** nebo **chyby/s**, se vykreslí v grafu. Vyberte zaškrtávací políčko, pokud chcete na řádku bude zobrazena v grafu. Zrušte zaškrtnutí políčka k odebrání řádku vykreslení grafu. I po odstranění čáry grafu zůstane statistika čítače nadále zobrazena v legendě.

-   **Rozsah:** v tomto sloupci se zobrazuje rozsah osy y čítač výkonu. Ve výchozím nastavení tato hodnota automaticky upraví jako řadu ukázková data změny. Automaticky upravený rozsah bude vždy o další mocninu desíti větší než maximální hodnota, včetně záporných mocnin desíti. Graf může obsahovat mnoho různých čítačů, z nichž každý má jiný rozsah. Osa y tedy není popsána žádným konkrétním rozsahem. Namísto toho je popsána hodnotami 0 až 100 představujícími procento celkového rozsahu každého čítače. Například pro čítač s rozsahem 1000 by datový bod 60 na ose y odpovídal hodnotě čítače 600.

    > [!NOTE]
    > Úpravy hodnot automatického rozsahu můžete vypnout blokováním rozsahu na určitou hodnotu. Je-li rozsah uzamčen, jsou všechny hodnoty přesahující tento rozsah zobrazeny jako maximální hodnota zadaná v horní části grafu. Použití **vykreslení možnosti** dialogové okno se uzamknout rozsahu na určitou hodnotu. Další informace najdete v tématu [postup: Zadejte možnosti pro vytváření grafů čítače vykreslení](../test/how-to-specify-plot-options-for-graphing-counters.md).

-   **Čítač:** čtyři sloupce s názvem **čítač**, **Instance**, **kategorie**, a **počítače** společně jednoznačně Identifikujte čítače výkonu.

-   **Barva:** **barva** sloupci se zobrazuje barvy a řádku styl čáry možná vykreslená pro čítač výkonu. Použití **vykreslení možnosti** dialogové okno změnit barvu nebo řádku styl čítače výkonu v grafu. **Vykreslení možnosti** dialogové okno je k dispozici z místní nabídky legendě. Další informace najdete v tématu [postup: Zadejte možnosti pro vytváření grafů čítače vykreslení](../test/how-to-specify-plot-options-for-graphing-counters.md).

-   **Statistiky:** **Min**, **maximální**, **průměr** a **poslední** sloupcích se zobrazují odpovídající statistické údaje o výkonu Čítač. Tyto hodnoty odpovídají data, která se zobrazí na viditelné oblasti grafu. Pokud například přiblížíte zobrazení na nějakou oblast běhu, statistika legendy bude odpovídat hodnotám platným pouze pro přiblíženou oblast. "Posledního" sloupce je hodnota čítače výkonu v nedávno provedených intervalu vzorkování.

    > [!NOTE]
    > Sloupec Poslední se zobrazí v legendě Analyzéru zátěžového testu pouze za běhu zátěžového testu.

     Další informace najdete v tématu [postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

Výběr položky v legendě provede následující:

-   Umožňuje položka, která má být odebráni ze legendu a grafu. Buď klikněte pravým tlačítkem položku a vyberte **odstranit**, nebo stiskněte klávesu **odstranit** klíč.

-   Označuje možná vykreslená řádku v grafu.

-   Způsobí, že mřížky data k zobrazení dat pro vybranou položku.

-   Umožňuje přístup **vykreslení možnosti** dialogové okno pro čítač.

> [!TIP]
> Můžete použít **rozevírací seznam možnosti grafu** tlačítka na panelu nástrojů a vyberte Analyzéru zátěžového testu **zobrazit legendu** zobrazit nebo skrýt **legendy** panel, který je spojen s zobrazení grafu.

## <a name="see-also"></a>Viz také

- [Postupy: určení možností grafu pro čítače grafů](../test/how-to-specify-plot-options-for-graphing-counters.md)
- [Postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)
- [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)