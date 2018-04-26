---
title: Doba odezvy stránky v zátěžovém testu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, response times
- response times in load tests
- load test results, response times
ms.assetid: e61c49f3-3161-45b1-9220-08b5459065a2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 3f65920a1f47895ab6caf4bc84dd75c8100487a9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-view-web-page-response-time-in-a-load-test-using-the-load-test-analyzer"></a>Postupy: Zobrazení doby odezvy webové stránky v zátěžovém testu pomocí analyzéru zátěžového testu

Doba potřebná pro každou webovou stránku načíst se označuje jako *doba odezvy*. Když vytvoříte testu výkonnosti webu, můžete nastavit cílem doba odezvy pro každý požadavek webové stránky v testu výkonnosti webu.

Pokud spustíte testu výkonu webu zátěži v zátěžovém testu, budete schopní analyzovat následující informace pro jednotlivé stránky:

-   Průměrná doba odezvy pro stránku.

-   Procento iterací testů, které splňují cílem čas odpověď pro stránku.

-   Časy odezvy webové stránky můžete analyzovat pomocí zobrazení tabulek nebo zobrazení grafů v Analyzéru zátěžového testu:

-   Analýza odezvy webové stránky v tabulkovém zobrazení

-   Analýza odezvy webové stránky v zobrazení grafů

## <a name="view-response-time-data-in-a-table"></a>Zobrazení odpovědi čas Data v tabulce

### <a name="to-view-response-time-data-in-a-table"></a>Chcete-li zobrazit odpověď časových dat v tabulce

1.  V Analyzéru zátěžového testu zvolte **tabulky** na panelu nástrojů a ujistěte se, že se zobrazí mřížku tabulky.

2.  V **tabulky** rozevíracím seznamu vyberte **stránky**.

3.  Data pro jednotlivé stránky se zobrazí v mřížce. Obvykle se zobrazí následující sloupce.

    |||
    |-|-|
    |**Stránka**|Název webové stránky.|
    |**Scénář**|Název tohoto scénáře. Důležité: Pokud máte více než jeden scénář v testu výkonnosti webu.|
    |**Test**|Název testu výkonnosti webu. Důležité: Pokud máte více než jeden testu výkonnosti webu v zátěžovém testu.|
    |**Sítě**|Typ sítě.<br /><br /> Ve výchozím nastavení nejsou shromažďovány tato data. Shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte uzel spuštění nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **AllIndividualDetails**.|
    |**Celkový počet**|Celkový počet požadavků, které byly provedeny pro webovou stránku. Toto je celkový počet pro všechny iterace v zátěžovém testu.|
    |**Průměr**|Doba odezvy průměrná stránky.<br /><br /> Ve výchozím nastavení nejsou shromažďovány tato data. Shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte uzel spuštění nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **AllIndividualDetails**.|
    |**Min.**|Doba odezvy minimální stránky.<br /><br /> Ve výchozím nastavení nejsou shromažďovány tato data. Shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte uzel spuštění nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **AllIndividualDetails**.|
    |**Medián**|Doba odezvy střední stránky.<br /><br /> Ve výchozím nastavení nejsou shromažďovány tato data. Shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte uzel spuštění nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **AllIndividualDetails**.|
    |**90%**|90. percentil dobu odezvy. To znamená, že 90 % stránek odpověděl rychleji, než je počet a 10 % stránek odpověděl pomaleji.<br /><br /> Ve výchozím nastavení nejsou shromažďovány tato data. Shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte uzel spuštění nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **AllIndividualDetails**.|
    |**95%**|95. percentil dobu odezvy. To znamená, že 95 % stránek odpověděl rychleji, než je počet a 5 % stránek odpověděl pomaleji.|
    |**99%**|99th percentilu dobu odezvy. To označuje, že 99 % stránek odpověděl rychleji, než toto číslo a 1 % stránek odpověděl pomaleji.<br /><br /> Ve výchozím nastavení nejsou shromažďovány tato data. Shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte uzel spuštění nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **AllIndividualDetails**.|
    |**Max**|Doba odezvy maximální stránky.<br /><br /> Ve výchozím nastavení nejsou shromažďovány tato data. Shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte uzel spuštění nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **AllIndividualDetails**.|
    |**Směrodatná odchylka**|Ve výchozím nastavení pokud nejsou zjištěny směrodatnou odchylku data. Shromažďovat tato data v **editoru zátěžových testů**v části **spustit nastavení** uzlu, vyberte uzel spuštění nastavení změnit. V **vlastnosti** okně pro **úložiště podrobností časování** vlastnosti, vyberte **AllIndividualDetails**.|
    |**Doba stránky**|Průměrná doba odezvy pro všechny požadavky, které byly provedeny pro webovou stránku.|
    |**Cílem**|Cílem čas stránky. Toto je konstantní hodnota pro stránku. **Poznámka:** cílem čas stránky se zobrazí jenom v případě, že cílem byla definována pro požadavku v testu výkonnosti webu.|
    |**Cílem % schůzky**|Procento požadavků, které byly provedeny pro webové stránky, která splnit cíle dobu odezvy.|

 Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="view-response-time-data-in-a-graph"></a>Data čas odpovědi zobrazení v grafu.

Odpověď časových dat můžete také zobrazit v grafu zobrazíte jeho změny v průběhu času během zátěžového testu. To je obzvláště užitečné, pokud vaše vzor zatížení zvyšuje test běží (například pokud používáte vzor zatížení kroku). Další informace najdete v tématu [úpravy vzorů zatížení pro aktivity virtuálního uživatele modelu](../test/edit-load-patterns-to-model-virtual-user-activities.md).

### <a name="to-view-response-time-data-in-a-graph"></a>Chcete-li zobrazit data čas odpovědi v grafu.

1.  V Analyzéru zátěžového testu zvolte **grafy** na panelu nástrojů a ujistěte se, že se zobrazí graf.

2.  V **čítače** okno, rozbalte uzel scénáře, ve kterém vás zajímá (například `Scenario1`).

3.  Rozbalte uzel testu výkonnosti webu, která vás zajímá.

4.  Rozbalte uzel **stránky**.

5.  Rozbalte uzel stránky, která vás zajímá.

6.  Klikněte pravým tlačítkem na **% stránky schůzku cílem** a potom zvolte **zobrazit čítače v grafu**.

     Data se přidá do grafu.

7.  (Volitelné) Opakujte předchozí krok pro střední Doba stránky, cílem čas odezvy stránky a celkový počet stránek.

    > [!NOTE]
    > Cílem čas odezvy stránky je konstantní.

 Další informace najdete v tématu [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md).

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)
- [Postupy: přístup k výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)