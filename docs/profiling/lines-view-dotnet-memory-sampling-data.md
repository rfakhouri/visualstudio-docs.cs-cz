---
title: "Zobrazení řádků – Data vzorkování paměti .NET | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Lines view
ms.assetid: 6631ab87-0e62-4c76-a063-4ea7222b07da
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 291cb024413072a6e07cbe46a2679994f7bd3315
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="lines-view---net-memory-sampling-data"></a>Zobrazení řádků – Data vzorkování paměti .NET
Zobrazení řádků pro data paměti .NET přidělení profilování využívající metody vzorkování uvádí příkazy, které přidělené paměti při spuštění profilování. Sloupce, které zahrnují také velikost a počet přidělených.  
  
 Ve zdrojovém souboru příkaz může mít rozsah více než jeden řádek v souboru zdroje a jeden řádek může obsahovat více než jeden výraz.  
  
 Příkaz je identifikována následující:  
  
-   Zdrojový soubor, který obsahuje příkaz funkce.  
  
-   Funkce, která obsahuje příkaz.  
  
-   Zdrojového řádku, od kterého začne příkaz.  
  
-   Znak v řádku zdroje, od kterého začne příkaz.  
  
-   Řádku zdroje, u které končí příkaz.  
  
-   Znak v řádku zdroje, u které končí příkaz.  
  
 Sloupec názvu řádku poskytuje řazení zřetězení dat identifikátor.  
  
 Podle definice příkaz nevyvolá dalších funkcí. Proto jsou uvedeny pouze výhradní hodnoty.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID procesu**|ID procesu (PID) z profilace spustit.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modul, který obsahuje příkaz.|  
|**Cesta modulu**|Cesta modul, který obsahuje příkaz.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje příkaz.|  
|**Název funkce**|Název funkce, která obsahuje příkaz.|  
|**Číslo řádku – funkce**|Číslo řádku spuštění této funkce ve zdrojovém souboru.|  
|**Adresa funkce**|Počáteční adresa funkce.|  
|**Začátek řádku zdroje**|Počáteční řádek číslo ve zdrojovém souboru, kdy došlo k chybě přidělení.|  
|**End řádku zdroje**|Koncová číslo řádku ve zdrojovém souboru, kdy došlo k chybě přidělení.|  
|**Začátek znaku zdroje**|Posun počáteční znak v řádku souboru zdroje, kdy došlo k přidělení.|  
|**End znaku zdroje**|Posun ukončovací znak v řádku souboru zdroje, kdy došlo k přidělení.|  
|**Název řádku**|Identifikátor generovaný profileru řádku pomocí následující syntaxe:`Source File`**; [** `Line Number Start` **,**`Character Start`**] ->; [**`Line Number Start,Character Start`**]**|  
|**Výhradní přidělení**|Celkový počet objektů, které byly vytvořeny v tomto řádku.|  
|**Výhradní přidělení %**|Procento všechny objekty vytvořené v profilaci spuštění, které byly přiděleny na tomto řádku.|  
|**Výhradní bajtů**|Procento všech bajtů paměti, které byly přiděleny v profilaci spuštění, které byly přiděleny na tomto řádku.|  
|**% Výhradní bajtů**|Procento všech bajtů paměti, které byly přiděleny v profilaci spuštění, které byly přiděleny na tomto řádku.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení řádků](../profiling/lines-view-sampling-data.md)