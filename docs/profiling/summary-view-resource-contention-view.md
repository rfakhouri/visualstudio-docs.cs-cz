---
title: "Souhrnné zobrazení – zobrazení kolize prostředků | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Summary view
ms.assetid: 6da57b83-7b42-4d7c-9aea-8e0a830faf6b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7a6e681c703847c970d79c1523ab12ce89e68d28
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="summary-view---resource-contention-view"></a>Souhrnné zobrazení – zobrazení kolize prostředků
Souhrnné zobrazení zobrazí informace o událostech v aplikaci, ve kterém byla pozastavena vlákna nebo proces, při jeho čekali pro přístup k prostředku.  
  
 Další informace, včetně popisu odkazy oznámení a sestavy seznamů v tématu [zobrazení souhrnu](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Časová osa grafu  
 Časová osa grafu v souhrnné zobrazení se zobrazuje číslo kolizní události PROFILOVANÉHO aplikace v průběhu času, který profilace došlo k chybě. Časová osa grafu můžete filtrovat zobrazení vybrané časové období. Další informace najdete v tématu [postupy: filtrování zobrazení sestav ze souhrnné časové osy](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="most-contended-resources"></a>Většina tvrdil prostředků  
 **Většina tvrdil prostředky** jsou uvedeny prostředky v aplikaci, která způsobila, že nejvíce kolizní události. Můžete kliknout na název zobrazíte zobrazení kolizí prostředku. Zobrazení kolizí poskytuje podrobné časové osy z kolize prostředku – tím, že přístup z více vláken.  
  
 **Většina tvrdil prostředky** zahrnuje následující data pro každého prostředku.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název prostředku.|  
|**% Kolizí**|Procento všech kolizní události v profilaci data, která měla kolizí přes tento prostředek.|  
  
## <a name="most-contended-thread"></a>Většina tvrdil přístup z více vláken  
 **Většina tvrdil vláken** uvádí vláken v aplikaci, která měla největšího počtu kolizní události. Klikněte na tlačítko Zobrazit kolizí, který poskytuje podrobné časové osy z kolize prostředku – tím, že vlákno názvu vlákna.  
  
 **Většina tvrdil vláken** zahrnuje následující data pro každé vlákno.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID**|Identifikátor přístup z více vláken.|  
|**Jméno**|Název procesu, který vlastní vlákno.|  
|**% Kolizí**|Procento všech kolizní události v profilaci data, která měla kolizí přes tento prostředek.|