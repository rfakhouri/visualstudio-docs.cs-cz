---
title: 'Postupy: Vytvoření sestavy trasování volání nástrojů pro profilaci | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dfe32847a37453b6a24a58538b2642fba66e4971
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63439118"
---
# <a name="how-to-create-a-profiling-tools-call-trace-report"></a>Postupy: Vytvoření sestavy trasování volání nástrojů pro profilaci
*Zpráva sledování volání* pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů pro profilaci sady uvádí informace o časování pro každý bod vstupu a výstupu funkcí aplikace a každé volání ostatních funkcí pomocí vaší funkce. Zprávy sledování volání jsou k dispozici pro data profilování pouze v případě, že byla shromážděna pomocí metody instrumentace.

> [!NOTE]
> Nelze zobrazit zprávy sledování volání v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Je nutné použít **VSPerfReport** nástroj příkazového řádku pro generování hodnot oddělených čárkami (. *sdílený svazek clusteru*) nebo. *xml* souboru. Další informace o tomto nástroji najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).

### <a name="to-create-a-call-trace-report"></a>K vytvoření sestavy trasování volání

1. Otevřít **příkazového řádku** okna.

2. V příkazovém řádku zadejte následující příkaz:

     *ToolsPath* **VSPerfReport** *VSPFile*  **/CallTrace [/Xml]**

    |||
    |-|-|
    |*ToolsPath*|Cesta nástroje příkazového řádku nástroje pro profilaci. Další informace najdete v tématu [zadejte cestu k nástroji příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|
    |*VSPFile*|Dat profilování (. *Vsp* nebo. *vsps*) soubor. Jsou přijímány úplné a částečné cesty.|
    |XML|Generuje zprávu ve formátu XML.|

## <a name="see-also"></a>Viz také:
- [Postupy: Shromažďování dat trasování událostí pro Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)
- [Nástroje rozhraní API pro profilaci](../profiling/profiling-tools-apis.md)
