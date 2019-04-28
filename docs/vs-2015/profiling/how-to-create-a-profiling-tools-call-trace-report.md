---
title: 'Postupy: Vytvoření sestavy trasování volání nástrojů pro profilaci | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
caps.latest.revision: 24
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 03c039d0059e3e5768681ece9bb547b0f4eb7783
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432751"
---
# <a name="how-to-create-a-profiling-tools-call-trace-report"></a>Postupy: Vytvoření sestavy trasování volání nástrojů pro profilaci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

*Zpráva sledování volání* pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů pro profilaci sady uvádí informace o časování pro každý bod vstupu a výstupu funkcí aplikace a každé volání ostatních funkcí pomocí vaší funkce. Zprávy sledování volání jsou k dispozici pro data profilování pouze v případě, že byla shromážděna pomocí metody instrumentace.  
  
> [!NOTE]
> Nelze zobrazit zprávy sledování volání v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Je nutné použít **VSPerfReport** nástroj příkazového řádku pro generování hodnot oddělených čárkami (CSV) nebo soubor Xml. Další informace o tomto nástroji najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).  
  
### <a name="to-create-a-call-trace-report"></a>K vytvoření sestavy trasování volání  
  
1. Otevřít **příkazového řádku**okno.  
  
2. V příkazovém řádku zadejte následující příkaz:  
  
     *ToolsPath* **VSPerfReport** *VSPFile*  **/CallTrace [/Xml]**  
  
    |||  
    |-|-|  
    |*ToolsPath*|Cesta nástroje příkazového řádku nástroje pro profilaci. Další informace najdete v tématu [zadání cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|  
    |*VSPFile*|Soubor dat profilování (.vsp nebo .vsps). Jsou přijímány úplné a částečné cesty.|  
    |XML|Generuje zprávu ve formátu Xml.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Shromažďovat události trasování pro Windows (ETW) dat.](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)   
 [Rozhraní API nástrojů pro profilaci](../profiling/profiling-tools-apis.md)
