---
title: Čas I-O (zobrazení vláken) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.io
helpviewer_keywords:
- Concurrency Visualizer, I/O time (Threads View)
ms.assetid: 0c4ec14d-d8dd-49c1-999c-dcbf4e8e1dc8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e50301149f844e0063deeb970e5bfb5bd46a55c1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="io-time-threads-view"></a>Čas I/O (Zobrazení vláken)
Tyto segmenty v časové ose jsou přidruženy k blokování pokusů, které jsou klasifikovány jako vstupně-výstupní operace. To znamená, že vlákno čeká na dokončení vstupně-výstupní operace. Vlákno může mít zablokovaný v rozhraní API, nebo čekání I/E-související jádra, která jako vstupně-výstupních operací je počítání vizualizér souběžnosti. Rozhraní API jako třeba `CreateFile()`, `ReadFile()`, a `WSARecv()` do této skupiny patří.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)