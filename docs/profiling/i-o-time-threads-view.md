---
title: Čas I/o (zobrazení vláken) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.io
helpviewer_keywords:
- Concurrency Visualizer, I/O time (Threads View)
ms.assetid: 0c4ec14d-d8dd-49c1-999c-dcbf4e8e1dc8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d7ba29383ddddc02160967a90b56046128d2f19
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56625449"
---
# <a name="io-time-threads-view"></a>čas I/O (zobrazení vláken)
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako vstupně-výstupních operací. To znamená, že vlákno čeká na dokončení operace vstupně-výstupních operací. Vlákno může mít zablokovaný v rozhraní API, nebo I O souvisejícím s/jádra čekání, který Vizualizátor souběžnosti se počítá jako vstupně-výstupních operací. Rozhraní API, jako `CreateFile()`, `ReadFile()`, a `WSARecv()` spadají do této skupiny.

## <a name="see-also"></a>Viz také:
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)