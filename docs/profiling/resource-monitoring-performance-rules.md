---
title: "Pravidla výkonu sledování prostředků | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 32ddf4774de92a24a5839f320d09eb61898c69d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="resource-monitoring-performance-rules"></a>Pravidla výkonu sledování prostředků
Výkon zprávy v kategorii sledování prostředků poskytují další data o výkonu vaší aplikace. Tato data můžete analyzovat problémy s výkonem. Tato pravidla jsou informativní a oznámená pro každý profilace spustit.  
  
|||  
|-|-|  
|[DA0501: Průměr spotřeby procesoru profilovaným procesem](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva hlásí procentuální hodnotu času, který byl procesor zaneprázdněný prováděna pokyny z aplikace. Hlášené hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaným procesem.|  
|[DA0502: Maximum spotřeby procesoru profilovaným procesem](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva hlásí maximální procento času, který byl procesor zaneprázdněný prováděna pokyny z aplikace. Hlášené hodnota je maximální hodnotu hlášenou mezi všechny měření intervaly, ve kterých byl aktivní profilovaným procesem.|  
|[DA0503: Průměr pracovní sady v bajtech pro profilovaný proces](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost fyzické paměti, v bajtech, které proces se používají při vytváření profilu byl aktivní. Tato míra fyzické paměti se říká pracovní sady.|  
|[DA0504: Maximum pracovní sady v bajtech pro profilovaný proces](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva hlásí maximální množství fyzické paměti, v bajtech, které proces se používají při vytváření profilu byl aktivní.|  
|[DA0505: Průměr nesdílených bajtů přidělených pro profilovaný proces](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost virtuální paměti, že byl proces v bajtech přidělena při profilace aktivní. Tato míra virtuální paměti se označuje jako *nesdílených bajtů*. Nesdílených bajtů představuje umístění virtuální paměti, které byly přiděleny proces, který lze přistupovat pouze vláken běžících v rámci procesu.|  
|[DA0506: Maximum nesdílených bajtů přidělených pro profilovaný proces](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí maximální velikost virtuální paměti, že byl proces přidělené v nesdílených bajtů při profilace aktivní.|