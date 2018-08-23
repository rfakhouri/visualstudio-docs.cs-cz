---
title: Čas synchronizace | Dokumentace Microsoftu
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
- vs.cv.threads.timeline.synchronization
helpviewer_keywords:
- Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b1ca6b7a0d6e7f7c3be41bb091674a3526edf53
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675707"
---
# <a name="synchronization-time"></a>Čas synchronizace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [čas synchronizace](https://docs.microsoft.com/visualstudio/profiling/synchronization-time).  
  
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako synchronizace. Pokud vlákno je označena jako blokováno při synchronizaci, je vyjádřena jednu z těchto věcí:  
  
-   Provádění vlákna bylo pravděpodobně způsobeno při volání k synchronizaci dobře známé vlákno rozhraní API, jako `EnterCriticalSection()` nebo `WaitForSingleObject()`.  
  
-   Porovnávací algoritmus rozhraní API nemůže být zcela komplexní, a proto některá rozhraní API, která by mohla být namapovány na jiných kategorií může také dojít, protože synchronizace, protože rámce při volání funkce zásobníku nakonec dosažena základní jádra blokování primitivní, který byl mapovat do této kategorie.  
  
 Informace o tom základní příčinu události blokování vlákna, pečlivě zkontrolujte blokování zásobníky volání a profilu, sestavy.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)



