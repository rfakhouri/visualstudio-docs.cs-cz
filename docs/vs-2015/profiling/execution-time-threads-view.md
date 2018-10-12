---
title: Doba spuštění (zobrazení vláken) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Time (Threads View)
ms.assetid: 80c100f8-2502-4613-bfef-4f4f2e09cc8d
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14e873196767c295ea3f333bbf8ef5217dc79d44
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49251197"
---
# <a name="execution-time-threads-view"></a>Doba spuštění (Zobrazení vláken)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tyto segmenty na časové ose zobrazení vláken představují doby spuštění, když vlákno aktivně pracuje na logické jádro v systému.  
  
 Události přepínače kontext jádra jsou zjištěné změny stavu vlákna. Trasování událostí pro Windows (ETW) zachycuje ukázka zásobníky každý milisekund. Ve velmi krátké zelený segment je možné, že žádné vzorek. Některé krátký spouštěcí segmenty proto může zobrazit žádný zásobník volání.  
  
 Když kliknete segment provádění, Vizualizátor souběžnosti zobrazí nejblíže k umístění kliknutím na Ukázka zásobníku. Umístění tohoto balíku ukázka zobrazí černé šipky, nebo se zobrazí blikající kurzor nad časovou osu a Ukázka zásobníku na **aktuální** kartu.  
  
 Chcete-li zobrazit profil tradiční vzorkování pro všechny spouštěcí segmenty v aktuálním zobrazení, klikněte na tlačítko **provádění** v profil viditelné časové osy.  
  
## <a name="see-also"></a>Viz také  
 [Sestava profilu spuštění](../profiling/execution-profile-report.md)   
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)



