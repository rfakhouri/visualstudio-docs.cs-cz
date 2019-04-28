---
title: Prázdný Segment časové osy | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.empty
helpviewer_keywords:
- Concurrency Visualizer, empty timeline segment
ms.assetid: f37b301f-3edc-4e56-8084-feec2dc5a9b1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a96cdc7ae4edc7ea7193d5b95dfc73fa1747c1fb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62970106"
---
# <a name="empty-timeline-segment"></a>Prázdný segment časové osy
Ve Vizualizátor souběžnosti, proč se části časové osy je prázdný (má bílé pozadí) závisí na typu vašeho kanálu.

- Pro kanál vlákna CPU znamená to, že vlákno neexistoval při tuto část časové osy. Pokud vás zajímá ve vlákně, najdete jeho provádění části pomocí ovládacího prvku přiblížení nebo posouvání vodorovně.

- Pro kanál vstupně-výstupních operací znamená to, že žádný přístup k disku došlo k jménem Cílový proces od tohoto okamžiku v čase.

- Pro kanál rozhraní DirectX znamená to, že se žádná práce GPU provedla jménem Cílový proces během této části časové osy.

- Pro značky kanál znamená to, že nevygenerovaly se žádné značky.

## <a name="see-also"></a>Viz také:
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)
- [Ovládací prvek Lupa (zobrazení vláken)](../profiling/zoom-control-threads-view.md)