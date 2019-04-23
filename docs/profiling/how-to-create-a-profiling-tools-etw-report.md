---
title: 'Postupy: Vytvoření sestavy trasování událostí pro Windows nástrojů pro profilaci | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: bf5547b3-f6c7-4989-9d47-2fe4f1261444
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 48946a5e12431cf00e296f445adab657f6c1a959
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60101961"
---
# <a name="how-to-create-a-profiling-tools-etw-report"></a>Postupy: Vytvoření sestavy Trasování událostí pro Windows nástrojů pro profilaci
Sestava trasování událostí pro Windows (ETW) obsahuje události trasování událostí pro Windows, které jsou zaznamenány v relaci výkonu z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje pro profilaci. Data trasování událostí pro Windows se shromažďují v binárním (. *ETL*) soubor. Další informace o této sestavě najdete v tématu [sestavy trasování událostí pro Windows (ETW)](../profiling/event-tracing-for-windows-etw-report.md).

> [!NOTE]
>  Nelze zobrazit sestavy trasování událostí pro Windows v rozhraní [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

- Informace o tom, jak shromažďování dat trasování událostí pro Windows pomocí rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], naleznete v tématu [jak: Shromažďování dat trasování událostí pro Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).

- Informace o tom, jak shromažďovat data trasování událostí pro Windows z příkazového řádku najdete v tématu [VSPerfCmd](../profiling/vsperfcmd.md) a [události](../profiling/events-vsperfcmd.md).

  Generování sestavy trasování událostí pro Windows pomocí **VSReport / summary: etw** příkazu. Na. *etl* trasování událostí pro Windows, který obsahuje data musí být ve stejném adresáři jako dat profilování (. *Vsp* nebo. *vsps*) soubor. Ve výchozím nastavení je sestava generována jako hodnoty oddělené čárkou (. *sdílený svazek clusteru*) soubor. Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).

### <a name="to-generate-an-etw-report"></a>Chcete-li generovat sestavu trasování událostí pro Windows

- V **příkazového řádku** okno, zadejte na příkazovém řádku následující:

     *ToolsPath* **VSPerfReport** *VSPFile*  **/Summary:ETW [/Xml]**

    |||
    |-|-|
    |*ToolsPath*|Cesta nástroje pro profilaci. Další informace najdete v tématu [zadejte cestu k nástroji příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|
    |*VSPFile*|Dat profilování (. *Vsp* nebo. *vsps*) soubor. Jsou přijímány úplné a částečné cesty.|
    |XML|Generuje sestavu, která je ve formátu v jazyce XML.|
