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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 442973edb18e75bafda8a9397eac799286c69dfa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963778"
---
# <a name="memory-management-time"></a>Čas správy paměti
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako správa paměti. Tento scénář znamená, že událost, ke které je přidružený k operaci správy paměti, jako je například stránkování blokuje vlákno. Během této doby je zablokovaný vlákno ve stavu rozhraní API nebo jádra, která Vizualizátor souběžnosti se počítá jako správa paměti. Mezi ně patří události, například stránkování a přidělování paměti.

 Podívejte se na související volání zásobníků a profilu, sestavy pro lepší pochopení základní příčiny bloky, které jsou klasifikovány jako správa paměti.

## <a name="see-also"></a>Viz také:
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)