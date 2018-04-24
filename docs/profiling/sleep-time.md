---
title: Doba spánku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0b9a3894097c553d8505fd61f15fbdec8c188e79
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="sleep-time"></a>Doba spánku
Tyto segmenty v časové ose jsou přidruženy k blokování čas, který je zařazen do režimu spánku. Kategorie režimu spánku znamená, že vlákno odpojit udělil si jeho logické jádra a je žádné pracuje. Během této doby je zablokovaný vlákna v rozhraní API, které je vizualizér souběžnosti počítání jako režimu spánku. Rozhraní API jako třeba `Sleep()` a `SwitchToThread()` do této skupiny patří.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)