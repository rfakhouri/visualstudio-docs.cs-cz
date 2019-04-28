---
title: Pravidla výkonu sledování prostředků | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6818bab45532aa44b8ed9ed73978df7c3a05a7bf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62834061"
---
# <a name="resource-monitoring-performance-rules"></a>Pravidla výkonu sledování prostředků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Výkon zprávy v kategorii monitorování prostředků poskytují další data o výkonu vaší aplikace. Tato data můžete použít k analýze problémů výkonu. Tato pravidla jsou informační a nahlášených pro každé spuštění profilování.  
  
|||  
|-|-|  
|[DA0501: Průměrná spotřeba procesoru profilovaným procesem](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva znamená procentuální hodnotu času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaný proces.|  
|[DA0502: Maximální spotřeba procesoru profilovaným procesem](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva znamená maximální procento času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je maximální hodnota uvedená mezi všechny intervaly měření, ve kterých byl aktivní profilovaný proces.|  
|[DA0503: Průměrná pracovní sada v bajtech profilovaného procesu](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost fyzické paměti, v bajtech, které proces používal během profilace byl aktivní. Tato míra fyzické paměti se označuje jako pracovní sady.|  
|[DA0504: Maximální pracovní sada v bajtech profilovaného procesu](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva znamená maximální velikost fyzické paměti, v bajtech, které proces používal během profilace byl aktivní.|  
|[DA0505: Průměrné nesdílené bajty přidělené profilovanému procesu](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost virtuální paměti, že byl aktivní proces přidělených bajtů při profilování. Tato míra virtuální paměti se označuje jako *Nesdílené bajty*. Nesdílené bajty představuje virtuální paměti umístění, které byly přiděleny procesem, který je přístupný pouze tím, že běží uvnitř procesu vlákna.|  
|[DA0506: Maximální nesdílené bajty přidělené profilovanému procesu](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí maximální velikost virtuální paměti, že byl aktivní proces nesdílených bajtů přidělených při profilování.|
