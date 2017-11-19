---
title: "Zobrazení jader | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.cores
helpviewer_keywords: Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 867e6a8bffd25a25e9c021aa7565e2087a7c4bd9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="cores-view"></a>Zobrazení jader
Zobrazení jader ukazuje, jak bylo provádění vlákna mapováno na jádrech logický procesor. Pokud píšete serverové aplikace, můžete toto zobrazení optimalizovat výkon mezipaměti pomocí nástroje Správa fondu vláken spřažení nebo přístup z více vláken. Může také pomoct zkoumat případech, kde použití spřažení podprocesu může mít zhoršit problém migrace mezi procesory. Zobrazení jader má dvě části, graf a legendy.  
  
 Graf zobrazuje logické jader na ose y a času na ose x. Každé vlákno v grafu má jedinečnou barvu, takže můžete sledovat jeho přesun mezi jader v čase. Vlákna na tomto grafu můžete filtrovat podle jejich výběrem v oblasti legendy.  
  
 Oblasti legendy má záznam pro každou barvu v grafu. Každé položky se zobrazuje barvu přístup z více vláken a název, číslo mezi základní kontext přepínačů, celkový počet kontextu přepínače a procento kontextu přepínače, které zasahují jader. Legenda je seřazen podle počtu přepnutí kontextu cross-core, v sestupném pořadí. Zobrazí se seznam pouze vláken, která spouští ve druhém zobrazené časové rozmezí.  Seznam je aktualizován, pokud zvětšení nebo posunete zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Vizualizér souběžnosti](../profiling/concurrency-visualizer.md)   
 [Zobrazení využití](../profiling/utilization-view.md)   
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)