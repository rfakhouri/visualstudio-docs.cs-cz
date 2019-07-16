---
title: Souhrnné zobrazení – zobrazení kolize prostředků | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 6da57b83-7b42-4d7c-9aea-8e0a830faf6b
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 65f659b64b6a1e29e1e25ae344dd8033e631de09
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157758"
---
# <a name="summary-view---resource-contention-view"></a>Souhrnné zobrazení – zobrazení kolize prostředků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
