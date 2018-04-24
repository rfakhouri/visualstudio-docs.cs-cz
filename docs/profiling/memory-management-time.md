---
title: Čas správy paměti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 80d7ddfcc220d858cfaa24b1e817f1e41c9ed734
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="memory-management-time"></a>Čas správy paměti
Tyto segmenty v časové ose jsou přidruženy k blokování pokusů, které jsou klasifikovány jako správa paměti. Z toho vyplývá, že vlákno je blokována událost, která souvisí s operací správy paměti jako je například stránkování. Během této doby je ve stavu rozhraní API nebo jádra, který je jako správa paměti počítání vizualizér souběžnosti zablokovaný vlákna. Mezi ně patří události, jako je například přidělení stránkování a paměti.  
  
 Zkontrolujte přidružené volání zásobníky a profilu, sestavy pro lepší pochopení základní příčiny bloků, které jsou klasifikovány jako správa paměti.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)