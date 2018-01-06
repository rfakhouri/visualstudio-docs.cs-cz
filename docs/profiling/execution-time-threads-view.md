---
title: "Doba spuštění (zobrazení vláken) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.execution
helpviewer_keywords: Concurrency Visualizer, Execution Time (Threads View)
ms.assetid: 80c100f8-2502-4613-bfef-4f4f2e09cc8d
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 91fda110b3bf73b59d7c9d7d8ff6f7226f9ec5fa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="execution-time-threads-view"></a>Doba spuštění (Zobrazení vláken)
Tyto segmenty v časová osa zobrazení vláken představují čas spuštění, když vlákno aktivně pracuje na logická jádra systému.  
  
 Změny ve stavu vlákno se zjišťují prostřednictvím událostí přepínač kontext jádra. Trasování událostí pro Windows (ETW) zachycuje ukázkových zásobníky každých milisekundu. Ve velmi krátké zelená segment je možné, že žádné vzorek. Proto některé segmenty krátké provádění může zobrazovat žádné zásobníku volání.  
  
 Po kliknutí na tlačítko segment provádění, zobrazí vizualizér souběžnosti nejblíže k umístění a klikněte na Ukázka zásobníku. Umístění tohoto balíku ukázka se zobrazí černou šipkou nebo pomocí kurzoru nad časovou osu a Ukázka zásobníku se zobrazí na **aktuální** kartě.  
  
 Chcete-li zobrazit profil tradiční vzorkování pro všechny segmenty provádění v aktuálním zobrazení, klikněte na tlačítko **provádění** v profil viditelné časové osy.  
  
## <a name="see-also"></a>Viz také  
 [Sestava profilu spuštění](../profiling/execution-profile-report.md)   
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)