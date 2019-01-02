---
title: Čas správy paměti | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.paging
helpviewer_keywords:
- Concurrency Visualizer, Paging Time
ms.assetid: 67af3509-3a7d-435d-bc37-5262448da915
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6741aa96941e9265ab414ea7d73bb614ace6f9b8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53913954"
---
# <a name="memory-management-time"></a>Čas správy paměti
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako správa paměti. Tento scénář znamená, že událost, ke které je přidružený k operaci správy paměti, jako je například stránkování blokuje vlákno. Během této doby je zablokovaný vlákno ve stavu rozhraní API nebo jádra, která Vizualizátor souběžnosti se počítá jako správa paměti. Mezi ně patří události, například stránkování a přidělování paměti.  
  
 Podívejte se na související volání zásobníků a profilu, sestavy pro lepší pochopení základní příčiny bloky, které jsou klasifikovány jako správa paměti.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)