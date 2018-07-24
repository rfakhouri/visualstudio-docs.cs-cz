---
title: Porušení prahové hodnoty pro zátěžové testy v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, threshold violations
ms.assetid: 0126d7b7-0538-4ea9-9046-6556654b3b9d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: cb64626034c8c9bf03875385a80ebc417bf05dcb
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204060"
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>Postupy: Analýza překročení mezních použitím panelu čítačů v Analyzéru zátěžového testu

**Čítače** panel je zobrazen v zobrazení grafů a zobrazení tabulek v **Analyzéru zátěžového testu** během zátěžového testu nebo během analýzy výsledku zátěžového testu. V tématu [výsledků zátěžového testu analyzovat v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md), [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) a [postupy: přístup k analýze výsledků zátěžového testu](../test/how-to-access-load-test-results-for-analysis.md).

 Porušení prahové hodnoty jsou přidruženy konkrétních čítačů výkonu a označení, že čítač výkonu překročil, nebo klesl pod prahovou hodnotu set. Ikony v **čítače** panel komunikovat mezních hodnot.

 ![Uzel počítače na panelu čítačů](../test/media/ltest_compnode.png)

 Na ikonu porušení prahové hodnoty je rozšířena z uzlu stromové struktury, ve kterém se nachází čítač selhání do kořenového adresáře. Ikona upozornění uživatele porušení na čítač, který se nemusí zobrazovat ve stromu, protože nebyla došlo k rozbalení stromu. Příklad ikony vidíte v **uzel počítače** v **čítače** panel na předchozím obrázku.

 Ikona bude jeden z následujících akcí:

 ![Žádná porušení prahové hodnoty](../test/media/icon_ltest_1.gif) Žádná porušení mezní hodnoty.

 ![Porušení kritické prahové hodnoty na posledního intervalu](../test/media/icon_ltest_2.gif) Na poslední interval došlo k porušení kritické prahové hodnoty.

 ![Porušení kritické prahové hodnoty na předchozí interval](../test/media/icon_ltest_3.gif) V předchozí interval došlo k porušení kritické prahové hodnoty.

 ![Varování porušení mezní hodnoty do posledního intervalu](../test/media/icon_ltest_4.gif) Na poslední interval došlo k porušení výstražné prahové hodnoty.

 ![Varování porušení mezní hodnoty na předchozí interval](../test/media/icon_ltest_5.gif) V předchozí interval došlo k porušení výstražné prahové hodnoty.

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>Analýza překročení mezních hodnot na panelu čítačů

1.  Po dokončení zátěžového testu nebo po načtení výsledků testu v Analyzéru zátěžového testu na panelu nástrojů, zvolte buď **grafy** nebo **tabulky**.

     **Čítače** panelu se zobrazí v zobrazení grafů nebo v zobrazení tabulek.

2.  Pokud **čítače** panelu není zobrazen, zvolte **zobrazit Panel čítačů** na panelu nástrojů.

     Všechny uzly, které obsahují překročení mezní hodnoty, budou obsahovat jednu z výše uvedených ikon.

3.  Rozbalte uzel, který obsahuje ikonu mezní hodnoty, jako **počítače** uzlu, jak je znázorněno na předchozím obrázku s názvem "Uzel počítače na panelu čítačů s překročením mezní hodnoty." Uzel dále rozbalujte, dokud nenarazíte na čítač výkonu s překročením mezní hodnoty. Například na obrázku znázorňuje chybné instance **Microsoft virtuálního adaptéru neúspěšné síťové sběrnice**.

4.  (Volitelné) Klikněte pravým tlačítkem myši na čítač výkonu s překročením mezní hodnoty a vyberte jednu z následujících možností:

    -   **Zobrazit čítač v grafu**: V zobrazení grafů bude čítač výkonu přidán a zvýrazněn ve vybraném grafu. Další informace najdete v tématu [postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

        > [!NOTE]
        > Ikony překročení mezní hodnoty mohou být rovněž zobrazeny v grafu v zobrazení grafu. V grafu vedle datový bod, kde došlo k porušení mezní hodnoty se zobrazí ikona prahovou hodnotu. Chcete-li to provést, zvolte **zobrazit legendu** rozevíracího seznamu na panelu nástrojů a vyberte **zobrazení překročení prahové hodnoty v grafu**.

    -   **Zobrazit čítač v legendě**: V legendě, čítač výkonu přidán a vybrán. Další informace najdete v tématu [použití legendy zobrazení grafů k analýze zátěžových testů](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Přidat graf**:

    1.  **Zadejte název grafu** se zobrazí dialogové okno.

    2.  V **název grafu** textového pole zadejte název pro nový graf a zvolte **OK**.

    3.  (Volitelné) Pravým tlačítkem myši na čítač výkonu znovu a vyberte **zobrazit čítač v grafu**.

         Další informace najdete v tématu [postupy: vytváření vlastních grafů](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (Volitelné) Pokud analyzujete překročení mezní hodnoty ve výsledku dokončeného zátěžového testu, zvažte použití funkcí přiblížení v zobrazení grafů. Další informace najdete v tématu [postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Je-li překročení mezní hodnoty byly zjištěny během zátěžového testu, bude k dispozici v odkaz s názvem "překročení mezních hodnot" počet porušení zásad, včetně **Analyzéru zátěžového testu** stavový řádek. Kliknete na odkaz zobrazíte všechny mezních hodnot v **prahové hodnoty** tabulky v zobrazení tabulek.

## <a name="see-also"></a>Viz také:

- [Použitím panelu čítačů v zobrazení grafů a zobrazení tabulek](../test/counters-panel-in-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)