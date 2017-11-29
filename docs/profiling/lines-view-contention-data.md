---
title: "Zobrazení řádků – Data kolizí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Lines view
ms.assetid: 859b02d2-eddf-4ad3-95de-0df67ee2ab03
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 88b8169f5e0e53a76ff2b1bee61dc80f41a9f595
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="lines-view---contention-data"></a>Zobrazení řádků – Data kolizí
Zobrazení řádků dat kolizí uvádí údaje o výkonu pro příkazy, které byly prováděny, kdy ukázky byly shromážděny v profilaci spustit. Ve zdrojovém souboru příkaz může mít rozsah více než jeden řádek v souboru zdroje a jeden řádek může obsahovat více než jeden výraz.  
  
 Příkaz je identifikována následující data:  
  
-   Zdrojový soubor, který obsahuje příkaz funkce.  
  
-   Funkce, která obsahuje příkaz.  
  
-   Zdrojového řádku, od kterého začne příkaz.  
  
-   Znak v řádku zdroje, od kterého začne příkaz.  
  
-   Řádku zdroje, u které končí příkaz.  
  
-   Znak v řádku zdroje, u které končí příkaz.  
  
 Sloupec názvu řádku poskytuje řazení zřetězení dat identifikátor.  
  
 Následující tabulka popisuje sloupce řádky zobrazit sestavu.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Výhradní blokované čas**|Množství času, během kterého byl zablokován spuštěním kódu v příkazu z důvodu kolizní událostí tohoto prohlášení. Blokované čas v funkce, které volá příkaz není součástí.|  
|**Výhradní blokované čas: %**|Procento všech blokovaných času v procesu, který byl výhradní blokované čas příkaz.|  
|**Výhradní kolizí**|Počet pokusů, které tento příkaz byl zablokován spuštěním kódu v příkazu z důvodu kolizní událostí. Kolizní události ve funkcích, které volá příkaz nejsou zahrnuty.|  
|**% Výhradní kolizí**|Procento kolizní události v procesu, které byly výhradní kolizí tohoto prohlášení.|  
|**Adresa funkce**|Adresa funkce, která obsahuje tento příkaz.|  
|**Název funkce**|Plně kvalifikovaný název funkce, která obsahuje tento příkaz.|  
|**Blokované čas (včetně).**|Volá se v příkazu blokované čas v tento příkaz a funkce.|  
|**Včetně blokované čas: %**|Procento všech blokovaných času v procesu, který byl včetně blokované čas příkaz.|  
|**Kolizí (včetně).**|Počet pokusů, tento příkaz a funkce, které byly volat v příkazu nebyly blokované spuštění.|  
|**% Kolizí (včetně).**|Procento kolizní události v procesu, které byly včetně kolizí tohoto prohlášení.|  
|**Název řádku**|Generované profileru identifikátor řádku. Identifikátor se používá následující syntaxe:`SourceFile`**; [** `LineNumberStart` **,**`CharacterStart`**] ->; [**`LineNumberEnd`**,**`CharacterEnd`**]**|  
|**Číslo řádku – funkce**|Číslo řádku spuštění této funkce ve zdrojovém souboru.|  
|**Název modulu**|Název modul, který obsahuje příkaz.|  
|**Cesta modulu**|Cesta modul, který obsahuje příkaz.|  
|**ID procesu**|ID procesu (PID) PROFILOVANÉHO procesu.|  
|**Název procesu**|Název procesu.|  
|**Začátek znaku zdroje**|Posun počáteční znak v řádku souboru zdroje, ve kterém se spustí tento příkaz.|  
|**End znaku zdroje**|Posun počáteční znak v řádku souboru zdroje, u které končí tohoto prohlášení.|  
|**Zdrojový soubor**|Název zdrojového souboru, který obsahuje příkaz funkce.|  
|**Začátek řádku zdroje**|Číslo řádku ve zdrojovém souboru, ve kterém se příkaz spustí.|  
|**End řádku zdroje**|Číslo řádku ve zdrojovém souboru, u které končí příkaz.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení řádků](../profiling/lines-view.md)   
 [Zobrazení řádků – vzorkování](../profiling/lines-view-dotnet-memory-sampling-data.md)   
 [Zobrazení řádků](../profiling/lines-view-sampling-data.md)