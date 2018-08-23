---
title: Čas I/o (zobrazení vláken) | Dokumentace Microsoftu
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
- vs.cv.threads.timeline.io
helpviewer_keywords:
- Concurrency Visualizer, I/O time (Threads View)
ms.assetid: 0c4ec14d-d8dd-49c1-999c-dcbf4e8e1dc8
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d25512da43fc32b42c2a1f79e3c8dbe992ea30ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675898"
---
# <a name="io-time-threads-view"></a>Čas I/O (Zobrazení vláken)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [i/o (zobrazení vláken) čas](https://docs.microsoft.com/visualstudio/profiling/i-o-time-threads-view).  
  
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako vstupně-výstupních operací. To znamená, že vlákno čeká na dokončení operace vstupně-výstupních operací. Vlákno může mít zablokovaný v rozhraní API, nebo I O souvisejícím s/jádra čekání, který Vizualizátor souběžnosti se počítá jako vstupně-výstupních operací. Rozhraní API, jako `CreateFile()`, `ReadFile()`, a `WSARecv()` spadají do této skupiny.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)



