---
title: Čas synchronizace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.synchronization
helpviewer_keywords:
- Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ae73f7b9a9838a006dce47bf44b0ed46aa0b84fa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62965307"
---
# <a name="synchronization-time"></a>Čas synchronizace
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako synchronizace. Pokud vlákno je označena jako blokováno při synchronizaci, je vyjádřena jednu z těchto věcí:

- Provádění vlákna bylo pravděpodobně způsobeno při volání k synchronizaci dobře známé vlákno rozhraní API, jako `EnterCriticalSection()` nebo `WaitForSingleObject()`.

- Porovnávací algoritmus rozhraní API nemůže být zcela komplexní, a proto některá rozhraní API, která by mohla být namapovány na jiných kategorií může také dojít, protože synchronizace, protože rámce při volání funkce zásobníku nakonec dosažena základní jádra blokování primitivní, který byl mapovat do této kategorie.

  Informace o tom základní příčinu události blokování vlákna, pečlivě zkontrolujte blokování zásobníky volání a profilu, sestavy.

## <a name="see-also"></a>Viz také:
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)