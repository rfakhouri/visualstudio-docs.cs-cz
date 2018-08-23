---
title: Pravidla výkonu sledování prostředků | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2bd11b8b18e5dd4e3f6625b1b269d104a6fd5a5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671485"
---
# <a name="resource-monitoring-performance-rules"></a>Pravidla výkonu sledování prostředků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [pravidla výkonu sledování prostředků](https://docs.microsoft.com/visualstudio/profiling/resource-monitoring-performance-rules).  
  
Výkon zprávy v kategorii monitorování prostředků poskytují další data o výkonu vaší aplikace. Tato data můžete použít k analýze problémů výkonu. Tato pravidla jsou informační a nahlášených pro každé spuštění profilování.  
  
|||  
|-|-|  
|[DA0501: Průměr spotřeby procesoru profilovaným procesem](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva znamená procentuální hodnotu času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaný proces.|  
|[DA0502: Maximum spotřeby procesoru profilovaným procesem](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva znamená maximální procento času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je maximální hodnota uvedená mezi všechny intervaly měření, ve kterých byl aktivní profilovaný proces.|  
|[DA0503: Průměr pracovní sady v bajtech pro profilovaný proces](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost fyzické paměti, v bajtech, které proces používal během profilace byl aktivní. Tato míra fyzické paměti se označuje jako pracovní sady.|  
|[DA0504: Maximum pracovní sady v bajtech pro profilovaný proces](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva znamená maximální velikost fyzické paměti, v bajtech, které proces používal během profilace byl aktivní.|  
|[DA0505: Průměr nesdílených bajtů přidělených pro profilovaný proces](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost virtuální paměti, že byl aktivní proces přidělených bajtů při profilování. Tato míra virtuální paměti se označuje jako *Nesdílené bajty*. Nesdílené bajty představuje virtuální paměti umístění, které byly přiděleny procesem, který je přístupný pouze tím, že běží uvnitř procesu vlákna.|  
|[DA0506: Maximum nesdílených bajtů přidělených pro profilovaný proces](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí maximální velikost virtuální paměti, že byl aktivní proces nesdílených bajtů přidělených při profilování.|



