---
title: Pravidla výkonu sledování prostředků | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7e4071820aece2f58f0a1345e1110a80c9f76f0f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947917"
---
# <a name="resource-monitoring-performance-rules"></a>Pravidla výkonu sledování prostředků
Výkon zprávy v kategorii monitorování prostředků poskytují další data o výkonu vaší aplikace. Tato data můžete použít k analýze problémů výkonu. Tato pravidla jsou informační a nahlášených pro každé spuštění profilování.  
  
|||  
|-|-|  
|[DA0501: Průměr spotřeby procesoru profilovaným procesem.](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva znamená procentuální hodnotu času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaný proces.|  
|[DA0502: Maximum spotřeby procesoru profilovaným procesem](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva znamená maximální procento času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je maximální hodnota uvedená mezi všechny intervaly měření, ve kterých byl aktivní profilovaný proces.|  
|[DA0503: Průměr pracovní sady v bajtech pro profilovaný proces](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost fyzické paměti, v bajtech, které proces používal během profilace byl aktivní. Tato míra fyzické paměti se označuje jako pracovní sady.|  
|[DA0504: Maximum pracovní sady v bajtech pro profilovaný proces](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva znamená maximální velikost fyzické paměti, v bajtech, které proces používal během profilace byl aktivní.|  
|[DA0505: Průměr nesdílených bajtů přidělených pro profilovaný proces](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost virtuální paměti, že byl aktivní proces přidělených bajtů při profilování. Tato míra virtuální paměti se označuje jako *Nesdílené bajty*. Nesdílené bajty představuje virtuální paměti umístění, které byly přiděleny procesem, který je přístupný pouze tím, že běží uvnitř procesu vlákna.|  
|[DA0506: Maximum nesdílených bajtů přidělených pro profilovaný proces](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí maximální velikost virtuální paměti, že byl aktivní proces nesdílených bajtů přidělených při profilování.|