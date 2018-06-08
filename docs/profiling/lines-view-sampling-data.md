---
title: Zobrazení řádků – vzorkování dat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Lines view
ms.assetid: 46497249-c797-42c5-a02c-3e4bb3b4ee60
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6f73db7e52c22291443ec262eb2f91ffbcd319c7
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845087"
---
# <a name="lines-view---sampling-data"></a>Zobrazení řádků – data vzorkování
Zobrazení dat vzorkování uvádí údaje o výkonu pro příkazy, které byly prováděny, kdy ukázky byly shromážděny v profilaci řádky spustit.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Ve zdrojovém souboru příkaz může mít rozsah více než jeden řádek v souboru zdroje a jeden řádek může obsahovat více než jeden výraz. Příkaz je identifikována následující:  
  
-   Zdrojový soubor, který obsahuje příkaz funkce.  
  
-   Funkce, která obsahuje příkaz.  
  
-   Řádku zdroje, při které začne příkaz.  
  
-   Znak v řádku zdroje, od kterého začne příkaz.  
  
-   Řádku zdroje, u které končí příkaz.  
  
-   Znak v řádku zdroje, u které končí příkaz.  
  
 Sloupec názvu řádku poskytuje řazení zřetězení dat identifikátor.  
  
 Podle definice příkaz nevyvolá dalších funkcí. Proto jsou uvedeny pouze výhradní hodnoty.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID procesu**|ID procesu (PID) z profilace spustit.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modul, který obsahuje řádek funkce.|  
|**Cesta modulu**|Cesta modul, který obsahuje řádek funkce.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje řádek funkce.|  
|**Název funkce**|Název funkce.|  
|**Číslo řádku – funkce**|Číslo řádku spuštění této funkce ve zdrojovém souboru.|  
|**Adresa funkce**|Počáteční adresa funkce.|  
|**Začátek řádku zdroje**|Počáteční řádek číslo ve zdrojovém souboru, kdy byl shromážděn této ukázce.|  
|**End řádku zdroje**|Koncová číslo řádku ve zdrojovém souboru, kdy byl shromážděn této ukázce.|  
|**Začátek znaku zdroje**|Posun počáteční znak v řádku souboru původního, kdy byl shromážděn této ukázce.|  
|**End znaku zdroje**|Posun ukončovací znak v řádku souboru zdroje, kdy byl shromážděn této ukázce.|  
|**Název řádku**|Identifikátor generovaný profileru řádku pomocí následující syntaxe:`Source File`**; [** `Line Number Start` **,**`Character Start`**] ->; [**`Line Number End`**,**`Character End`**]**|  
|**Výhradní ukázky**|Celkový počet vzorků, které byly shromážděny při provádění funkce řádku.|  
|**% Výhradní ukázky**|Procento všechny ukázky v profilaci spuštění, které byly shromážděny při provádění funkce řádku.|  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení řádků – vzorkování](../profiling/lines-view-dotnet-memory-sampling-data.md)