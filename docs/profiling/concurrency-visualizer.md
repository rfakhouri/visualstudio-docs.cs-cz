---
title: Vizualizátor souběžnosti | Dokumentace Microsoftu
ms.date: 07/11/2017
ms.topic: conceptual
f1_keywords:
- vs.cv.performance.viewnavigation
- vs.cv.overview
- vs.cv.performance.gettingstarted
- vs.cv.gettingstarted
helpviewer_keywords:
- Concurrency Visualizer, Concurrency Visualizer
ms.assetid: ae5879a0-1e1a-455a-ba72-148e57f59289
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3e19cdb633528c3304d500fe268a583c542f1e4d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63001028"
---
# <a name="concurrency-visualizer"></a>Vizualizér souběžnosti

> [!NOTE]
> Vizualizátor souběžnosti je volitelné rozšíření pro Visual Studio. Vizualizátor souběžnosti a kolekce nástrojů pro Concurrency Visualizer můžete stáhněte z následující odkazy:
>
> - Stáhněte si [Concurrency Visualizer pro Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.ConcurrencyVisualizer2017#overview) rozšíření.
> - Stáhněte si [Concurrency Visualizer pro Visual Studio 2015](https://marketplace.visualstudio.com/items?itemName=Diagnostics.ConcurrencyVisualizerforVisualStudio2015) rozšíření.
> - Stáhněte si [Concurrency Visualizer kolekce nástrojů pro Visual Studio 2015](http://www.microsoft.com/download/details.aspx?id=49103).
>
> [Concurrency Visualizer nástroje příkazového řádku (CVCollectionCmd)](../profiling/concurrency-visualizer-command-line-utility-cvcollectioncmd.md) umožňuje shromažďovat trasování z příkazového řádku, který se zobrazí ve vizualizátoru souběžnosti pro Visual Studio 2015. Nástroj můžete použít na počítačích, které nemají nainstalovanou sadu Visual Studio.

Vizualizátor souběžnosti můžete zobrazit, jak vaše aplikace s více podprocesy provádí. Zobrazení v Concurrency Visualizer poskytují grafická, tabulková a textová data, která zobrazují časové vztahy mezi vlákny v programu a systém jako celek. Vizualizátor souběžnosti můžete použít k vyhledání problémových míst výkonu, procesoru nízkého využití, kolize vlákna, migrace vlákna přes jádro, zpoždění synchronizace, rozhraní DirectX aktivity, míst překrytí I/O a dalších informací. Zobrazení obsahují data, která můžete reagovat propojením jejich grafického výstupu na volání zásobníků a zdrojový kód.

> [!NOTE]
> Vizualizátor souběžnosti nepodporuje webové projekty.

Vizualizátor souběžnosti spoléhá na [události trasování pro Windows](http://go.microsoft.com/fwlink/?LinkId=234579) funkce.

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Zobrazení využití](../profiling/utilization-view.md)|Popisuje, jak zobrazit a analyzovat aktivitu systému přes všechny procesory.|
|[Zobrazení vláken](../profiling/threads-view-parallel-performance.md)|Popisuje, jak analyzovat interakce mezi vlákny v programu.|
|[Zobrazení jader](../profiling/cores-view.md)|Popisuje, jak analyzovat migraci vlákna mezi jádry.|
|[Obecné vzory pro vícevláknové aplikace s nevhodným chováním](../profiling/common-patterns-for-poorly-behaved-multithreaded-applications.md)|Popisuje několik běžných vzorů a ukazuje, jak vypadají ve vizualizátoru souběžnosti.|
|[Souběžného vývoje v sadě Visual Studio blog](http://go.microsoft.com/fwlink/?LinkId=235385)|Poskytuje tipy a osvědčené postupy pro Vizualizátor souběžnosti.|
|[Zobrazení sestav výkonu](../profiling/performance-report-views.md)|Poskytuje referenční informace pro sestavy a zobrazení nástrojů pro profilaci Visual Studio.|
|[SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md)|Popisuje, jak použít zdrojový kód k zobrazení dalších informací ve vizualizátoru souběžnosti.|
|[Nástroj příkazového řádku ve Vizualizéru souběžnosti (CVCollectionCmd)](../profiling/concurrency-visualizer-command-line-utility-cvcollectioncmd.md)|Popisuje, jak používat nástroj příkazového řádku Vizualizéru souběžnosti (CVCollectionCmd.exe) ke shromažďování a zpracování trasování na počítačích, které nemáte Visual Studio.|

## <a name="see-also"></a>Viz také:

- [Profilace v sadě Visual Studio](../profiling/index.md)
- [Nejdřív se podívejte na nástroje pro profilaci](../profiling/profiling-feature-tour.md)
