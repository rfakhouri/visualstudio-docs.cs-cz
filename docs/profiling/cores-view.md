---
title: "Zobrazení jader | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1867f2b0ba84590068b1ae54b0a7aa1d48475247
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/27/2018
---
# <a name="cores-view"></a>Zobrazení jader
**Zobrazení jader** ukazuje, jak bylo provádění vlákna mapováno na jádrech logický procesor (zvolte **analyzovat** > **vizualizér souběžnosti** spuštění Vizualizér souběžnosti). Pokud píšete serverové aplikace, můžete toto zobrazení optimalizovat výkon mezipaměti pomocí nástroje Správa fondu vláken spřažení nebo přístup z více vláken. Může také pomoct zkoumat případech, kde použití spřažení podprocesu může mít zhoršit problém migrace mezi procesory. Zobrazení jader má dvě části, graf a legendy.  
  
 Graf zobrazuje logické jader na ose y a času na ose x. Každé vlákno v grafu má jedinečnou barvu, takže můžete sledovat jeho přesun mezi jader v čase. Vlákna na tomto grafu můžete filtrovat podle jejich výběrem v oblasti legendy.  
  
 Oblasti legendy má záznam pro každou barvu v grafu. Každé položky se zobrazuje barvu přístup z více vláken a název, číslo mezi základní kontext přepínačů, celkový počet kontextu přepínače a procento kontextu přepínače, které zasahují jader. Legenda je seřazen podle počtu přepnutí kontextu cross-core, v sestupném pořadí. Zobrazí se seznam pouze vláken, která spouští ve druhém zobrazené časové rozmezí.  Seznam je aktualizován, pokud zvětšení nebo posunete zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Vizualizér souběžnosti](../profiling/concurrency-visualizer.md)   
 [Zobrazení využití](../profiling/utilization-view.md)   
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)