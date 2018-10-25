---
title: Čas přerušení | Dokumentace Microsoftu
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
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f302dff3ea72217c6325aca667aec8ff4d7f218f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49905230"
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



