---
title: Čas přerušení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de7a02f7247e09876bc4598d44fc1c395161ebc2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935890"
---
# <a name="preemption-time"></a>Čas přerušení
Tyto segmenty na časové ose jsou přidruženy k blokování, který je zařazený do kategorie jako ztracený čas. Tato kategorie znamená, že je vlákno přepnutí z jednoho z těchto důvodů:

- Plánovač se nahrazuje použití vyšší priorita vlákna.

- Kvantové doby provádění vlákna vypršela platnost a byly jiná vlákna připravená ke spuštění.

  Během této doby je blokovaná společností Důvod čekání jádra, která Vizualizátor souběžnosti se počítá jako ztracený vlákno. Ztracený segmenty spustit, když vlákno je vložena mimo logické jádro a ukončit, pokud bylo vlákno pokračuje v provádění.

  Popis pro segment dojde ke zrušení zobrazí název procesu nebo vlákna, která způsobila ztracený. Nicméně to neznamená, že proces nebo vlákno, které převzal skutečně spustila v průběhu preempted období.

## <a name="see-also"></a>Viz také:
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)