---
title: 'Postupy: Vytvoření sestavy trasování událostí pro Windows nástrojů pro profilaci | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: bf5547b3-f6c7-4989-9d47-2fe4f1261444
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e8ad32f3231915c86f9578563ec4c0684435a3ee
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797334"
---
# <a name="how-to-create-a-profiling-tools-etw-report"></a>Postupy: Vytvoření sestavy trasování událostí pro Windows nástrojů pro profilaci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sestava trasování událostí pro Windows (ETW) obsahuje události trasování událostí pro Windows, které jsou zaznamenány v relaci výkonu z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástroje pro profilaci. Data trasování událostí pro Windows se shromažďují v souboru binárního souboru (.etl). Další informace o této sestavě najdete v tématu [sestavy trasování událostí pro Windows (ETW)](../profiling/event-tracing-for-windows-etw-report.md).  
  
> [!NOTE]
>  Nelze zobrazit sestavy trasování událostí pro Windows v rozhraní [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
- Informace o tom, jak shromažďování dat trasování událostí pro Windows pomocí rozhraní pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], naleznete v tématu [jak: Shromažďování trasování událostí pro Windows (ETW) Data](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
- Informace o tom, jak shromažďovat data trasování událostí pro Windows z příkazového řádku najdete v tématu [VSPerfCmd](../profiling/vsperfcmd.md) a [události](../profiling/events-vsperfcmd.md).  
  
  Generování sestavy trasování událostí pro Windows pomocí **VSReport / summary: etw** příkazu. ETL, který obsahuje data trasování událostí pro Windows musí být ve stejném adresáři jako soubor dat profilování (.vsp nebo .vsps). Ve výchozím nastavení je sestava generována jako soubor hodnot oddělených čárkami (CSV). Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).  
  
### <a name="to-generate-an-etw-report"></a>Chcete-li generovat sestavu trasování událostí pro Windows  
  
-   V **příkazového řádku** okno, zadejte na příkazovém řádku následující:  
  
     *ToolsPath* **VSPerfReport** *VSPFile*  **/Summary:ETW [/Xml]**  
  
    |||  
    |-|-|  
    |*ToolsPath*|Cesta nástroje pro profilaci. Další informace najdete v tématu [zadání cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|  
    |*VSPFile*|Soubor dat profilování (.vsp nebo .vsps). Jsou přijímány úplné a částečné cesty.|  
    |XML|Generuje sestavu, která je ve formátu v jazyce XML.|
