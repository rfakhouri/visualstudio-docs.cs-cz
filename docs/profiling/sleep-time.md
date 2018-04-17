---
title: Doba spánku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 06a7d53eaaae7f59d8400d0aeaead6eab7a252ae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sleep-time"></a>Doba spánku
Tyto segmenty v časové ose jsou přidruženy k blokování čas, který je zařazen do režimu spánku. Kategorie režimu spánku znamená, že vlákno odpojit udělil si jeho logické jádra a je žádné pracuje. Během této doby je zablokovaný vlákna v rozhraní API, které je vizualizér souběžnosti počítání jako režimu spánku. Rozhraní API jako třeba `Sleep()` a `SwitchToThread()` do této skupiny patří.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)