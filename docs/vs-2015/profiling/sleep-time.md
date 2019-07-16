---
title: Doba spánku | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8a79bbca9f6275f115105cc2ba6b001ac0ca7d44
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198379"
---
# <a name="sleep-time"></a>Doba spánku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tyto segmenty na časové ose jsou přidruženy k blokování čas, který je zařazený do kategorie jako přejít do režimu spánku. Kategorie z režimu spánku znamená, že vlákno dobrovolně udělil si jeho logické jádro a je to žádná práce. Během této doby je zablokovaný vlákno v rozhraní API, které Vizualizátor souběžnosti se počítá jako přejít do režimu spánku. Rozhraní API, jako `Sleep()` a `SwitchToThread()` spadají do této skupiny.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)
