---
title: Doba spuštění (zobrazení vláken) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Time (Threads View)
ms.assetid: 80c100f8-2502-4613-bfef-4f4f2e09cc8d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bce4b4e5c0d4a9d4f66fade6b01044ac149968a0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="execution-time-threads-view"></a>Doba spuštění (Zobrazení vláken)
Tyto segmenty v časová osa zobrazení vláken představují čas spuštění, když vlákno aktivně pracuje na logická jádra systému.  
  
 Změny ve stavu vlákno se zjišťují prostřednictvím událostí přepínač kontext jádra. Trasování událostí pro Windows (ETW) zachycuje ukázkových zásobníky každých milisekundu. Ve velmi krátké zelená segment je možné, že žádné vzorek. Proto některé segmenty krátké provádění může zobrazovat žádné zásobníku volání.  
  
 Po kliknutí na tlačítko segment provádění, zobrazí vizualizér souběžnosti nejblíže k umístění a klikněte na Ukázka zásobníku. Umístění tohoto balíku ukázka se zobrazí černou šipkou nebo pomocí kurzoru nad časovou osu a Ukázka zásobníku se zobrazí na **aktuální** kartě.  
  
 Chcete-li zobrazit profil tradiční vzorkování pro všechny segmenty provádění v aktuálním zobrazení, klikněte na tlačítko **provádění** v profil viditelné časové osy.  
  
## <a name="see-also"></a>Viz také  
 [Sestava profilu spuštění](../profiling/execution-profile-report.md)   
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)