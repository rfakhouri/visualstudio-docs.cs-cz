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
ms.openlocfilehash: c06722e9270269ca674370d5bf8b1925d850ce00
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34477402"
---
# <a name="understand-resource-contention-data-values"></a>Pochopení hodnotám dat kolizí prostředku

Profilace kolizí prostředku shromažďuje podrobné zásobníku volání informace pokaždé, když, že konkurenční vláken v aplikaci, vynuceně přesunuty čekání na přístup k sdíleného prostředku.

Sestavy kolizí prostředku zobrazí celkový počet kolizí a celková doba strávená čeká na prostředek pro moduly, funkce, řádků zdrojového kódu a pokyny, ve kterých došlo k čekání.

- (Včetně) hodnot zobrazí celkový počet kolizí, které vynutit funkce čekání podle kolize prostředku – a celkovou dobu, kterou čekali funkce.  Kolizí, která byla způsobena podřízené funkce, které byly volá funkci jsou součástí (včetně) hodnot.

- Výhradní hodnoty zobrazit jenom Počet kolizí, vynutit funkce čekat a která byla způsobena kódu v těle funkce. Kolizí způsobené podřízené funkce nejsou zahrnuty. Výhradní čas pro funkci také obsahuje pouze dobu čekání, která byla způsobena příkazy v těle funkce.

Zobrazení sestav kolizí prostředku také obsahovat časová osa grafy, které se zobrazí jednotlivé kolizní události v čase a zobrazit zásobníky volání, které vytvořili určitá událost. Další informace naleznete v jednom z následujících témat:

- [Zobrazení podrobností o vláknu](../profiling/thread-details-view-contention-data.md)

- [Zobrazení podrobností o prostředku](../profiling/resource-details-view-contention-data.md)

Další informace o druhý režim profilace souběžného zpracování najdete v tématu [vizualizér souběžnosti](../profiling/concurrency-visualizer.md).