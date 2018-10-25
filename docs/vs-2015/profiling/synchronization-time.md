---
title: Čas synchronizace | Dokumentace Microsoftu
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
- vs.cv.threads.timeline.synchronization
helpviewer_keywords:
- Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12be885a79daa3ba5531f6da9652d6a9708b3c96
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49826996"
---
# <a name="synchronization-time"></a>Čas synchronizace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako synchronizace. Pokud vlákno je označena jako blokováno při synchronizaci, je vyjádřena jednu z těchto věcí:  
  
- Provádění vlákna bylo pravděpodobně způsobeno při volání k synchronizaci dobře známé vlákno rozhraní API, jako `EnterCriticalSection()` nebo `WaitForSingleObject()`.  
  
- Porovnávací algoritmus rozhraní API nemůže být zcela komplexní, a proto některá rozhraní API, která by mohla být namapovány na jiných kategorií může také dojít, protože synchronizace, protože rámce při volání funkce zásobníku nakonec dosažena základní jádra blokování primitivní, který byl mapovat do této kategorie.  
  
  Informace o tom základní příčinu události blokování vlákna, pečlivě zkontrolujte blokování zásobníky volání a profilu, sestavy.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)



