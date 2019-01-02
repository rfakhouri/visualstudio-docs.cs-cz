---
title: Prázdný Segment časové osy | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: a3411de6fbc4d30f3b8dcb3dbe7a8eeba12e8ad9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53959365"
---
# <a name="empty-timeline-segment"></a>Prázdný segment časové osy
Ve Vizualizátor souběžnosti, proč se části časové osy je prázdný (má bílé pozadí) závisí na typu vašeho kanálu.  
  
-   Pro kanál vlákna CPU znamená to, že vlákno neexistoval při tuto část časové osy. Pokud vás zajímá ve vlákně, najdete jeho provádění části pomocí ovládacího prvku přiblížení nebo posouvání vodorovně.  
  
-   Pro kanál vstupně-výstupních operací znamená to, že žádný přístup k disku došlo k jménem Cílový proces od tohoto okamžiku v čase.  
  
-   Pro kanál rozhraní DirectX znamená to, že se žádná práce GPU provedla jménem Cílový proces během této části časové osy.  
  
-   Pro značky kanál znamená to, že nevygenerovaly se žádné značky.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)   
 [Ovládací prvek Lupa (zobrazení vláken)](../profiling/zoom-control-threads-view.md)