---
title: Diagram možností pro grafické zobrazení čítačů pro zátěžové testy v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, graphing counters
ms.assetid: 1969c20b-e0eb-48f6-a49f-a9090cd86008
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 5df33a8cf05e4ad73b1643e2948392e49a32356e
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382318"
---
# <a name="how-to-specify-plot-options-for-graphing-counters"></a>Postupy: Zadejte možnosti pro čítače grafů grafu

**Možnosti grafu** dialogové okno umožňuje změnit barvu a styl čáry vykresleného čítače v grafu. Lze také nastavit rozsah na konkrétní hodnotu nebo nastavit to, aby byl rozsah automaticky upraven na základě vzorkovaných dat.

![Zobrazit dialogové okno Možnosti](../test/media/ltest_plotoptions.png)

## <a name="to-specify-plotting-options-for-graphs"></a>Určení možností zobrazování grafů

1.  V **Analyzéru zátěžového testu**, zvolte **grafy** na panelu nástrojů.

     Výsledky zátěžového testu se zobrazí v zobrazení grafu.

2.  V legendě nebo v grafu klikněte pravým tlačítkem na řádek nebo aktuální čáru grafu čítače výkonu, pro kterou chcete změnit možnost zobrazení a potom vyberte **možnosti grafu**.

     **Možnosti grafu** zobrazí dialogové okno.

3.  Použít **barva** rozevíracího seznamu a vyberte barvu, kterou chcete použít pro vykreslení čítače výkonu.

4.  Použít **styl** rozevíracího seznamu a vyberte styl, který chcete použít pro vykreslení čítače výkonu.

5.  Proveďte jednu z těchto akcí:

     Vyberte **automaticky upravit rozsah** (výchozí)

     \- nebo –

     Vymazat **automaticky upravit rozsah** a použít **rozsah** rozevíracího seznamu k určení rozsahu, který chcete použít pro vykreslení čítače výkonu.

6.  Zvolte **OK**.

     Čítač výkonu, pro který jste změnili možnosti, se zobrazí v grafu se změnami, které jste zadali.

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Postupy: vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md)
