---
title: "Čas přerušení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0ee0f1be5d687c145bc2c8af448b30ec364df2f7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="preemption-time"></a>Čas přerušení
Tyto segmenty v časové ose jsou přidruženy k blokování čas, který je zařazený do kategorie jako přerušení. Tuto kategorii znamená, že vlákno je přepnuta se z jednoho z těchto důvodů:  
  
-   Plánovač ho nahradit pomocí vyšší priorita vlákna.  
  
-   Quantum provádění vlákna platnost a byly jiná vlákna připravena ke spouštění.  
  
 Během této doby vlákno zablokoval z důvodu čekání jádra, který je jako přerušování počítání vizualizér souběžnosti. Přerušování segmenty spustit v případě, že vlákno se posune mimo logická jádra a koncovou při daném vláknu obnoví spuštění.  
  
 Popisek pro preempted segment zobrazí název procesu nebo vláken, která způsobila, že přerušení. Ale to neznamená, že proces nebo podproces, který převzal ve skutečnosti spustili po celou dobu preempted.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)