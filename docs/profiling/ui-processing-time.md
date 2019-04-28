---
title: Doba zpracování uživatelského rozhraní | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.uiprocessing
helpviewer_keywords:
- Concurrency Visualizer, UI Processing Time
ms.assetid: 0ddb05a3-8c6b-448b-8488-2751c1e5abcc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 391b4582d03e32e738f0eade823326e72a662a43
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63004439"
---
# <a name="ui-processing-time"></a>Doba zpracování uživatelského rozhraní
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako zpracování uživatelského rozhraní. Z toho vyplývá, že vlákno – čerpání zpráv Windows nebo provádění jiné práce uživatelské rozhraní (UI). Během této doby je zablokovaný vlákno v rozhraní API, které Vizualizátor souběžnosti se počítá jako zpracování uživatelského rozhraní. Rozhraní API, jako `GetMessage()` a `MsgWaitForMultipleObjects()` spadají do této skupiny.

 Pokud se zjistí, žádné předdefinované blokování rozhraní API, projděte si zásobníky volání a profilu, sestavy určit základní příčiny zpoždění.

 Kategorie zpracování uživatelského rozhraní vám pomůže pochopit rychlosti odezvy aplikací grafického uživatelského rozhraní a je žádoucí v aplikacích, které závisí na rychlosti odezvy uživatelského rozhraní. Například pokud vlákno uživatelského rozhraní v aplikaci dosáhne 100 % času v zpracování uživatelského rozhraní, je pravděpodobně nebude reagovat. Pokud vlákno uživatelského rozhraní stráví značnou dobu v jiných kategoriích, ale hledat hlavní příčiny a zvažte možnosti snížení kategorie bez uživatelského rozhraní v daném vláknu.

## <a name="see-also"></a>Viz také:
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)