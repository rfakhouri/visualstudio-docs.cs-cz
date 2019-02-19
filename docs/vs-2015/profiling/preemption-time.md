---
title: Čas přerušení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6fd209f65464126650106eb4509cd3de39ad8c25
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54752636"
---
# <a name="preemption-time"></a>Čas přerušení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tyto segmenty na časové ose jsou přidruženy k blokování čas, který je zařazený do kategorie jako přerušení. Tato kategorie znamená, že je vlákno přepnutí z jednoho z těchto důvodů:  
  
- Plánovač se nahrazuje použití vyšší priorita vlákna.  
  
- Kvantové doby provádění vlákna vypršela platnost a byly jiná vlákna připravená ke spuštění.  
  
  Během této doby je blokovaná společností Důvod čekání jádra, která Vizualizátor souběžnosti se počítá jako přerušení vlákna. Přerušení segmenty spustit, když vlákno je vložena mimo logické jádro a ukončit, pokud bylo vlákno pokračuje v provádění.  
  
  Popisek pro preempted segment zobrazuje název procesu nebo vlákna, která způsobila přerušení. Nicméně to neznamená, že proces nebo vlákno, které převzal skutečně spustila v průběhu preempted období.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)
