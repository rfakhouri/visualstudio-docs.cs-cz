---
title: Analýza využití paměti
ms.custom: seodec18
ms.date: 01/02/2018
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b73fc70231e9756bf20f90f5873a0241c5f29bdd
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315560"
---
# <a name="analyze-memory-usage"></a>Analýza využití paměti
Použijte integrovaný ladicí program **využití paměti** diagnostický nástroj k vyhledání nevrácené paměti a využití paměti neefektivní. Umožňuje nástroj využití paměti, můžete provést jeden nebo více *snímky* spravovaný a nativní paměti haldy. Můžete shromažďovat snímky aplikací .NET, ASP.NET, nativní nebo smíšený režim (.NET a nativní).

-   Jeden snímek pochopit jeho relativní dopad typů objektů na využití paměti a vyhledání kódu vaší aplikace, která používá paměť neefektivně, můžete analyzovat.

-   Můžete také porovnat (rozdíl) dvěma snímky vyhledejte oblasti v kódu aplikace, které způsobují využití paměti časem zvětšuje.

Podrobné pokyny najdete v tématu [analýza využití paměti](../profiling/memory-usage.md) kurzu.  V současné době k měření využití paměti pro aplikace .NET Core, musíte použít nástroj s připojeným ladícím nástrojem. Pro další spravované a nativní aplikace, můžete pomocí nástroje s nebo bez ladicí program připojený.

Můžete použít profilovací nástroje bez ladicího programu s Windows 7 a novější. Windows 8 a novější se vyžaduje pro spuštění nástrojů pro profilaci s ladicím programem (**diagnostické nástroje** okno).

## <a name="blogs-and-videos"></a>Blogy a videa

[Analýza využití procesoru a paměti během ladění](https://devblogs.microsoft.com/visualstudio/analyze-cpu-memory-while-debugging/)

[Visual C++ blog: Profilování paměti v aplikaci Visual C++ 2015](https://blogs.msdn.microsoft.com/vcblog/2015/10/21/memory-profiling-in-visual-c-2015/)

## <a name="see-also"></a>Viz také:

- [Profilace v sadě Visual Studio](../profiling/index.md)
- [Nejdřív se podívejte na nástroje pro profilaci](../profiling/profiling-feature-tour.md)