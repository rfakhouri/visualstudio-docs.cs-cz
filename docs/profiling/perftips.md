---
title: Tipy pro výkon | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 509d2d4f-48a5-4cdf-acad-6f7b75421303
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0713ae13038991ec65dcbebe350c9085f7d6a94a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60103417"
---
# <a name="perftips"></a>Tipy pro výkon
Ladicí program sady Visual Studio *tipy pro výkon* a integrovaný ladicí program **diagnostické nástroje** dozvíte, jak monitorovat a analyzovat výkon vaší aplikace během ladění.

 I když diagnostické nástroje integrované v ladicím programu jsou skvělý způsob, od zjištění problémů s výkonem při vývoji, ladicí program může mít významný dopad na výkon vaší aplikace. Ke shromažďování přesnější údaje o výkonu, zvažte použití diagnostických nástrojů sady Visual Studio, na kterých běží mimo ladicí program příliš jako další část vaší vyšetřování výkonu. Zobrazit [spustit s nebo bez ladicího programu nástroje pro profilaci](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="perftips"></a>Tipy pro výkon
 Pokud ladicí program zastaví provedení u zarážky a krokování operace, uplynulý čas přerušení od předchozí zarážky se zobrazí jako popis tlačítka v okně editoru. Další informace najdete v tématu [tipy pro výkon: Výkon informace na přehledem při ladění se sadou Visual Studio](https://devblogs.microsoft.com/devops/perftips-performance-information-at-a-glance-while-debugging-with-visual-studio/).

 ![PerfTip](../profiling/media/dbgdiag_perf_perftip.png "DBGDIAG_PERF_PerfTip")

## <a name="diagnostics-tools-window"></a>Okno diagnostické nástroje
 Zarážky a údaje o načasování související se zaznamenávají do **diagnostické nástroje** okna.

 Následující grafické ukazuje **diagnostické nástroje** okna v aplikaci Visual Studio 2015 Update 1:

 ![DiagnosticTools&#45;Update1](../profiling/media/diagnostictools-update1.png "DiagnosticTools-Update1")

- **Události přerušení** časová osa označit zarážky, které se dosáhlo v relaci ladění. Klikněte na událost, která ho vyberte **ladicí program** seznam podrobností.

- **Využití výkonu procesoru** graf zobrazuje změnu ve využití procesoru ze všech jader procesoru v relaci ladění.

- **Události** seznam **ladicí program** v podokně podrobností zahrnují položky pro každou událost přerušení.

- **Doba trvání** sloupec události přerušení Zobrazí uplynulý čas mezi událostí a předchozí zarážky.

## <a name="turn-perftips-on-or-off"></a>Zapnout nebo vypnout tipy pro výkon
 K povolení nebo zakázání tipy pro výkon:

1. Na **ladění** nabídce zvolte **možnosti**.

2. Zaškrtněte nebo zrušte zaškrtnutí **zobrazit vypršel PerfTip při ladění**.

## <a name="turn-the-diagnostic-tools-window-on-or-off"></a>Zapnout nebo vypnout v okně diagnostické nástroje
 Povolit nebo zakázat v okně diagnostické nástroje:

1. Na **ladění** nabídce zvolte **možnosti**.

2. Zaškrtněte nebo zrušte zaškrtnutí **při ladění povolit diagnostické nástroje**.

## <a name="see-also"></a>Viz také:
- [Profilace v sadě Visual Studio](../profiling/index.md)
- [Nejdřív se podívejte na nástroje pro profilaci](../profiling/profiling-feature-tour.md)
