---
title: "Doba zpracování uživatelského rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.uiprocessing
helpviewer_keywords: Concurrency Visualizer, UI Processing Time
ms.assetid: 0ddb05a3-8c6b-448b-8488-2751c1e5abcc
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8171fa96848aa53fb151ed4d4701268308e4ad1c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ui-processing-time"></a>Doba zpracování uživatelského rozhraní
Tyto segmenty v časové ose jsou přidruženy k blokování pokusů, které jsou klasifikovány jako zpracování uživatelského rozhraní. To znamená, že je čerpání zpráv systému Windows nebo provádění jiných uživatelské rozhraní (UI) pracovní vlákno. Během této doby je zablokovaný vlákna v rozhraní API, které je vizualizér souběžnosti počítání jako zpracování uživatelského rozhraní. Rozhraní API jako třeba `GetMessage()` a `MsgWaitForMultipleObjects()` do této skupiny patří.  
  
 Pokud se identifikuje žádné předdefinované blokování rozhraní API, zkontrolujte zásobníky volání a profilu, sestavy určit základní příčiny zpoždění.  
  
 Kategorie zpracování uživatelského rozhraní je důležité porozumět tomu, rychlost odezvy aplikací grafického uživatelského rozhraní a je žádoucí v aplikacích, které jsou závislé na odezvy uživatelského rozhraní. Například pokud vlákna uživatelského rozhraní v aplikaci, která patří dosahuje 100 % času při zpracování uživatelského rozhraní, je velmi pravděpodobně nebude reagovat. Ale pokud vlákna uživatelského rozhraní tráví mnoho času v jiných kategoriích, vyhledejte základní příčiny a zvažte snížení kategorií bez uživatelského rozhraní v daném vláknu možnosti.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)