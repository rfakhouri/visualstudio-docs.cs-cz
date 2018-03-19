---
title: "Analýza zátěžový test chyb s použitím panelu čítačů v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Load Test Analyzer, counters panel
ms.assetid: 981b4f1e-505a-4078-a06d-58ae17d996b4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 055925fd626e03df6e80fe02647fc2c1ca67d6ad
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-analyze-errors-using-the-counters-panel"></a>Postupy: Analýza chyb s použitím panelu čítačů

Panel čítačů je v zobrazení grafů a zobrazení tabulek v Analyzéru zátěžového testu zobrazen během zátěžového testu nebo během analýzy výsledku zátěžového testu. Další informace najdete v tématu [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md), [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) a [postupy: přístup k analýzevýsledkůzátěžovéhotestu](../test/how-to-access-load-test-results-for-analysis.md).

 **Chyby** uzlu v panelu čítačů obsahuje všechny chyby, které byly zjištěny během zátěžového testu. Uzel chyby obsahuje několik uzlů chyba dílčí kategorie, které jsou specifické pro různé druhy chyb. Například **výjimky** a **chyby protokolu HTTP**.

 ![Čítač panely chyby uzlu](../test/media/ltest_errornode.png "LTest_ErrorNode")

## <a name="to-analyze-errors-in-the-counters-panel"></a>K analýze chyb v panelu čítačů

1.  Po dokončení testu zatížení, nebo po načtení výsledků testů, v panelu nástrojů nástroje načíst testování Analyzer společnosti, zvolte buď **grafy** nebo **tabulky**.

     **Čítače** panelu se zobrazí v zobrazení grafů nebo tabulkovém zobrazení.

2.  Pokud není viditelná panelu čítačů, zvolte **zobrazit Panel čítačů** na panelu nástrojů.

3.  Rozbalte **chyby** a vyberte kategorii k chybě nebo dílčí kategorie chyby, který chcete analyzovat.

4.  Klikněte pravým tlačítkem na chybu a vyberte jednu z následujících možností:

    -   **Zobrazit čítače na graf**: V zobrazení grafů chyba přidat a zvýrazněným vybrané grafu. Další informace najdete v tématu [postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

    -   **Čítač zobrazí v legendě**: Chyba a je vybraný v legendě. Další informace najdete v tématu [použití legendy zobrazení grafů k analýze zátěžových testů](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Přidat graf**:

    1.  **Zadejte název grafu** se zobrazí dialogové okno.

    2.  V **název grafu** textového pole zadejte název pro nový graf a pak zvolte **OK**.

    3.  (Volitelné) Znovu klikněte pravým tlačítkem chyby a vyberte **zobrazit čítače v grafu**.

         Další informace najdete v tématu [postupy: vytvoření vlastní grafy](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (Volitelné) Pokud jsou analýza chybu ve výsledku dokončeného zátěžového testu, zvažte použití funkcí zvětšení v průběhu v grafech. Další informace najdete v tématu [postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Pokud všechny chyby byly zjištěny během zátěžového testu, spuštění, odkaz s názvem, včetně počtu chyb zjištěno, že bude k dispozici ve stavovém řádku načíst testování analyzátor. Můžete na odkaz zobrazíte všechny chyby v **chyby** tabulky zobrazení tabulek.

## <a name="see-also"></a>Viz také

- [Použitím panelu čítačů v zobrazení grafů a tabulek zobrazení](../test/counters-panel-in-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)