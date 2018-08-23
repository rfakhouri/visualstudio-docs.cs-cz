---
title: Čas správy paměti | Dokumentace Microsoftu
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
- vs.cv.threads.timeline.paging
helpviewer_keywords:
- Concurrency Visualizer, Paging Time
ms.assetid: 67af3509-3a7d-435d-bc37-5262448da915
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9371c4d5249539c80299fd1b1573eba19c9dd14f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627405"
---
# <a name="memory-management-time"></a>Čas správy paměti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [čas správy paměti](https://docs.microsoft.com/visualstudio/profiling/memory-management-time).  
  
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako správa paměti. Z toho vyplývá, že událost, ke které je přidružený k operaci správy paměti, jako je například stránkování blokuje vlákno. Během této doby je zablokovaný vlákno ve stavu rozhraní API nebo jádra, která Vizualizátor souběžnosti se počítá jako správa paměti. Mezi ně patří události, například stránkování a přidělování paměti.  
  
 Podívejte se na související volání zásobníků a profilu, sestavy pro lepší pochopení základní příčiny bloky, které jsou klasifikovány jako správa paměti.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)



