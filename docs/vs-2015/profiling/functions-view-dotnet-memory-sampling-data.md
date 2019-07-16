---
title: Zobrazení funkcí – Data vzorkování paměti .NET | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Functions view
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8e77c6c2b3bf079e8aae88c9779c3b487ff97fe7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68141878"
---
# <a name="functions-view---net-memory-sampling-data"></a>Zobrazení funkcí – data vzorkování paměti .NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zobrazení funkcí data, která byla shromážděna pomocí metody vzorkování profilace přidělování paměti .NET jsou uvedeny funkce, které přidělené paměti během spuštění profilování a sestavy, velikost a počet přidělení.  
  
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
|**Celkově přidělení**|Celkový počet objektů, které byly přiděleny v této funkci a její podřízené funkce.|  
|**% Celkových přidělení**|Procento všech objektů, které byly přiděleny v profilování, která se celkově přidělení této funkce.|  
|**Výhradní přidělení**|Počet objektů, které se vytvořily při provádění funkce přímo v horní části zásobníku volání. Toto číslo nezahrnuje objekty, které byly vytvořeny v podřízené funkce.|  
|**% Výhradních přidělení**|Procento všech objektů, které byly přiděleny v profilování, které byly výhradních přidělení této funkce.|  
|**Celkově bajtů**|Počet bajtů paměti, které byly přiděleny tak, že tuto funkci a její podřízené funkce.|  
|**% Celkových bajtů**|Procento bajtů paměti, které byly přiděleny v profilování, která se celkově bajtů této funkce.|  
|**Výhradní bajty**|Počet bajtů paměti, které byly přiděleny touto funkcí, ale ne její podřízené funkce.|  
|**% Výhradních bajtů**|Procento všech počet bajtů paměti, které byly přiděleny v profilování, které byly výhradních bajtů této funkce.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení funkcí – instrumentace](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-sampling-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-instrumentation-data.md)
