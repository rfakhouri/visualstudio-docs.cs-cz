---
title: Zobrazení stromu volání – Data vzorkování | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method,Call Tree view
- Call Tree view
ms.assetid: 5c4e8ec3-d0d3-485a-93bd-9060df4eb739
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c71ff415ea121f5fb8a28eb8365e601414ba5d0a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53917485"
---
# <a name="call-tree-view---sampling-data"></a>Zobrazení stromu volání – data vzorkování
Zobrazení stromu volání zobrazí cesty spuštění funkce, které byly Procházet v profilované aplikaci.  
  
> [!NOTE]
>  Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Kořen stromu je vstupním bodem do aplikace nebo komponenty. Každý uzel funkce obsahuje všechny funkce, které ji volaly a údaje o výkonu o volání těchto funkcí.  
  
 Hodnoty v zobrazení stromu volání jsou pro instance funkce, které byly volány nadřazené funkce ve stromu volání. Procentní hodnoty se počítá srovnáním hodnota instance funkce, která má celkový počet vzorků při spuštění profilování.  
  
## <a name="highlight-the-execution-hot-path"></a>Zvýrazněte provádění kritickou cestu  
 Zobrazení stromu volání můžete rozbalit a zvýraznit cestu spuštění procesu nebo funkce, která je Vzorkovaná nejčastěji. Zobrazení nejaktivnějších cesty, procesu nebo funkce klikněte pravým tlačítkem a pak klikněte na **rozbalit kritickou cestu**.  
  
## <a name="set-the-call-tree-root-node"></a>Nastavit kořenový uzel stromu volání  
 Každý proces při spuštění profilování se zobrazí jako kořenový uzel. Pokud chcete nastavit počáteční uzel zobrazení stromu volání, klikněte pravým tlačítkem na uzel, který chcete nastavit jako počáteční uzel a vyberte **nastavit kořenový**.  
  
 Když nastavíte kořenový uzel, odstraníte všechny položky ze zobrazení s výjimkou podstrom vybraný uzel. Obnovit původní uzel kořenový uzel, klikněte pravým tlačítkem v okně zobrazení stromu volání a vyberte **resetování kořenového**.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID procesu**|ID procesu (PID) běhu profilování.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje funkci.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
|**Název funkce**|Plně kvalifikovaný název funkce.|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Adresa funkce**|Adresa funkce.|  
|**Úroveň**|Hloubka tuto funkci ve stromu volání. Pouze v [VSPerfReport](../profiling/vsperfreport.md) příkazového řádku sestavy.|  
|**Výhradní vzorky**|Počet vzorků, které byly shromážděny v této funkci, když se jmenovala nadřazené funkce ve stromu volání. Toto číslo nezahrnuje ukázky, které byly shromážděny v funkce, které byly volány funkce.|  
|**% Výhradních vzorků**|Procento všechny ukázky během spuštění profilování, které byly výhradních vzorků této funkce, když se jmenovala nadřazené funkce ve stromu volání.|  
|**Celkových vzorků**|Počet vzorků, které byly shromážděny v této funkci, když se jmenovala nadřazené funkce ve stromu volání. Toto číslo zahrnuje ukázky, které byly shromážděny ve funkcích, které byly volány funkce.|  
|**% Celkových vzorků**|Procento všechny ukázky během spuštění profilování, které byly celkových vzorků této funkce, když se jmenovala nadřazené funkce ve stromu volání.|  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení stromu volání – data vzorkování profileru](../profiling/call-Tree-view-sampling-data.md)   
 [Strom volání zobrazení – vzorkování](../profiling/call-tree-view-dotnet-memory-sampling-data.md)   
 [Zobrazení stromu volání – instrumentace](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [Zobrazení stromu volání](../profiling/call-tree-view-instrumentation-data.md)