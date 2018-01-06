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
ms.workload: multiple
ms.openlocfilehash: abea2c5ed246fe3463205894326a7f9611b56043
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="io-time-threads-view"></a>Čas I/O (Zobrazení vláken)
Tyto segmenty v časové ose jsou přidruženy k blokování pokusů, které jsou klasifikovány jako vstupně-výstupní operace. To znamená, že vlákno čeká na dokončení vstupně-výstupní operace. Vlákno může mít zablokovaný v rozhraní API, nebo čekání I/E-související jádra, která jako vstupně-výstupních operací je počítání vizualizér souběžnosti. Rozhraní API jako třeba `CreateFile()`, `ReadFile()`, a `WSARecv()` do této skupiny patří.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)