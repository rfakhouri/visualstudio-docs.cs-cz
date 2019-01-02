---
title: Aktivita GPU (jiné procesy) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 570e5d313b6246903f5e6a931b10f33fa40bf3ac
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53913407"
---
# <a name="gpu-activity-other-processes"></a>Aktivita GPU (jiné procesy)
**Aktivita GPU (jiné procesy)** segmenty v zobrazení vlákna Vizualizátor souběžnosti představují časy, kdy GPU zpracovává požadavky jménem jiných procesů v systému. Tyto požadavky jsou odesílány GPU jako pakety paměti (DMA) přístup.  Délka segment, který představuje časový interval, zpracování paketu GPU.  
  
 Když vyberete tento druh segmentu, sestavy na **aktuální** karta zobrazuje informace o paketu, který byl zpracován.  Tyto informace zahrnují množství času, které paket čekání ve frontě hardwaru, který je spojen s modul rozhraní DirectX, proces, který odešle paket a čas, který je potřebný ke zpracování paketu.