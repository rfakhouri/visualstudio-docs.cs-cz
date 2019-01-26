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
ms.openlocfilehash: be698fdb7dd931b4609e797434116d2eb1b5056e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54940034"
---
# <a name="ui-processing-time"></a>Doba zpracování uživatelského rozhraní
Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako zpracování uživatelského rozhraní. Z toho vyplývá, že vlákno – čerpání zpráv Windows nebo provádění jiné práce uživatelské rozhraní (UI). Během této doby je zablokovaný vlákno v rozhraní API, které Vizualizátor souběžnosti se počítá jako zpracování uživatelského rozhraní. Rozhraní API, jako `GetMessage()` a `MsgWaitForMultipleObjects()` spadají do této skupiny.  
  
 Pokud se zjistí, žádné předdefinované blokování rozhraní API, projděte si zásobníky volání a profilu, sestavy určit základní příčiny zpoždění.  
  
 Kategorie zpracování uživatelského rozhraní vám pomůže pochopit rychlosti odezvy aplikací grafického uživatelského rozhraní a je žádoucí v aplikacích, které závisí na rychlosti odezvy uživatelského rozhraní. Například pokud vlákno uživatelského rozhraní v aplikaci dosáhne 100 % času v zpracování uživatelského rozhraní, je pravděpodobně nebude reagovat. Pokud vlákno uživatelského rozhraní stráví značnou dobu v jiných kategoriích, ale hledat hlavní příčiny a zvažte možnosti snížení kategorie bez uživatelského rozhraní v daném vláknu.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)