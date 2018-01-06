---
title: "Zobrazení procesů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.process
helpviewer_keywords:
- performance tools reports, process view
- Process view
- performance tools, process view
- Profiling Tools,process view
- Profiling Tools,process report
ms.assetid: 6d4e2a5d-9f17-4ece-a6f1-75836e1fc382
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c730169988d931d3e1e57dd22f2793b1f8a16a72
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="process-view"></a>Zobrazení procesů
Zobrazení procesů zobrazí data profilování pro procesy a vláken, které byly provedeny během spuštění profilování.  
  
 Procesy jsou uvedeny podle názvu. Vlákna jsou uvedeny jako uzly podřízené proces, který je vytvořil. Vlákna jsou pojmenované funkce, která spustit vlákno nebo popisek **[ntdll.dll]** Pokud jsou k dispozici žádné symboly.  
  
 Chcete-li přidat nebo odebrat sloupce, klikněte pravým tlačítkem na zobrazení a pak vyberte **přidat nebo odebrat sloupce**. Kromě toho můžete řadit data kliknutím na název sloupce. Další informace najdete v tématu [postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md).  
  
 Sloupce zobrazení procesů jsou stejné pro data, která je generována pomocí metody vzorkování a instrumentace a pro data, která obsahuje data paměti .NET. Následující tabulka popisuje hodnoty ve sloupcích.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jedinečné ID**|Identifikátor generovaný profileru, které jsou jedinečné pro proces nebo přístup z více vláken.|  
|**ID**|Generované systémem identifikátor procesu nebo přístup z více vláken.|  
|**Jméno**|Název procesu nebo přístup z více vláken.|  
|**Počáteční čas**|Počet milisekund nebo cyklů procesoru od začátku profilace na začátek procesu nebo přístup z více vláken.|  
|**Koncový čas**|Počet milisekund nebo cyklů procesoru od začátku profilace na konci procesu nebo přístup z více vláken.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)   
 [Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)   
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)