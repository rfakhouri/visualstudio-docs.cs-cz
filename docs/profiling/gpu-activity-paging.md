---
title: Aktivita GPU (stránkování) | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: 919f99ad24764017e823dbceda51bec4461401e4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53942720"
---
# <a name="gpu-activity-paging"></a>Aktivita GPU (stránkování)
**Aktivita GPU (stránkování)** segmenty na **vlákna** kartě představují časy, kdy GPU zpracovává požadavky stránkování.  Délka segment, který představuje čas, GPU zpracování paket stránkování paměti přístup (DMA). Stránkování pakety jsou obvykle spojené s přenos paměti mezi CPU a GPU.  
  
 Když vyberete segment stránkování GPU sestavy na **aktuální** karta zobrazuje informace o paketu DMA, který byl zpracován. To zahrnuje množství času, které ho čekání ve frontě hardwaru, který je spojen s modul rozhraní DirectX, proces odeslání paketů DMA a čas, který je potřeba zpracovat paketu.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení využití](../profiling/utilization-view.md)