---
title: Aktivita GPU (jiné procesy) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a3b0e97d82d67916aa71f932038930dba48c17e4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62434134"
---
# <a name="gpu-activity-other-processes"></a>Aktivita GPU (jiné procesy)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Aktivita GPU (jiné procesy)** segmenty v zobrazení vlákna Vizualizátor souběžnosti představují časy, kdy GPU zpracovává požadavky jménem jiných procesů v systému. Tyto požadavky jsou odesílány GPU jako pakety paměti (DMA) přístup.  Délka segment, který představuje časový interval, zpracování paketu GPU.  
  
 Když vyberete tento druh segmentu, sestavy na **aktuální** karta zobrazuje informace o paketu, který byl zpracován.  Tyto informace zahrnují množství času, které paket čekání ve frontě hardwaru, který je spojen s modul rozhraní DirectX, proces, který odešle paket a čas, který je potřebný ke zpracování paketu.
