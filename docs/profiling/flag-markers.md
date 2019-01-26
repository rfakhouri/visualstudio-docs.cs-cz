---
title: Příznak značek | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.markers.flag
ms.assetid: f3ec919e-63e5-484b-adbf-8f0e79342e75
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 19ecac740035cc6de49a5651b20f2408eddd27ca
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986823"
---
# <a name="flag-markers"></a>Značky příznaků
Příznak značka představuje něco, ke které došlo v okamžiku v čase v aplikaci. Příznak, který může představovat různé druhy událostí aplikace. Příznak, který může například zobrazit naplánovaného konkrétní pracovní položce nebo když došlo k výjimce. Moduly runtime, jako je například Task Parallel Library můžete vygenerovat také příznaky.  
  
## <a name="flag-importance"></a>Důležitosti příznaku  
 Příznaky jsou zobrazeny v různě v závislosti na jejich význam. Stejně jako všechny značky může být význam nízká, Normální, vysoká nebo kritické.  Tento obrázek ukazuje vzhled značek podle úrovně závažnosti:  
  
 ![Nízká, Normální, vysokou a kritický význam značky](../profiling/media/cvmarkerimportance.png "CVMarkerImportance")  
Značky zobrazující důležitosti příznaku  
  
## <a name="flag-category"></a>Příznak kategorie  
 Příznak, který se zobrazí v jednom z pěti různých barev v závislosti na jeho kategorie. Barvy jsou znovu použít, pokud existuje více než pět kategorií. Nemůžete zvolit barvu. Stejně jako všechny značky kategorie může být libovolné celé číslo. Následující obrázek znázorňuje barvy pro prvních pět kategorií.  
  
 ![Pět barvy značky kategorie](../profiling/media/cvmarkercategory.png "CVMarkerCategory")  
Zobrazení kategorií značky  
  
## <a name="alerts"></a>Upozornění  
 Výstraha je red barevné příznak, který představuje událost kritické aplikace, jako je například výjimku.  Tady je výstrahy:  
  
 ![Upozornění značek pro Concurrency Visualizer](../profiling/media/cvmarkeralert.png "CVMarkerAlert")  
Upozornění značky  
  
## <a name="aggregation-flags"></a>Příznaky agregace  
 Někdy příznaky probíhá tak blízko sebe Vizualizátor souběžnosti, že se nedá vykreslit jednotlivě. Pokud k tomu dojde, šedé *agregace příznak* , že se zobrazí představuje základní příznaky. Když ukazatel myši na jednu z těchto ikon, zobrazí popisek počet základní příznaky, které jsou reprezentovány. Chcete-li zobrazit příznaků, Přiblížit. Pokud přiblížíte úplně a zachovat si agregaci příznak, můžete zobrazit základní příznaky v [sestava značek](../profiling/markers-report.md).  
  
 Příznaky agregace jsou vykreslovány v různých velikostech. Velikost závisí na úroveň důležitosti příznaku nejdůležitější v agregaci. Následující obrázek znázorňuje příznaky agregace ve vzestupném pořadí podle důležitosti.  
  
 ![Agregace příznaky znázorňující čtyři úrovně důležitosti](../profiling/media/cvmarkeraggregate.png "CVMarkerAggregate")  
Příznaky agregace podle úrovně závažnosti  
  
## <a name="see-also"></a>Viz také:  
 [Značky Vizualizéru souběžnosti](../profiling/concurrency-visualizer-markers.md)   
 [SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md)