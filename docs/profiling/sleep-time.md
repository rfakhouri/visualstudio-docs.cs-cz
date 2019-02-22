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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be2d566228367e2cdb07aecc2d73eaf82a6d961f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56637682"
---
# <a name="sleep-time"></a>Doba spánku
Tyto segmenty na časové ose jsou přidruženy k blokování čas, který je zařazený do kategorie jako přejít do režimu spánku. Kategorie z režimu spánku znamená, že vlákno dobrovolně udělil si jeho logické jádro a je to žádná práce. Během této doby je zablokovaný vlákno v rozhraní API, které Vizualizátor souběžnosti se počítá jako přejít do režimu spánku. Rozhraní API, jako `Sleep()` a `SwitchToThread()` spadají do této skupiny.

## <a name="see-also"></a>Viz také:
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)