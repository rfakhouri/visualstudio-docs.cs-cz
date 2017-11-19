---
title: "Čas I-O (zobrazení vláken) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.io
helpviewer_keywords: Concurrency Visualizer, I/O time (Threads View)
ms.assetid: 0c4ec14d-d8dd-49c1-999c-dcbf4e8e1dc8
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d53cfcf4daa5e1ac1129230884684692867b121d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="io-time-threads-view"></a>Čas I/O (Zobrazení vláken)
Tyto segmenty v časové ose jsou přidruženy k blokování pokusů, které jsou klasifikovány jako vstupně-výstupní operace. To znamená, že vlákno čeká na dokončení vstupně-výstupní operace. Vlákno může mít zablokovaný v rozhraní API, nebo čekání I/E-související jádra, která jako vstupně-výstupních operací je počítání vizualizér souběžnosti. Rozhraní API jako třeba `CreateFile()`, `ReadFile()`, a `WSARecv()` do této skupiny patří.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)