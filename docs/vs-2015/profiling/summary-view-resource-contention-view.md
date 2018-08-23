---
title: Souhrnné zobrazení – zobrazení kolize prostředků | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Summary view
ms.assetid: 6da57b83-7b42-4d7c-9aea-8e0a830faf6b
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf83509cd56343001a94da619b9246464ed75bdf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632388"
---
# <a name="summary-view---resource-contention-view"></a>Souhrnné zobrazení – zobrazení kolize prostředků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [souhrnné zobrazení – zobrazení kolize prostředků](https://docs.microsoft.com/visualstudio/profiling/summary-view-resource-contention-view).  
  
Souhrnné zobrazení zobrazuje informace o událostech ve vaší aplikaci, ve kterém byl pozastaven vlákna nebo procesu při čekání na přístup k prostředku.  
  
 Další informace, včetně popisu odkazy oznámení a sestavy seznamy, naleznete v tématu [souhrnné zobrazení](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Časová osa grafu  
 Časová osa grafu v souhrnném zobrazení zobrazuje počet kolizní události profilované aplikace v čase, které profilaci došlo k chybě. Časová osa grafu můžete použít k filtrování zobrazení tak, aby ve vybraném časovém rozsahu. Další informace najdete v tématu [postupy: filtrování zobrazení sestav ze časová osa souhrnu](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="most-contended-resources"></a>Nejspornější prostředky  
 **Většinu prostředků ve sporných** seznam prostředků v aplikaci, která způsobila nejvíce kolizní události. Můžete kliknout na název prostředku k zobrazení sporů. Zobrazení kolizí poskytuje podrobné časová osa sporů prostředků vláknem.  
  
 **Většinu prostředků ve sporných** zahrnuje následující data pro jednotlivé prostředky.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název prostředku.|  
|**% Sporů**|Procento všech kolizní události v profilaci dat, které byly sporů za tento prostředek.|  
  
## <a name="most-contended-thread"></a>Většina Nejspornější vlákna  
 **Většina ve sporných vláken** vypíše vlákna, v aplikaci, která měla největší počet kolizní události. Můžete kliknout na název vlákna k zobrazení sporů, která poskytuje podrobné časová osa sporů prostředků tím, že vlákno.  
  
 **Většina ve sporných vláken** zahrnuje následující údaje pro každé vlákno.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID**|Identifikátor vlákna.|  
|**Jméno**|Název procesu, který vlastní vlákno.|  
|**% Sporů**|Procento všech kolizní události v profilaci dat, které byly sporů za tento prostředek.|



