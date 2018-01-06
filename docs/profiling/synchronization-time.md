---
title: "Čas synchronizace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.synchronization
helpviewer_keywords: Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8252bc569ef17725570b5222afa12a59c387c278
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="synchronization-time"></a>Čas synchronizace
Tyto segmenty v časové ose jsou přidruženy k blokování pokusů, které jsou klasifikovány jako synchronizace. Když vlákno je označený jako blokované při synchronizaci, je implicitní jednu z těchto věcí:  
  
-   Spuštění podprocesu bylo pravděpodobně způsobeno v volání synchronizace dobře známé vláken rozhraní API, jako `EnterCriticalSection()` nebo `WaitForSingleObject()`.  
  
-   Algoritmus odpovídající rozhraní API nemůže být zcela komplexní, a proto některé rozhraní API, který může být namapovaný na ostatních kategorií může také zobrazit jako synchronizace, protože rámce ve volání zásobníku nakonec dosažen základní jádra blokování primitivní, který byl mapovat na tuto kategorii.  
  
 Abyste pochopili základní příčinu události blokující přístup z více vláken, pečlivě zkontrolujte blokování zásobníky volání a profilu, sestavy.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)