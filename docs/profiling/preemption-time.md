---
title: Čas přerušení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7ac7152ec663a0a7b7bbbeee5c30a38885623cb9
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254756"
---
# <a name="preemption-time"></a>Čas přerušení
Tyto segmenty v časové ose jsou přidruženy k blokování čas, který je zařazený do kategorie jako předkupní. Tuto kategorii znamená, že vlákno je přepnuta se z jednoho z těchto důvodů:  
  
-   Plánovač ho nahradit pomocí vyšší priorita vlákna.  
  
-   Quantum provádění vlákna platnost a byly jiná vlákna připravena ke spouštění.  
  
 Během této doby vlákno zablokoval z důvodu čekání jádra, který je jako předkupní počítání vizualizér souběžnosti. Segmenty předkupní spustit v případě, že vlákno se posune mimo logická jádra a koncovou při daném vláknu obnoví spuštění.  
  
 Popisek pro segment zrušeny zobrazí název procesu nebo vláken, která způsobila, že předkupní. Ale to neznamená, že proces nebo podproces, který převzal ve skutečnosti spustili po celou dobu preempted.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)