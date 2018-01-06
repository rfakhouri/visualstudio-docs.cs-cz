---
title: "Graf využití procesoru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.cpu.graph
helpviewer_keywords: CPU Utilization GraphConcurrency Visualizer, CPU Utilization Graph
ms.assetid: 5332fd38-622d-47a3-874f-8c2fd7a30f95
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1158d4a584bddc065b65bd282a5f53666eae9946
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cpu-utilization-graph"></a>Graf využití procesoru
Graf využití procesoru v aplikaci znázorňuje úroveň využití v průběhu času. Osy x představuje dobu trvání trasování a osy y představuje počet logických jader v systému. Graf nezobrazí, které konkrétní základní je aktivní v daném okamžiku. Například pokud každé dvě jádra jsou spuštěné v 50 procent kapacity pro dané časové období, pak toto zobrazení uvádí jednoho logického jádra využívání.  
  
## <a name="cpu-utilization-graph-colors"></a>Barvy graf využití procesoru  
  
-   Zelená značí využití logické jader v systému v aktuálním procesu.  
  
-   Světle šedé označuje využití logické jader s jinými procesy v systému. Vysoké procento světla šedé v grafu procesoru označuje velkém zatížení systému s jinými procesy a že váš proces je pravděpodobně být zrušeny podle nich. Ke snížení spotřeby logické jader s jinými procesy, snižte počet je spuštěna v systému.  
  
-   Tmavý šedá označuje spotřeby logické jader proces systému. Nemůžete ovládat přímo to ale je užitečné vědět, kdy dochází, protože může ovlivnit dostupnost logická jádra pro proces.  
  
-   Prázdné označuje dostupnost nepoužívané logické jádra systému. Pokud zjistíte většího počtu možností pro stupně paralelního zpracování jsou k dispozici pro váš proces těchto jader.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení využití](../profiling/utilization-view.md)   
 [Průměrné využití procesoru](../profiling/average-cpu-utilization.md)