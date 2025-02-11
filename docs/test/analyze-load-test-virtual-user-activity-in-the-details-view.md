---
title: Analýza aktivity virtuálních uživatelů zátěžového testu
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
manager: jillfra
ms.openlocfilehash: a03096e92f2a5da98da2d1850f505c65eb5b6e27
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918611"
---
# <a name="analyzing-load-test-virtual-user-activity-in-the-details-view-of-the-load-test-analyzer"></a>Analýza aktivity virtuálních uživatelů zátěžového testu v podrobném zobrazení Analyzéru zátěžového testu

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

**Graf aktivity virtuálního uživatele**

![Graf aktivity virtuálního uživatele](../test/media/virtual_actchart.png)

**Podrobnosti** zobrazení zobrazí **graf aktivity virtuálního uživatele**, který se používá k vizuální analýza jednotlivého virtuálního uživatele nebyla během zátěžového testu. **Graf aktivity virtuálního uživatele** vám umožní vidět vzory aktivity uživatelů, vzory zátěže, korelovat Nezdařená nebo pomalá testy a zobrazit žádosti pomocí další aktivity virtuálního uživatele. **Graf aktivity virtuálního uživatele** můžete také vám pomáhají určit, provozní špičky ve využití procesoru, drops požadavků za sekundu, a co testy nebo stránky, které byly spuštěny během špičky a drops.

> [!NOTE]
> Před spuštěním zátěžového testu, pro kterou chcete použít **graf podrobností aktivity virtuálního uživatele**, musíte ověřit, že **úložiště podrobností časování** je nastavena na  **AllIndividualDetails** možnost pomocí editoru zátěžových testů výkonu.

**Panel podrobné legendy**

![Panel podrobné legendy](../test/media/ltest_detailslegend.png)

Je viditelný v panel podrobné legendy **graf aktivity virtuálního uživatele**. Podrobnosti o legendy podokně umožňuje filtrovat testy, stránky a transakce na základě několika různých kritérií. Můžete například odebrat určité testy ze zobrazení, nebo odebrání všech úspěšných testů nebo odebrání testů, které se nezdařilo s některým chybám. Můžete také odebrat všechny testy, které nemají protokoly.

Můžete zvýraznit testů, které se nezdařilo, který se zobrazí všechny neúspěšné testy vybarvenými červeně. Můžete také zvýraznit testy, které mají protokolů testu. Testy s využitím protokolů se zobrazí zeleně.

**Filtrování výsledků Panel**

![Filtrovat panel výsledků](../test/media/ltest_filterresults.png)

Panel výsledků filtru je zobrazen v **graf aktivity virtuálního uživatele**. Panel výsledků filtru můžete filtrovat podle následujících akcí:

- **Zobrazit pouze výsledky s protokoly** zobrazí pouze výsledky, které mají protokolů testu k nim má přiřazené testů.

- **Zobrazit úspěšné výsledky** úspěšné výsledky se zobrazí.

- **Zobrazit výsledky s chybami** zobrazuje výsledky s chybami, které vám mohou pomoci při ladění.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-|-|
|**Spusťte zátěžový test:** Jakmile vytvoříte zátěžový test a nakonfigurujete ho tak, aby umožňoval shromažďování dat aktivity virtuálního uživatele, je nutné spustit test, dokud není dokončen, aby bylo možné zobrazit **graf aktivity virtuálního uživatele**.||
|**Zobrazení výsledků zátěžového testu, které obsahují data aktivity virtuálního uživatele:** Po vytvoření, konfiguraci a dokončení zátěžového testu můžete zobrazit data aktivity virtuálního uživatele pomocí **grafu aktivity virtuálního uživatele**.|-   [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)<br />-   [Jak: Analyzovat virtuální uživatele v průběhu zátěžového testu](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md)|
|**Izolace potíží s výkonem v zátěžových testech:** **Graf aktivity virtuálního uživatele** můžete použít ke zjištění problémů s výkonem v zátěžovém testu.|-   [Podrobné Izolace problémů pomocí grafu aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)|

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)