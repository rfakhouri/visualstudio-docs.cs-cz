---
title: Aktivita GPU (Tento proces) | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: a6ba732650d1415c59769ef2a5f0b5604b701c57
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53876702"
---
# <a name="gpu-activity-this-process"></a>Aktivita GPU (tento proces)
**Aktivita GPU (Tento proces)** segmenty v zobrazení vláken ve vizualizátoru souběžnosti představují časy, kdy GPU zpracovává požadavky jménem aktuální proces. Tyto požadavky se odesílají do GPU jako pakety paměti (DMA) přístup. Délka segment, který představuje čas, GPU zpracování paketů DMA jménem aktuální proces.  
  
 Když vyberete na segment aktivity GPU, sestava **aktuální** karta zobrazuje informace o paketu DMA, který byl zpracován. Tyto informace zahrnují množství času, které paket čekání ve frontě hardwaru, který je spojen s modul rozhraní DirectX, proces, který odešle paket a čas, který je potřebný ke zpracování paketu. Procesu než aktuální proces může fyzicky odeslání paketů DMA do GPU. Vizualizátor souběžnosti lze rozpoznat, kdy se jiný proces odeslání práce GPU jménem aktuální proces.