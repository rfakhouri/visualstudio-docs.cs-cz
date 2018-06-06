---
title: 'Postupy: vytvoření sestavy trasování událostí pro Windows nástrojů pro profilaci | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: bf5547b3-f6c7-4989-9d47-2fe4f1261444
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4b086e726f45010d2d71395d0c6119625180add3
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815295"
---
# <a name="how-to-create-a-profiling-tools-etw-report"></a>Postupy: vytvoření sestavy trasování událostí pro Windows nástrojů pro profilaci
Tato sestava trasování událostí pro Windows (ETW) uvádí události trasování událostí pro Windows, které se zaznamenávají v relaci výkonu z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci. Trasování událostí pro Windows data jsou shromažďována v binárním (. *ETL*) souboru. Další informace o této sestavě najdete v tématu [sestavy trasování událostí pro Windows (ETW)](../profiling/event-tracing-for-windows-etw-report.md).  
  
> [!NOTE]
>  Nelze zobrazit sestavy trasování událostí pro Windows v rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   Informace o tom, jak shromažďování dat trasování událostí pro Windows pomocí rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], najdete v části [postup: data shromažďovat trasování událostí pro Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
-   Informace o tom, jak shromažďování dat trasování událostí pro Windows z příkazového řádku najdete v tématu [VSPerfCmd](../profiling/vsperfcmd.md) a [události](../profiling/events-vsperfcmd.md).  
  
 Vygenerování sestavy trasování událostí pro Windows pomocí **VSReport / souhrn: etw** příkaz. Na. *etl* trasování událostí pro Windows, který obsahuje data musí být ve stejném adresáři jako data profilování (. *Vsp* nebo. *vsps*) souboru. Ve výchozím nastavení je sestava generována jako hodnoty oddělené čárkami (. *CSV*) souboru. Další informace najdete v tématu [vsperfreport –](../profiling/vsperfreport.md).  
  
### <a name="to-generate-an-etw-report"></a>Při generování sestav trasování událostí pro Windows  
  
-   V **příkazového řádku** okno, zadejte následující příkaz:  
  
     *ToolsPath* **vsperfreport –** *VSPFile***/Summary:ETW [XML]**  
  
    |||  
    |-|-|  
    |*ToolsPath*|Cesta nástroj nástrojích pro profilaci. Další informace najdete v tématu [zadejte cestu k nástroje příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|  
    |*VSPFile*|Data profilování (. *Vsp* nebo. *vsps*) souboru. Úplné a částečné cesty, jsou přijaty.|  
    |XML|V kódu XML generuje sestavy, který je naformátovaný.|
