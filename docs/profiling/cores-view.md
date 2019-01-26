---
title: Zobrazení jader | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: abca09620c82ba41f3acec5f878c621f6af02ae8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55038848"
---
# <a name="cores-view"></a>Zobrazení jader
**Zobrazení jader** ukazuje, jak bylo vlákno provádění mapované na logický procesor jader (zvolte **analyzovat** > **Vizualizátor souběžnosti** spusťte Vizualizér souběžnosti). Pokud píšete serverových aplikací, toto zobrazení vám může pomoci optimalizovat výkon mezipaměti pomocí nástroje Správa fondu vztahů nebo vlákna. vlákna. Může také pomoct prozkoumat případy, kdy použití spřažení vláken může mít zhoršit problém migrace napříč jádry. Zobrazení jader má dvě části, graf a legendu.  
  
 Graf zobrazuje počet logických jader na ose y a času na ose x. Každé vlákno v grafu má odlišnou barvu, takže můžete sledovat jeho pohyb mezi jádry v čase. Vlákna v tomto grafu můžete filtrovat tak, že je vyberete v oblasti legend.  
  
 Oblasti legend má záznam pro každou barvu v grafu. Každá položka zobrazuje barva vlákna a název, číslo přepnutí kontextu mezi jádry, celkový počet přepnutí kontextu a procento přepínačů kontextů napříč jádry. Legenda je seřazený podle počtu přepínače kontextu mezi jádry v sestupném pořadí. Vypíše vlákna, které provedených během zobrazený časový rozsah.  Seznam se aktualizuje, pokud zvětšování nebo posouvání.  
  
## <a name="see-also"></a>Viz také:  
 [Vizualizátor souběžnosti](../profiling/concurrency-visualizer.md)   
 [Zobrazení využití](../profiling/utilization-view.md)   
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)