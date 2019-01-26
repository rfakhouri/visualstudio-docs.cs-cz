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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 98917d9f0492a59b832d9e91da8f8e16059faae9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54948788"
---
# <a name="gpu-activity-paging"></a>Aktivita GPU (stránkování)
**Aktivita GPU (stránkování)** segmenty na **vlákna** kartě představují časy, kdy GPU zpracovává požadavky stránkování.  Délka segment, který představuje čas, GPU zpracování paket stránkování paměti přístup (DMA). Stránkování pakety jsou obvykle spojené s přenos paměti mezi CPU a GPU.  
  
 Když vyberete segment stránkování GPU sestavy na **aktuální** karta zobrazuje informace o paketu DMA, který byl zpracován. To zahrnuje množství času, které ho čekání ve frontě hardwaru, který je spojen s modul rozhraní DirectX, proces odeslání paketů DMA a čas, který je potřeba zpracovat paketu.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení využití](../profiling/utilization-view.md)