---
title: Aktivita GPU (stránkování) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuactivity
- vs.cv.threads.timeline.gpupaging
ms.assetid: 95284ac5-3492-4f7b-a79f-7d2840a07679
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 015fa34d2bb87cf98a64fb3431a6440202cf729b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49195855"
---
# <a name="gpu-activity-paging"></a>Aktivita GPU (stránkování)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Aktivita GPU (stránkování)** segmenty na kartě vlákna představují časy, kdy GPU zpracovává požadavky stránkování.  Délka segment, který představuje čas, GPU zpracování paket stránkování paměti přístup (DMA). Stránkování pakety jsou obvykle spojené s přenos paměti mezi CPU a GPU.  
  
 Když vyberete segment stránkování GPU sestavy na **aktuální** karta zobrazuje informace o paketu DMA, který byl zpracován. To zahrnuje množství času, které ho čekání ve frontě hardwaru, který je spojen s modul rozhraní DirectX, proces odeslání paketů DMA a čas, který je potřeba zpracovat paketu.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení využití](../profiling/utilization-view.md)



