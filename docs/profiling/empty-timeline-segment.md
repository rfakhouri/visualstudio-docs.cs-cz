---
title: Prázdný Segment časové osy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.empty
helpviewer_keywords:
- Concurrency Visualizer, empty timeline segment
ms.assetid: f37b301f-3edc-4e56-8084-feec2dc5a9b1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 122eb98fcac3bd03d3a4043399cb31041bab52f5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="empty-timeline-segment"></a>Prázdný segment časové osy
V Concurrency Visualizer, důvod, proč části časové osy je prázdná (má bílé pozadí) závisí na druhu kanálu.  
  
-   Pro přístup z více vláken kanál procesoru znamená to, že vlákno neexistoval během této části časovou osu. Pokud vás zajímá vlákno, najdete jeho provádění části pomocí ovládacího prvku Zvětšení nebo posouvání vodorovně.  
  
-   Pro vstupně-výstupního kanálu znamená to, že žádný přístup k disku došlo k chybě jménem tento cílový proces v tomto bodě v čase.  
  
-   Pro kanál DirectX znamená to, že žádná práce GPU byla provedena jménem tento cílový proces během této části časovou osu.  
  
-   Pro kanál značky to znamená, že byly vygenerovány žádné značky.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)   
 [Ovládací prvek Lupa (Zobrazení vláken)](../profiling/zoom-control-threads-view.md)