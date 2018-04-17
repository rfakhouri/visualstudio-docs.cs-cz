---
title: Vytváření sestav profileru z příkazového řádku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f371c324b94c20a300b7f96582c187ee2e61ad03
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="creating-profiler-reports-from-the-command-line"></a>Vytváření sestav profileru z příkazového řádku
**Vsperfreport –** nástroj příkazového řádku můžete vytvořit .xml nebo hodnot oddělených čárkami (.csv) sestavy z profilace soubory dat (.vsp). Typy sestav nástroje VSPerfReport přesně odpovídají zobrazením založeným na tabulkách rozhraní pro sadu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Sestavu můžete filtrovat a zobrazit pouze váš kód a také zobrazit pouze část souboru dat profilování. Další informace najdete v tématu [vsperfreport –](../profiling/vsperfreport.md).  
  
 Soubory dat profilování lze také jednodušeji sdílet vložením symbolů do souboru .vsp a vytvořením předem analyzovaných souborů sestav (.vsps), které jsou menší a rychleji se otevírají.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Vytvořte základní sestavu.** Vytvořte všechny nebo část typů sestav VSPerfReport.|-   [Vytváření základních sestav](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|  
|**Porovnejte dvě datových souborů profilování.** Vytvořte sestavu „diff“, která porovnává data o výkonu ve dvou souborech dat profilování.|-   [Postupy: vytvoření sestavy porovnání profileru z příkazového řádku](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|  
|**Trasování volání zobrazení a data události trasování pro Windows (ETW).** Vytvořte sestavu trasování volání, která uvádí informace o časování pro jednotlivé body vstupu a výstupu funkcí aplikace a každé volání ostatních funkcí pomocí vaší funkce. Nebo vytvořte podrobný seznam všech událostí ETW, které byly shromážděny během spuštění profilování.|-   [Postupy: vytvoření sestavy trasování volání](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|  
|**Filtrování sestavy.** Omezte sestavy pouze tyto funkce ve vašem kódu nebo v určený čas v profilaci datového souboru.|-   [Postupy: filtrování sestav z příkazového řádku](../profiling/how-to-filter-reports-from-the-command-line.md)|  
|**Vytváření přenosných datových souborů profilování.** Chcete-li sdílet data profilování snadněji, lze vložit symboly pro běh profilování do souboru .vsp. Můžete také vytvořit předem analyzovaný soubor dat profilování (.vsps), který je menší a lze jej rychleji otevřít.|-   [Vytváření přenosných datových souborů profilace](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|