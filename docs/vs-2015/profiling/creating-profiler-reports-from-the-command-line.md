---
title: Vytváření sestav Profiler z příkazového řádku | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d94a2c6c025ada73e1d43e041c2bf6e30f8b66c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668380"
---
# <a name="creating-profiler-reports-from-the-command-line"></a>Vytváření sestav profileru z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Profiler vytváření sestav z příkazového řádku](https://docs.microsoft.com/visualstudio/profiling/creating-profiler-reports-from-the-command-line).  
  
**VSPerfReport** nástroj příkazového řádku vám umožní vytvořit .xml nebo sestavy hodnot oddělených čárkami (.csv) z profilování (.vsp) datové soubory. Typy sestav nástroje VSPerfReport přesně odpovídají zobrazením založeným na tabulkách rozhraní pro sadu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Sestavu můžete filtrovat a zobrazit pouze váš kód a také zobrazit pouze část souboru dat profilování. Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).  
  
 Soubory dat profilování lze také jednodušeji sdílet vložením symbolů do souboru .vsp a vytvořením předem analyzovaných souborů sestav (.vsps), které jsou menší a rychleji se otevírají.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Vytvoření základní sestavy.** Vytvořte všechny nebo část typů sestav VSPerfReport.|-   [Vytváření základních sestav](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|  
|**Porovnání dvou souborů dat profilování.** Vytvořte sestavu „diff“, která porovnává data o výkonu ve dvou souborech dat profilování.|-   [Postupy: vytvoření sestavy porovnání Profiler z příkazového řádku](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|  
|**Zobrazení trasování volání a dat událostí trasování pro Windows (ETW).** Vytvořte sestavu trasování volání, která uvádí informace o časování pro jednotlivé body vstupu a výstupu funkcí aplikace a každé volání ostatních funkcí pomocí vaší funkce. Nebo vytvořte podrobný seznam všech událostí ETW, které byly shromážděny během spuštění profilování.|-   [Postupy: vytvoření sestavy trasování volání](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|  
|**Filtrování sestavy.** Omezte sestavu pouze na funkce ve vašem kódu nebo na určitou dobu v souboru dat profilování.|-   [Postupy: filtrování sestav z příkazového řádku](../profiling/how-to-filter-reports-from-the-command-line.md)|  
|**Vytváření přenosných datových souborů profilace.** Chcete-li sdílet data profilování snadněji, lze vložit symboly pro běh profilování do souboru .vsp. Můžete také vytvořit předem analyzovaný soubor dat profilování (.vsps), který je menší a lze jej rychleji otevřít.|-   [Vytváření přenosných datových souborů profilace](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|



