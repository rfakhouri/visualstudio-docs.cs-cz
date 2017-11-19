---
title: Aktivita GPU (Tento proces) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 255a1ff62d4f9c444169e1330dcd11eb8e1030ed
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="gpu-activity-this-process"></a>Aktivita GPU (tento proces)
**Aktivita GPU (Tento proces)** segmentů v zobrazení vláken v Concurrency Visualizer představují dobu, kdy GPU zpracovává požadavky jménem aktuální proces. Tyto požadavky jsou odesílány GPU v paměti přímý přístup (DMA) paketů. Délka segment představuje čas, že GPU zpracovává paket DMA jménem aktuálním procesu.  
  
 Když vyberete segmentu aktivity GPU sestavy na **aktuální** karta zobrazuje informace o DMA paketu, který byl zpracován. Tyto informace zahrnují množství času, který paketu čekali ve frontě hardwaru, který je spojen s modul DirectX, proces, který odeslal paketu a čas, které je nutné zpracovat paketu. Proces než aktuální proces může mít fyzicky odeslat paket DMA na grafický procesor. Vizualizér souběžnosti může rozpoznat, kdy se jiný proces odeslání pracovní na grafický procesor s jménem aktuálním procesu.