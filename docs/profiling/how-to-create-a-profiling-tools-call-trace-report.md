---
title: "Postupy: vytvoření sestavy trasování volání nástrojů pro profilaci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1daf97ee7de7a0deea9b3b1c8a9a17529edfe9b4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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