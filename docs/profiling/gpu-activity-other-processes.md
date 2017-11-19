---
title: "Aktivita GPU (jiné procesy) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b32ee2967ccc4a7cf1f02935a58cfff5c9e8a33
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="gpu-activity-other-processes"></a>Aktivita GPU (jiné procesy)
**Aktivita GPU (jiné procesy)** segmentů v zobrazení vláken vizualizér souběžnosti představují dobu, kdy GPU zpracovává požadavky jménem jiné procesy v systému. Tyto požadavky jsou odesílány GPU v paměti přímý přístup (DMA) paketů.  Délka segment představuje dobu trvání čas, který byl zpracován paketu GPU.  
  
 Když vyberete tento druh segmentu, sestavy na **aktuální** karta zobrazuje informace o paketu, který byl zpracován.  Informace zahrnují množství času, který paketu čekali ve frontě hardwaru, který je spojen s modul DirectX, proces, který odeslal paketu a čas, které je nutné zpracovat paketu.