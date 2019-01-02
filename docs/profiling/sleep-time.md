---
title: Doba spánku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 53f9137c35bd89e812f1d671e2e51f88b343753c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53920255"
---
# <a name="sleep-time"></a>Doba spánku
Tyto segmenty na časové ose jsou přidruženy k blokování čas, který je zařazený do kategorie jako přejít do režimu spánku. Kategorie z režimu spánku znamená, že vlákno dobrovolně udělil si jeho logické jádro a je to žádná práce. Během této doby je zablokovaný vlákno v rozhraní API, které Vizualizátor souběžnosti se počítá jako přejít do režimu spánku. Rozhraní API, jako `Sleep()` a `SwitchToThread()` spadají do této skupiny.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)