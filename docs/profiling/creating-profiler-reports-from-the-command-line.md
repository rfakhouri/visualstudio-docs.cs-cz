---
title: Vytváření sestav Profiler z příkazového řádku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6a6d31d15f7f7ed533d73683a3c12d152bd7046
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62552899"
---
# <a name="create-profiler-reports-from-the-command-line"></a>Vytváření sestav profileru z příkazového řádku
**VSPerfReport** nástroj příkazového řádku vám umožní vytvořit. *XML* nebo hodnot oddělených čárkami (. *sdílený svazek clusteru*) sestavy z dat profilování (. *Vsp*) soubory. Typy sestav nástroje VSPerfReport přesně odpovídají zobrazením založeným na tabulkách rozhraní pro sadu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Sestavu můžete filtrovat a zobrazit pouze váš kód a také zobrazit pouze část souboru dat profilování. Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).

 Můžete provést také soubory dat profilování snadněji sdílet vložením symbolů do. *vsp* soubory a vytvořením předem analyzovaných sestavy (. *vsps*) soubory, které jsou menší a rychleji se otevírají.

## <a name="common-tasks"></a>Běžné úkoly

|Úloha|Související obsah|
|----------|---------------------|
|**Vytvoření základní sestavy.** Vytvořte všechny nebo část typů sestav VSPerfReport.|-   [Vytváření základních sestav](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|
|**Porovnání dvou souborů dat profilování.** Vytvořte sestavu „diff“, která porovnává data o výkonu ve dvou souborech dat profilování.|-   [Jak: Vytvoření sestavy porovnání profileru z příkazového řádku](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|
|**Zobrazení trasování volání a dat událostí trasování pro Windows (ETW).** Vytvořte sestavu trasování volání, která uvádí informace o časování pro jednotlivé body vstupu a výstupu funkcí aplikace a každé volání ostatních funkcí pomocí vaší funkce. Nebo vytvořte podrobný seznam všech událostí ETW, které byly shromážděny během spuštění profilování.|-   [Jak: Vytvoření sestavy trasování volání](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|
|**Filtrování sestavy.** Omezte sestavu pouze na funkce ve vašem kódu nebo na určitou dobu v souboru dat profilování.|-   [Jak: Filtr sestavy z příkazového řádku](../profiling/how-to-filter-reports-from-the-command-line.md)|
|**Vytváření přenosných datových souborů profilace.** Chcete-li sdílet data profilování snadněji, lze vložit symboly pro běh profilování do. *vsp* souboru. Můžete také vytvořit předem analyzovaný dat profilování (. *vsps*) soubor, který je menší a rychleji se otevírají.|-   [Vytváření přenosných datových souborů profilace](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|