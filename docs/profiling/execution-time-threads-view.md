---
title: Doba spuštění (zobrazení vláken) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Time (Threads View)
ms.assetid: 80c100f8-2502-4613-bfef-4f4f2e09cc8d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 231c39b739e7d508fe01857d8388201929ec00db
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54945850"
---
# <a name="execution-time-threads-view"></a>Doba spuštění (zobrazení vláken)
Tyto segmenty na časové ose zobrazení vláken představují doby spuštění, když vlákno aktivně pracuje na logické jádro v systému.  
  
 Události přepínače kontext jádra jsou zjištěné změny stavu vlákna. Trasování událostí pro Windows (ETW) zachycuje ukázka zásobníky každý milisekund. Ve velmi krátké zelený segment je možné, že žádné vzorek. Některé krátký spouštěcí segmenty proto může zobrazit žádný zásobník volání.  
  
 Když kliknete segment provádění, Vizualizátor souběžnosti zobrazí nejblíže k umístění kliknutím na Ukázka zásobníku. Umístění tohoto balíku ukázka zobrazí černé šipky, nebo se zobrazí blikající kurzor nad časovou osu a Ukázka zásobníku na **aktuální** kartu.  
  
 Chcete-li zobrazit profil tradiční vzorkování pro všechny spouštěcí segmenty v aktuálním zobrazení, klikněte na tlačítko **provádění** v profil viditelné časové osy.  
  
## <a name="see-also"></a>Viz také:  
 [Sestava profilu spuštění](../profiling/execution-profile-report.md)   
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)