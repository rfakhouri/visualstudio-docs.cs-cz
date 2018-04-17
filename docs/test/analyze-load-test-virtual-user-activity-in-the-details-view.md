---
title: Analýza aktivity virtuálních uživatelů zatížení testů v sadě Visual Studio | Microsoft Docs
ms.date: 10/03/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.activitychart
helpviewer_keywords:
- virtual user activity chart
- load test, virtual user activity chart
ms.assetid: 63f4bd42-3cfb-4eee-af68-e8334976539e
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 5f874b070e726374a20e821508115b5798f40b80
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="analyzing-load-test-virtual-user-activity-in-the-details-view-of-the-load-test-analyzer"></a>Analýza aktivity virtuálních uživatelů v rámci zátěžového testu v podrobném zobrazení analyzéru zátěžového testu

**Graf aktivity virtuálního uživatele**

 ![Graf aktivity virtuálního uživatele](../test/media/virtual_actchart.png "Virtual_ActChart")

 Zobrazení podrobností se zobrazí virtuální graf aktivity uživatele, který se používá k vizuálně analyzovat, co jednotlivé virtuálních uživatelů při zatížení otestovat. Graf aktivity virtuálního uživatele umožňuje najdete v části vzory aktivity uživatelů, vzory zátěže, korelovat testy selhání nebo pomalé a najdete v části požadavky, které ostatní aktivity virtuálních uživatelů. Grafu aktivity virtuálního uživatele také vám pomohou určit špičky využití procesoru, vyřazuje v požadavků za sekundu a jaké testů nebo stránky běžely během špičky a hodnota neklesne.

> [!NOTE]
> Než spustíte zátěžový test, pro který chcete použít virtuální graf podrobnosti aktivity uživatele, musíte se ověřit, že **úložiště podrobností časování** je nastavena na **AllIndividualDetails** možnost pomocí Editor zátěžového testu výkonu. Další informace najdete v tématu [postupy: Konfigurace shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md).

 **Panel podrobnosti legendy**

 ![Podrobnosti legendy panely](../test/media/ltest_detailslegend.png "LTest_DetailsLegend")

 Panel podrobností legendy je viditelný v grafu aktivity virtuálního uživatele. Podrobnosti o umožňuje podokně legendy, filtrovat testy, stránky a transakce na základě několika různých kritérií. Můžete například odebrat určité testy ze zobrazení, nebo odeberte všechny testy úspěšné nebo odeberte testy, které se nezdařilo s určitým chybám. Rovněž můžete odebrat všechny testy, které nemají protokoly.

 Můžete zvýrazněte testy, které se nezdařilo, který zobrazuje všechny neúspěšných testů označeno červeně. Můžete také zvýraznit testy, které mají protokolů testování. Testy s protokoly bude označeno zeleně.

 **Filtrování výsledků panely**

 ![Filtrovat výsledky panely](../test/media/ltest_filterresults.png "LTest_FilterResults")

 Panel výsledky filtr je viditelný v grafu aktivity virtuálního uživatele. Panel Filtr výsledky můžete filtrovat podle následující:

-   **Zobrazit pouze výsledky s protokoly** zobrazí pouze zkušební výsledky, které mají protokolů testování s nimi spojených.

-   **Zobrazit výsledky úspěšné** zobrazí výsledky úspěšné.

-   **Zobrazit výsledky s chybami** zobrazí výsledky s chybami, které mohou pomoci při ladění.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Nakonfigurovat svůj test zatížení na grafu aktivity virtuálního uživatele:** před spuštěním zátěžový test, který chcete zobrazit data aktivity virtuálních uživatelů v, musíte nejdřív nakonfigurovat nastavení zatížení testy vlastností.|-   [Postupy: nastavení shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md)|
|**Spuštění zátěžového testu:** po vytvoření zátěžový test a nakonfigurovat jej a povolte sběru dat aktivity virtuálního uživatele, dokud nebude dokončeno, chcete-li zobrazit grafu aktivity virtuálního uživatele musíte spustit test.||
|**Zobrazení výsledků testu zatížení, které obsahují data aktivity virtuálních uživatelů:** po zátěžový test byly vytvořeny, konfigurovány a dokončení běhu, můžete zobrazit data aktivit virtuálních uživatelů pomocí grafu aktivity virtuálního uživatele.|-   [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)<br />-   [Postupy: analýza, co dělají virtuálních uživatelů během zátěžového testu](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md)|
|**Izolovat problémy s výkonem v zátěžových testech:** grafu aktivity virtuálního uživatele můžete izolovat problémy s výkonem v zátěžovém testu.|-   [Návod: Izolace problémů pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)|

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)