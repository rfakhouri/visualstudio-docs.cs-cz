---
title: Porozumění hodnotám dat kolizí prostředku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bdc41ee4c3c9f53d45245c6c305d7f8e221757f4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="understanding-resource-contention-data-values"></a>Porozumění hodnotám dat kolizí prostředku

Profilace kolizí prostředku shromažďuje podrobné zásobníku volání informace pokaždé, když, že konkurenční vláken v aplikaci, vynuceně přesunuty čekání na přístup k sdíleného prostředku.

Sestavy kolizí prostředku zobrazí celkový počet kolizí a celková doba strávená čeká na prostředek pro moduly, funkce, řádků zdrojového kódu a pokyny, ve kterých došlo k čekání.

- (Včetně) hodnot zobrazí celkový počet kolizí, které vynutit funkce čekání podle kolize prostředku – a celkovou dobu, kterou čekali funkce.  Kolizí, která byla způsobena podřízené funkce, které byly volá funkci jsou součástí (včetně) hodnot.

- Výhradní hodnoty zobrazit jenom Počet kolizí, vynutit funkce čekat a která byla způsobena kódu v těle funkce. Kolizí způsobené podřízené funkce nejsou zahrnuty. Výhradní čas pro funkci také obsahuje pouze dobu čekání, která byla způsobena příkazy v těle funkce.

Zobrazení sestav kolizí prostředku také obsahovat časová osa grafy, které se zobrazí jednotlivé kolizní události v čase a zobrazit zásobníky volání, které vytvořili určitá událost. Další informace naleznete v jednom z následujících témat:

- [Zobrazení podrobností o vláknu](../profiling/thread-details-view-contention-data.md)

- [Zobrazení podrobností o prostředku](../profiling/resource-details-view-contention-data.md)

Další informace o druhý režim profilace souběžného zpracování najdete v tématu [vizualizér souběžnosti](../profiling/concurrency-visualizer.md).