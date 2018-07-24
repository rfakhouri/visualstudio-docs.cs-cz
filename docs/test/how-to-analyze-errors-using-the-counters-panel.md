---
title: Analýza zátěžového testu chyb s použitím panelu čítačů v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Load Test Analyzer, counters panel
ms.assetid: 981b4f1e-505a-4078-a06d-58ae17d996b4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e7ccd21e5432003de7ec3b03bf94716802846bd4
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204333"
---
# <a name="how-to-analyze-errors-using-the-counters-panel"></a>Postupy: Analýza chyb s použitím panelu čítačů

**Čítače** panel je zobrazen v zobrazení grafů a zobrazení tabulek v **Analyzéru zátěžového testu** během zátěžového testu nebo během analýzy výsledku zátěžového testu. Další informace najdete v tématu [výsledků zátěžového testu analyzovat v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md), [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) a [postupy: přístup k analýzevýsledkyzátěžovéhotestu](../test/how-to-access-load-test-results-for-analysis.md).

 **Chyby** uzlu **čítače** panel obsahuje všechny chyby, které byly zjištěny během zátěžového testu. **Chyby** uzel obsahuje několik uzlů podkategorie chyb, které jsou specifické pro různé druhy chyb. Například **výjimky** a **chyby protokolu HTTP**.

 ![Uzel chyby na panelu čítačů](../test/media/ltest_errornode.png)

## <a name="to-analyze-errors-in-the-counters-panel"></a>Analyzovat chyby na panelu čítačů

1.  Po dokončení zátěžového testu nebo po načtení výsledků testu v Analyzéru zátěžového testu na panelu nástrojů, zvolte buď **grafy** nebo **tabulky**.

     **Čítače** panelu se zobrazí v zobrazení grafů nebo v zobrazení tabulek.

2.  Pokud **čítače** panelu není zobrazen, zvolte **zobrazit Panel čítačů** na panelu nástrojů.

3.  Rozbalte **chyby** a vyberte kategorii chyby nebo dílčí kategorie chyby, který chcete analyzovat.

4.  Klikněte pravým tlačítkem na chybu a vyberte jednu z následujících možností:

    -   **Zobrazit čítač v grafu**: V zobrazení grafů chyba přidán a zvýrazněn ve vybraném grafu. Další informace najdete v tématu [postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

    -   **Zobrazit čítač v legendě**: Chyba přidán a vybrán v legendě. Další informace najdete v tématu [použití legendy zobrazení grafů k analýze zátěžových testů](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Přidat graf**:

    1.  **Zadejte název grafu** se zobrazí dialogové okno.

    2.  V **název grafu** textového pole zadejte název pro nový graf a zvolte **OK**.

    3.  (Volitelné) Klikněte pravým tlačítkem na chybu znovu a vyberte **zobrazit čítač v grafu**.

         Další informace najdete v tématu [postupy: vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (Volitelné) Pokud analyzujete chybu ve výsledku dokončeného zátěžového testu, zvažte použití funkcí přiblížení v grafu. Další informace najdete v tématu [postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Pokud při spuštění zátěžového testu nebyly zjištěny žádné chyby, odkaz s názvem chyb včetně jich bude k dispozici v **Analyzéru zátěžového testu** stavový řádek. Kliknete na odkaz zobrazíte všechny chyby v **chyby** tabulky v zobrazení tabulek.

## <a name="see-also"></a>Viz také:

- [Použití panelu čítačů v zobrazení grafů a zobrazení tabulek](../test/counters-panel-in-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)