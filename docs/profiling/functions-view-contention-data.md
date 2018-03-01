---
title: "Zobrazení funkcí – Data kolizí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Functions view
ms.assetid: 208773b0-1a54-4b7a-ad37-2b6fd4f731d4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d9dcf9ab34e5d0441f3c1ce3a47d5e148c9394d0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="functions-view---contention-data"></a>Zobrazení funkcí – Data kolizí
Sestavy funkce Zobrazit seznamů dat kolizí funkce v profilaci spuštění, které byly blokované ze spuštění během spuštění profilování.  
  
 Následující tabulka vysvětluje hodnoty, které se zobrazují v zobrazení funkce profilování datový soubor, který byl shromážděn pomocí metoda souběžného zpracování.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Výhradní blokované čas**|Množství času, během kterého byl zablokován spuštěním kódu v těle funkce této funkce. Blokované čas v funkce, které byly volá funkci není součástí.|  
|**Výhradní blokované čas: %**|Procento všech blokovaných času v profilaci spuštění, který byl časový výhradní blokované této funkce.|  
|**Výhradní kolizí**|Počet pokusů, které tuto funkci byl zablokován spuštěním kódu v těle funkce. Kolizí ve funkcích, které byly volá funkci nejsou zahrnuty.|  
|**% Výhradní kolizí**|Procento všech kolizí v profilaci spustit byly výhradní kolizí této funkce.|  
|**Adresa funkce**|Adresa funkce.|  
|**Název funkce**|Plně kvalifikovaný název funkce.|  
|**Blokované čas (včetně).**|Čas, tato funkce nebo funkce, která byla volána pomocí této funkce byl zablokován provádění.|  
|**Včetně blokované čas: %**|Procento všech blokovaných času v profilaci spustit, který byl včetně blokované čas tento modul nebo funkce.|  
|**Kolizí (včetně).**|Počet pokusů, které tuto funkci nebo funkci, která byla volána pomocí této funkce byl zablokován provádění.|  
|**% Kolizí (včetně).**|Procento všech kolizí v profilaci spuštění, které byly včetně kolizí této funkce nebo modul.|  
|**Číslo řádku – funkce**|Číslo řádku spuštění této funkce ve zdrojovém souboru.|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta modulu**|Cesta modul, který obsahuje funkce.|  
|**ID procesu**|ID procesu (PID) procesu, ve kterém se provádí funkce.|  
|**Název procesu**|Název procesu.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení funkcí](../profiling/functions-view.md)   
 [Zobrazení funkcí – instrumentace](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [Zobrazení funkcí – vzorkování](../profiling/functions-view-dotnet-memory-sampling-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-instrumentation-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-sampling-data.md)