---
title: 'Postupy: vytvoření sestavy trasování volání nástrojů pro profilaci | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 19c611644b7bfcc1995d1289742901325e02d975
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-profiling-tools-call-trace-report"></a>Postupy: Vytvoření sestavy trasování volání nástrojů pro profilaci
*Sestavy trasování volání* pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci uvádí informace o časování pro každý vstupní a výstupní bod pro funkce aplikace a každé volání jiných funkcí podle funkce. Jsou k dispozici pro profilace data jenom v případě, že byl shromážděné pomocí metody instrumentace sestavy trasování volání.  
  
> [!NOTE]
>  Nelze zobrazit sestavy trasování volání v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Je nutné použít **vsperfreport –** nástroj příkazového řádku pro generování hodnot oddělených čárkami (.csv) nebo soubor Xml. Další informace o tomto nástroji najdete v tématu [vsperfreport –](../profiling/vsperfreport.md).  
  
### <a name="to-create-a-call-trace-report"></a>Vytvoření sestavy trasování volání  
  
1.  Otevřete **příkazového řádku**in okno.  
  
2.  V příkazovém řádku zadejte následující příkaz:  
  
     *ToolsPath* **vsperfreport –** *VSPFile***/CallTrace [XML]**   
  
    |||  
    |-|-|  
    |*ToolsPath*|Cesta profilace nástrojům příkazového řádku. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|  
    |*VSPFile*|Profilování dat (.vsp nebo .vsps) souboru. Úplné a částečné cesty, jsou přijaty.|  
    |XML|Generuje zprávu formátu Xml.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: shromažďování trasování událostí pro Windows (ETW) dat](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)   
 [Rozhraní API nástrojů pro profilaci](../profiling/profiling-tools-apis.md)