---
title: Souhrnné zobrazení – zobrazení kolize prostředků | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 6da57b83-7b42-4d7c-9aea-8e0a830faf6b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 32bd10c1260309856eba14a3a42d2acaac939f6e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029216"
---
# <a name="summary-view---resource-contention-view"></a>Souhrnné zobrazení – zobrazení kolize prostředků
Souhrnné zobrazení zobrazuje informace o událostech ve vaší aplikaci, ve kterém byl pozastaven vlákna nebo procesu při čekání na přístup k prostředku.  
  
 Další informace, včetně popisu odkazy oznámení a sestavy seznamy, naleznete v tématu [souhrnné zobrazení](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Časová osa grafu  
 Časová osa grafu v souhrnném zobrazení zobrazuje počet kolizní události profilované aplikace v čase, které profilaci došlo k chybě. Časová osa grafu můžete použít k filtrování zobrazení tak, aby ve vybraném časovém rozsahu. Další informace najdete v tématu [jak: Filtrování zobrazení sestav ze souhrnné časové osy](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="most-contended-resources"></a>Nejspornější prostředky  
 **Většinu prostředků ve sporných** seznam prostředků v aplikaci, která způsobila nejvíce kolizní události. Můžete kliknout na název prostředku k zobrazení sporů. Zobrazení kolizí poskytuje podrobné časová osa sporů prostředků vláknem.  
  
 **Většinu prostředků ve sporných** zahrnuje následující data pro jednotlivé prostředky.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Název**|Název prostředku.|  
|**% Sporů**|Procento všech kolizní události v profilaci dat, které byly sporů za tento prostředek.|  
  
## <a name="most-contended-thread"></a>Většina Nejspornější vlákna  
 **Většina ve sporných vláken** vypíše vlákna, v aplikaci, která měla největší počet kolizní události. Můžete kliknout na název vlákna k zobrazení sporů, která poskytuje podrobné časová osa sporů prostředků tím, že vlákno.  
  
 **Většina ve sporných vláken** zahrnuje následující údaje pro každé vlákno.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID**|Identifikátor vlákna.|  
|**Název**|Název procesu, který vlastní vlákno.|  
|**% Sporů**|Procento všech kolizní události v profilaci dat, které byly sporů za tento prostředek.|