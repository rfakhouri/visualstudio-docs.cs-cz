---
title: Aktivita GPU (stránkování) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuactivity
- vs.cv.threads.timeline.gpupaging
ms.assetid: 95284ac5-3492-4f7b-a79f-7d2840a07679
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 822b65309d1db2423b3c5798c51db6c9631bf835
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="gpu-activity-paging"></a>Aktivita GPU (stránkování)
**Aktivita GPU (stránkování)** segmenty na kartě vláken představují dobu, kdy GPU zpracovává požadavky stránkování.  Délka segment představuje doba, aby byl na grafický procesor s zpracování paket stránkování paměti přímý přístup (DMA). Obvykle jsou přidruženy k přenosu paměti mezi procesoru a GPU stránkování paketů.  
  
 Když vyberete segment stránkování GPU sestavy na **aktuální** karta zobrazuje informace o DMA paketu, který byl zpracován. To zahrnuje množství času, který ho čekali ve frontě hardwaru, který je spojen s modul DirectX, proces, který odeslal paket DMA a čas, které je nutné zpracovat paketu.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení využití](../profiling/utilization-view.md)