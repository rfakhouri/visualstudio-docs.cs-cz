---
title: "Doba spánku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4385fd42c14d13e83f85683ef33a613fd6f78765
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sleep-time"></a>Doba spánku
Tyto segmenty v časové ose jsou přidruženy k blokování čas, který je zařazen do režimu spánku. Kategorie režimu spánku znamená, že vlákno odpojit udělil si jeho logické jádra a je žádné pracuje. Během této doby je zablokovaný vlákna v rozhraní API, které je vizualizér souběžnosti počítání jako režimu spánku. Rozhraní API jako třeba `Sleep()` a `SwitchToThread()` do této skupiny patří.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)