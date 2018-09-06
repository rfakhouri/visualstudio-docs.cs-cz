---
title: Čas synchronizace | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.synchronization
helpviewer_keywords:
- Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f3236530c1a7b92fd1cba1bdd61e3e1c0973b58c
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/06/2018
ms.locfileid: "35675875"
---
# <a name="synchronization-time"></a>Čas synchronizace
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako synchronizace. Pokud vlákno je označena jako blokováno při synchronizaci, je vyjádřena jednu z těchto věcí:  
  
-   Provádění vlákna bylo pravděpodobně způsobeno při volání k synchronizaci dobře známé vlákno rozhraní API, jako `EnterCriticalSection()` nebo `WaitForSingleObject()`.  
  
-   Porovnávací algoritmus rozhraní API nemůže být zcela komplexní, a proto některá rozhraní API, která by mohla být namapovány na jiných kategorií může také dojít, protože synchronizace, protože rámce při volání funkce zásobníku nakonec dosažena základní jádra blokování primitivní, který byl mapovat do této kategorie.  
  
 Informace o tom základní příčinu události blokování vlákna, pečlivě zkontrolujte blokování zásobníky volání a profilu, sestavy.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)