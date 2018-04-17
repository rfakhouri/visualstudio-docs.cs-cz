---
title: Aktivita GPU (Tento proces) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44d676fc69142e0ab8de4f63637b81578a0e2a00
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="gpu-activity-this-process"></a>Aktivita GPU (tento proces)
**Aktivita GPU (Tento proces)** segmentů v zobrazení vláken v Concurrency Visualizer představují dobu, kdy GPU zpracovává požadavky jménem aktuální proces. Tyto požadavky jsou odesílány GPU v paměti přímý přístup (DMA) paketů. Délka segment představuje čas, že GPU zpracovává paket DMA jménem aktuálním procesu.  
  
 Když vyberete segmentu aktivity GPU sestavy na **aktuální** karta zobrazuje informace o DMA paketu, který byl zpracován. Tyto informace zahrnují množství času, který paketu čekali ve frontě hardwaru, který je spojen s modul DirectX, proces, který odeslal paketu a čas, které je nutné zpracovat paketu. Proces než aktuální proces může mít fyzicky odeslat paket DMA na grafický procesor. Vizualizér souběžnosti může rozpoznat, kdy se jiný proces odeslání pracovní na grafický procesor s jménem aktuálním procesu.