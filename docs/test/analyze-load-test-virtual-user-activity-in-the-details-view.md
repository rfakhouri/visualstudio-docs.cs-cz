---
title: Analýza aktivity virtuálních uživatelů zatížení testů v sadě Visual Studio
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
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 5ab42b66fca32dc5325ce0cb4d78fbb53df8b90f
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36233792"
---
# <a name="analyzing-load-test-virtual-user-activity-in-the-details-view-of-the-load-test-analyzer"></a>Analýza aktivity virtuálních uživatelů zatížení testu v podrobném zobrazení analyzéru spouštění testů

**Graf aktivity virtuálního uživatele**

 ![Graf aktivity virtuálního uživatele](../test/media/virtual_actchart.png)

 **Podrobnosti** zobrazení zobrazí **graf aktivity virtuálního uživatele**, který se používá k vizuálně analyzovat, co se jednotlivých virtuálních uživatelů během zátěžového testu. **Graf aktivity virtuálního uživatele** umožňuje najdete v části vzory aktivity uživatelů, vzory zátěže, korelovat testy selhání nebo pomalé a najdete v části požadavky, které ostatní aktivity virtuálních uživatelů. **Graf aktivity virtuálního uživatele** můžete také vám pomáhají určit špičky využití procesoru, vyřazuje v požadavků za sekundu, a co testy nebo stránky běžely během špičky a hodnota neklesne.

> [!NOTE]
> Před spuštěním zátěžový test, pro který chcete použít **graf podrobnosti aktivity virtuálního uživatele**, musíte ověřit, že **úložiště podrobností časování** je nastavena na  **AllIndividualDetails** možnost pomocí editoru zátěžových testů výkonu. Další informace najdete v tématu [postupy: nastavení shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md).

 **Panel podrobnosti legendy**

 ![Panel podrobnosti legendy](../test/media/ltest_detailslegend.png)

 Panel legendy podrobností se zobrazí na **graf aktivity virtuálního uživatele**. Podrobnosti o umožňuje podokně legendy, filtrovat testy, stránky a transakce na základě několika různých kritérií. Můžete například odebrat určité testy ze zobrazení, nebo odeberte všechny testy úspěšné nebo odeberte testy, které se nezdařilo s určitým chybám. Rovněž můžete odebrat všechny testy, které nemají protokoly.

 Můžete zvýrazněte testy, které se nezdařilo, který zobrazuje všechny neúspěšných testů označeno červeně. Můžete také zvýraznit testy, které mají protokolů testování. Testy s protokoly bude označeno zeleně.

 **Filtrování výsledků panely**

 ![Výsledky panel Filtr](../test/media/ltest_filterresults.png)

 Se zobrazí na panelu výsledků filtr **graf aktivity virtuálního uživatele**. Panel Filtr výsledky můžete filtrovat podle následující:

-   **Zobrazit pouze výsledky s protokoly** zobrazí pouze zkušební výsledky, které mají protokolů testování s nimi spojených.

-   **Zobrazit výsledky úspěšné** zobrazí výsledky úspěšné.

-   **Zobrazit výsledky s chybami** zobrazí výsledky s chybami, které mohou pomoci při ladění.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Nakonfigurovat svůj test zatížení na grafu aktivity virtuálního uživatele:** před spuštěním zátěžový test, který chcete zobrazit data aktivity virtuálních uživatelů v, musíte nejdřív nakonfigurovat nastavení zatížení testy vlastností.|-   [Postupy: nastavení shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md)|
|**Spuštění zátěžového testu:** po vytvoření zátěžový test a nakonfigurovat jej a povolte sběru dat aktivity virtuálního uživatele, dokud nebude dokončeno, abyste zobrazili musíte spustit test **graf aktivity virtuálního uživatele**.||
|**Zobrazení výsledků testu zatížení, které obsahují data aktivity virtuálních uživatelů:** po zátěžový test byly vytvořeny, konfigurovány a dokončení běhu, můžete zobrazit data aktivity virtuálního uživatele pomocí **graf aktivity virtuálního uživatele** .|-   [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)<br />-   [Postupy: analýza, co dělají virtuálních uživatelů během zátěžového testu](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md)|
|**Izolovat problémy s výkonem v zátěžových testech:** můžete použít **graf aktivity virtuálního uživatele** lze izolovat problémy s výkonem v zátěžovém testu.|-   [Návod: Izolace problémů pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)|

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)