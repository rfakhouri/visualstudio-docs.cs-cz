---
title: Graf využití procesoru | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph
helpviewer_keywords:
- CPU Utilization GraphConcurrency Visualizer, CPU Utilization Graph
ms.assetid: 5332fd38-622d-47a3-874f-8c2fd7a30f95
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 570ddb4472baec04e656db0b36af5a2550720774
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53830281"
---
# <a name="cpu-utilization-graph"></a>Graf využití procesoru
Graf využití procesoru v aplikaci zobrazí úroveň využití v průběhu času. Představuje dobu trvání trasování osy x a osy y představuje počet logických jader v systému. Grafu nezobrazí, které konkrétní core je aktivní v daném okamžiku. Například pokud dvě jádra každý systém plně využívá kapacitu 50 procent za dané časové období, pak toto zobrazení uvádí využívané jednoho logického jádra.  
  
## <a name="cpu-utilization-graph-colors"></a>Barvy graf využití procesoru  
  
-   Zelená značí využití logických jader v systému v aktuálním procesu.  
  
-   Světle šedá označuje využití logických jader s jinými procesy v systému. Vysoké procento světle šedá v grafu využití procesoru označuje, že systém je silně zatížen jinými procesy a, že váš proces by mohla být dojde ke zrušení jimi. Ke snížení spotřeby logických jader s jinými procesy, snížit počet z nich spuštěné v systému.  
  
-   Tmavě šedá označuje spotřeby logických jader systémový proces. Nemůžete ovládat, přímo toto, ale je vhodné vědět, kdy dochází, protože ho může mít vliv na dostupnost logického jádra pro proces.  
  
-   Prázdné označuje dostupnosti nepoužité logických jader v systému. Pokud nemůžete najít další příležitosti pro paralelismus jsou k dispozici pro váš proces těchto jader.  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení využití](../profiling/utilization-view.md)   
 [Průměrné využití procesoru](../profiling/average-cpu-utilization.md)