---
title: Aktivita GPU (jiné procesy) | Dokumentace Microsoftu
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
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 94076c392223fb38d98c1c20b68cf76507955715
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671959"
---
# <a name="gpu-activity-other-processes"></a>Aktivita GPU (jiné procesy)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [aktivita GPU (jiné procesy)](https://docs.microsoft.com/visualstudio/profiling/gpu-activity-other-processes).  
  
**Aktivita GPU (jiné procesy)** segmenty v zobrazení vlákna Vizualizátor souběžnosti představují časy, kdy GPU zpracovává požadavky jménem jiných procesů v systému. Tyto požadavky jsou odesílány GPU jako pakety paměti (DMA) přístup.  Délka segment, který představuje časový interval, zpracování paketu GPU.  
  
 Když vyberete tento druh segmentu, sestavy na **aktuální** karta zobrazuje informace o paketu, který byl zpracován.  Tyto informace zahrnují množství času, které paket čekání ve frontě hardwaru, který je spojen s modul rozhraní DirectX, proces, který odešle paket a čas, který je potřebný ke zpracování paketu.



