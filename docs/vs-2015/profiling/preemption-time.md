---
title: Čas přerušení | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 614b049bf7aa881ce4454d8f832190b0391ff342
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676080"
---
# <a name="preemption-time"></a>Čas přerušení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [čas přerušení](https://docs.microsoft.com/visualstudio/profiling/preemption-time).  
  
Tyto segmenty na časové ose jsou přidruženy k blokování čas, který je zařazený do kategorie jako přerušení. Tato kategorie znamená, že je vlákno přepnutí z jednoho z těchto důvodů:  
  
-   Plánovač se nahrazuje použití vyšší priorita vlákna.  
  
-   Kvantové doby provádění vlákna vypršela platnost a byly jiná vlákna připravená ke spuštění.  
  
 Během této doby je blokovaná společností Důvod čekání jádra, která Vizualizátor souběžnosti se počítá jako přerušení vlákna. Přerušení segmenty spustit, když vlákno je vložena mimo logické jádro a ukončit, pokud bylo vlákno pokračuje v provádění.  
  
 Popisek pro preempted segment zobrazuje název procesu nebo vlákna, která způsobila přerušení. Nicméně to neznamená, že proces nebo vlákno, které převzal skutečně spustila v průběhu preempted období.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)



