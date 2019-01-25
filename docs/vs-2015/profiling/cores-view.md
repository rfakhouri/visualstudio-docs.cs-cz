---
title: Zobrazení jader | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 869980fe7bbb773d566dffd38088b003e3a97a3d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54763005"
---
# <a name="cores-view"></a>Zobrazení jader
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zobrazení jader ukazuje, jak bylo vlákno provádění mapované na logický procesor jader. Pokud píšete serverových aplikací, toto zobrazení vám může pomoci optimalizovat výkon mezipaměti pomocí nástroje Správa fondu vztahů nebo vlákna. vlákna. Může také pomoct prozkoumat případy, kdy použití spřažení vláken může mít zhoršit problém migrace napříč jádry. Zobrazení jader má dvě části, graf a legendu.  
  
 Graf zobrazuje počet logických jader na ose y a času na ose x. Každé vlákno v grafu má odlišnou barvu, takže můžete sledovat jeho pohyb mezi jádry v čase. Vlákna v tomto grafu můžete filtrovat tak, že je vyberete v oblasti legend.  
  
 Oblasti legend má záznam pro každou barvu v grafu. Každá položka zobrazuje barva vlákna a název, číslo přepnutí kontextu mezi jádry, celkový počet přepnutí kontextu a procento přepínačů kontextů napříč jádry. Legenda je seřazený podle počtu přepínače kontextu mezi jádry v sestupném pořadí. Vypíše vlákna, které provedených během zobrazený časový rozsah.  Seznam se aktualizuje, pokud zvětšování nebo posouvání.  
  
## <a name="see-also"></a>Viz také  
 [Vizualizátor souběžnosti](../profiling/concurrency-visualizer.md)   
 [Zobrazení využití](../profiling/utilization-view.md)   
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)
