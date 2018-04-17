---
title: Čas I-O (zobrazení vláken) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 070e47d42b5d00058480cf5c4f94437855bfd80b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="io-time-threads-view"></a>Čas I/O (Zobrazení vláken)
Tyto segmenty v časové ose jsou přidruženy k blokování pokusů, které jsou klasifikovány jako vstupně-výstupní operace. To znamená, že vlákno čeká na dokončení vstupně-výstupní operace. Vlákno může mít zablokovaný v rozhraní API, nebo čekání I/E-související jádra, která jako vstupně-výstupních operací je počítání vizualizér souběžnosti. Rozhraní API jako třeba `CreateFile()`, `ReadFile()`, a `WSARecv()` do této skupiny patří.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)