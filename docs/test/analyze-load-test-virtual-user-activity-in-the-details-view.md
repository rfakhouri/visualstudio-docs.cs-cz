---
title: Analýza aktivity virtuálních uživatelů zátěžového testu v sadě Visual Studio
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
ms.openlocfilehash: 32f613f29bb0627f45f5ce331589629744d61373
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49840633"
---
# <a name="analyzing-load-test-virtual-user-activity-in-the-details-view-of-the-load-test-analyzer"></a>Analýza aktivity virtuálních uživatelů zátěžového testu v podrobném zobrazení Analyzéru zátěžového testu

**Graf aktivity virtuálního uživatele**

 ![Graf aktivity virtuálního uživatele](../test/media/virtual_actchart.png)

 **Podrobnosti** zobrazení zobrazí **graf aktivity virtuálního uživatele**, který se používá k vizuální analýza jednotlivého virtuálního uživatele nebyla během zátěžového testu. **Graf aktivity virtuálního uživatele** vám umožní vidět vzory aktivity uživatelů, vzory zátěže, korelovat Nezdařená nebo pomalá testy a zobrazit žádosti pomocí další aktivity virtuálního uživatele. **Graf aktivity virtuálního uživatele** můžete také vám pomáhají určit, provozní špičky ve využití procesoru, drops požadavků za sekundu, a co testy nebo stránky, které byly spuštěny během špičky a drops.

> [!NOTE]
> Před spuštěním zátěžového testu, pro kterou chcete použít **graf podrobností aktivity virtuálního uživatele**, musíte ověřit, že **úložiště podrobností časování** je nastavena na  **AllIndividualDetails** možnost pomocí editoru zátěžových testů výkonu. Další informace najdete v tématu [postupy: nastavení shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md).

 **Panel podrobné legendy**

 ![Panel podrobné legendy](../test/media/ltest_detailslegend.png)

 Je viditelný v panel podrobné legendy **graf aktivity virtuálního uživatele**. Podrobnosti o legendy podokně umožňuje filtrovat testy, stránky a transakce na základě několika různých kritérií. Můžete například odebrat určité testy ze zobrazení, nebo odebrání všech úspěšných testů nebo odebrání testů, které se nezdařilo s některým chybám. Můžete také odebrat všechny testy, které nemají protokoly.

 Můžete zvýraznit testů, které se nezdařilo, který se zobrazí všechny neúspěšné testy vybarvenými červeně. Můžete také zvýraznit testy, které mají protokolů testu. Testy s využitím protokolů se zobrazí zeleně.

 **Filtrování výsledků Panel**

 ![Filtrovat panel výsledků](../test/media/ltest_filterresults.png)

 Panel výsledků filtru je zobrazen v **graf aktivity virtuálního uživatele**. Panel výsledků filtru můžete filtrovat podle následujících akcí:

-   **Zobrazit pouze výsledky s protokoly** zobrazí pouze výsledky, které mají protokolů testu k nim má přiřazené testů.

-   **Zobrazit úspěšné výsledky** úspěšné výsledky se zobrazí.

-   **Zobrazit výsledky s chybami** zobrazuje výsledky s chybami, které vám mohou pomoci při ladění.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-|-|
|**Konfigurace vašeho zátěžového testu pro graf aktivity virtuálního uživatele:** před spuštěním zátěžového testu, který chcete zobrazit data aktivity virtuálního uživatele na, je nutné nejprve nakonfigurovat nastavení vlastností zátěžových testů.|-   [Postupy: nastavení shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md)|
|**Spuštění zátěžového testu:** po vytvoření zátěžového testu a jeho nakonfigurování ke shromažďování dat aktivity virtuálních uživatelů, musíte spustit test, dokud se nedokončí v abyste mohli zobrazit **graf aktivity virtuálního uživatele**.||
|**Prohlédněte si výsledky testu zatížení, které obsahují data aktivity virtuálního uživatele:** po byly vytvořeny, konfigurovány a po dokončení jeho běhu zátěžového testu můžete zobrazit data aktivity virtuálního uživatele pomocí **graf aktivity virtuálního uživatele** .|-   [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)<br />-   [Postupy: analýza, co dělají virtuálních uživatelů během zátěžového testu](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md)|
|**Izolace potíží s výkonem v zátěžových testech:** můžete použít **graf aktivity virtuálního uživatele** a určit tak problémy s výkonem v zátěžovém testu.|-   [Návod: Izolace potíží s pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)|

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)