---
title: "Překročení mezních hodnot pro zátěžové testy v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, threshold violations
ms.assetid: 0126d7b7-0538-4ea9-9046-6556654b3b9d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 9c511bb3edf8ad8277b367733f85108d9587898e
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>Postupy: Analýza překročení mezních hodnot s použitím panelu čítačů v Analyzéru zátěžového testu

Panel čítačů je v zobrazení grafů a zobrazení tabulek v Analyzéru zátěžového testu zobrazen během zátěžového testu nebo během analýzy výsledku zátěžového testu. V tématu [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md), [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) a [postupy: přístup k výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md).

 Porušení pravidel mezních jsou přidruženy konkrétních čítačích výkonu a naznačují, že čítač výkonu překročil, nebo klesla pod prahovou hodnotu sady. Ikony v panelu čítačů komunikovat mezních hodnot.

 ![Uzel počítače čítač panely](../test/media/ltest_compnode.png "LTest_CompNode")

 Ikona pro porušení prahové hodnoty je rozšířena z uzlu stromu, které se čítač selhání nachází do kořenového adresáře. Ikona upozornění uživatele k narušení u čítačů, které nemusí být vidět ve stromu, protože nebyl rozšířila stromu. Příklad ikony si můžete prohlédnout ve **počítače uzlu** panelu čítačů na předchozím obrázku.

 Ikona bude jeden z následujících akcí:

 ![Žádná porušení prahové hodnoty](../test/media/icon_ltest_1.gif "Icon_LTest_1") žádné porušení prahové hodnoty.

 ![Porušení kritické prahové hodnoty na posledního intervalu](../test/media/icon_ltest_2.gif "Icon_LTest_2") na posledního intervalu došlo k porušení kritické prahové hodnoty.

 ![Porušení kritické prahové hodnoty v předchozí intervalu](../test/media/icon_ltest_3.gif "Icon_LTest_3") na předchozí interval došlo k porušení kritické prahové hodnoty.

 ![Porušení výstražné prahové hodnoty na posledního intervalu](../test/media/icon_ltest_4.gif "Icon_LTest_4") na posledního intervalu došlo k porušení výstražné prahové hodnoty.

 ![Porušení výstražné prahové hodnoty v předchozí intervalu](../test/media/icon_ltest_5.gif "Icon_LTest_5") na předchozí interval došlo k porušení výstražné prahové hodnoty.

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>Analýza překročení mezních hodnot na panelu čítačů

1.  Po dokončení testu zatížení, nebo po načtení výsledků testů, v panelu nástrojů nástroje načíst testování Analyzer společnosti, zvolte buď **grafy** nebo **tabulky**.

     Panel čítačů se zobrazí v zobrazení grafů nebo v zobrazení tabulek.

2.  Pokud není viditelná panelu čítačů, zvolte **zobrazit Panel čítačů** na panelu nástrojů.

     Všechny uzly, které obsahují překročení mezní hodnoty, budou obsahovat jednu z výše uvedených ikon.

3.  Rozbalte uzel, který obsahuje ikonu prahovou hodnotu, jako jsou například **počítače** uzlu, jak je vidět na předchozím obrázku s názvem "Počítače uzlu v Panel čítačů s porušení prahové hodnoty." Uzel dále rozbalujte, dokud nenarazíte na čítač výkonu s překročením mezní hodnoty. Například obrázku se nezdařilo instanci **Microsoft se nezdařilo sběrnice síťový adaptér virtuálního počítače**.

4.  (Volitelné) Klikněte pravým tlačítkem myši na čítač výkonu s překročením mezní hodnoty a vyberte jednu z následujících možností:

    -   **Zobrazit čítače na graf**: V zobrazení grafů, je přidat a zvýrazněným grafu, pro vybrané čítače výkonu. Další informace najdete v tématu [postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

        > [!NOTE]
        > Ikony překročení mezní hodnoty mohou být rovněž zobrazeny v grafu v zobrazení grafu. Ikona prahová hodnota se zobrazí v grafu vedle datového bodu, kde došlo k porušení prahové hodnoty. Chcete-li to provést, zvolte **zobrazit legendu** rozevíracího seznamu na panelu nástrojů a vyberte **zobrazit mezních hodnot v grafu**.

    -   **Čítač zobrazí v legendě**: V legendě, bude přidána a vybrané čítače výkonu. Další informace najdete v tématu [použití legendy zobrazení grafů k analýze zátěžových testů](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Přidat graf**:

    1.  **Zadejte název grafu** se zobrazí dialogové okno.

    2.  V **název grafu** textového pole zadejte název pro nový graf a pak zvolte **OK**.

    3.  (Volitelné) Klikněte pravým tlačítkem na čítače výkonu znovu a vyberte **zobrazit čítače v grafu**.

         Další informace najdete v tématu [postupy: vytvoření vlastní grafy](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (Volitelné) Pokud analyzujete překročení mezní hodnoty ve výsledku dokončeného zátěžového testu, zvažte použití funkcí přiblížení v zobrazení grafů. Další informace najdete v tématu [postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Je-li překročení mezní hodnoty zjištěno v průběhu zátěžového testu, ve stavovém řádku Analyzéru zátěžového testu se zobrazí odkaz s názvem „překročení mezních hodnot“, včetně počtu překročení. Můžete na odkaz zobrazíte všechny překročení mezních hodnot v **prahové hodnoty** tabulky zobrazení tabulek.

## <a name="see-also"></a>Viz také

- [Použitím panelu čítačů v zobrazení grafů a tabulek zobrazení](../test/counters-panel-in-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)