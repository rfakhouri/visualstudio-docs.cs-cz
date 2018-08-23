---
title: 'Postupy: vytvoření sestavy trasování událostí pro Windows nástrojů pro profilaci | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf5547b3-f6c7-4989-9d47-2fe4f1261444
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93aea1474bb8e8ac215a6eb8e3c8b695d4901cba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671318"
---
# <a name="how-to-create-a-profiling-tools-etw-report"></a>Postupy: Vytvoření sestavy Trasování událostí pro Windows nástrojů pro profilaci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: vytvoření sestavy trasování událostí pro Windows nástrojů pro profilaci](https://docs.microsoft.com/visualstudio/profiling/how-to-create-a-profiling-tools-etw-report).  
  
Sestava trasování událostí pro Windows (ETW) obsahuje události trasování událostí pro Windows, které jsou zaznamenány v relaci výkonu z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástroje pro profilaci. Data trasování událostí pro Windows se shromažďují v souboru binárního souboru (.etl). Další informace o této sestavě najdete v tématu [sestavy trasování událostí pro Windows (ETW)](../profiling/event-tracing-for-windows-etw-report.md).  
  
> [!NOTE]
>  Nelze zobrazit sestavy trasování událostí pro Windows v rozhraní [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
-   Informace o tom, jak shromažďování dat trasování událostí pro Windows pomocí rozhraní pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], naleznete v tématu [postupy: shromažďování trasování událostí pro Windows (ETW) Data](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
-   Informace o tom, jak shromažďovat data trasování událostí pro Windows z příkazového řádku najdete v tématu [VSPerfCmd](../profiling/vsperfcmd.md) a [události](../profiling/events-vsperfcmd.md).  
  
 Generování sestavy trasování událostí pro Windows pomocí **VSReport / summary: etw** příkazu. ETL, který obsahuje data trasování událostí pro Windows musí být ve stejném adresáři jako soubor dat profilování (.vsp nebo .vsps). Ve výchozím nastavení je sestava generována jako soubor hodnot oddělených čárkami (CSV). Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).  
  
### <a name="to-generate-an-etw-report"></a>Chcete-li generovat sestavu trasování událostí pro Windows  
  
-   V **příkazového řádku** okno, zadejte na příkazovém řádku následující:  
  
     *ToolsPath* **VSPerfReport** *VSPFile* **/Summary: ETW [/ XML]**  
  
    |||  
    |-|-|  
    |*ToolsPath*|Cesta nástroje pro profilaci. Další informace najdete v tématu [zadání cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|  
    |*VSPFile*|Soubor dat profilování (.vsp nebo .vsps). Jsou přijímány úplné a částečné cesty.|  
    |XML|Generuje sestavu, která je ve formátu v jazyce XML.|



