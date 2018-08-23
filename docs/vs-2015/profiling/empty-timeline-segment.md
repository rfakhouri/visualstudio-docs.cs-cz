---
title: Prázdný Segment časové osy | Dokumentace Microsoftu
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
- vs.cv.threads.timeline.empty
helpviewer_keywords:
- Concurrency Visualizer, empty timeline segment
ms.assetid: f37b301f-3edc-4e56-8084-feec2dc5a9b1
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3002888730ae785d741e7274d6262d23db0faa35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669197"
---
# <a name="empty-timeline-segment"></a>Prázdný segment časové osy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [prázdný Segment časové osy](https://docs.microsoft.com/visualstudio/profiling/empty-timeline-segment).  
  
Ve Vizualizátor souběžnosti, proč se části časové osy je prázdný (má bílé pozadí) závisí na typu vašeho kanálu.  
  
-   Pro kanál vlákna CPU znamená to, že vlákno neexistoval při tuto část časové osy. Pokud vás zajímá ve vlákně, najdete jeho provádění části pomocí ovládacího prvku přiblížení nebo posouvání vodorovně.  
  
-   Pro kanál vstupně-výstupních operací znamená to, že žádný přístup k disku došlo k jménem Cílový proces od tohoto okamžiku v čase.  
  
-   Pro kanál rozhraní DirectX znamená to, že se žádná práce GPU provedla jménem Cílový proces během této části časové osy.  
  
-   Pro značky kanál znamená to, že nevygenerovaly se žádné značky.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)   
 [Ovládací prvek Lupa (Zobrazení vláken)](../profiling/zoom-control-threads-view.md)



