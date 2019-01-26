---
title: Zobrazení funkcí – Data vzorkování paměti .NET | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Functions view
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: b2e25e1106741e3ebb81bbff52fd5bc75368e806
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941113"
---
# <a name="functions-view---net-memory-sampling-data"></a>Zobrazení funkcí – data vzorkování paměti .NET
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
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení funkcí – instrumentace](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-sampling-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-instrumentation-data.md)