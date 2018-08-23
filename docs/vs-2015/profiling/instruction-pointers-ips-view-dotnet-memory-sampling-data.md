---
title: Zobrazení ukazatelů na instrukce – Data vzorkování paměti .NET | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: 7d91cc14-e8e9-4ebb-b14f-b9f0da770508
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 21141483d462df0faee099c22e2b79fc1718880d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628828"
---
# <a name="instruction-pointers-ips-view---net-memory-sampling-data"></a>Zobrazení ukazatelů na instrukce – data vzorkování paměti .NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [zobrazení ukazatele na instrukce (IP) – Data vzorkování paměti .NET](https://docs.microsoft.com/visualstudio/profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data).  
  
Zobrazení IP adres pro .NET profilování data o přidělování paměti, která byla shromážděna pomocí metody vzorkování uvádí instrukce sestavení, které přidělené paměti během spuštění profilování. Sloupce zobrazení také seznam velikost a počet přidělení.  
  
 Pouze výhradní hodnoty jsou uvedeny.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID procesu**|ID procesu (PID) běhu profilování.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modulu, který obsahuje instrukce.|  
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje instrukce.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje instrukce.|  
|**Název funkce**|Název funkce.|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Adresa funkce**|Počáteční adresa funkce.|  
|**Začátek řádku zdroje**|Počáteční řádek číslo ve zdrojovém souboru, ve kterém došlo k chybě přidělení paměti.|  
|**Konec řádku zdroje**|Koncové číslo řádku ve zdrojovém souboru, ve kterém došlo k chybě přidělení paměti.|  
|**Počáteční znak zdrojového kódu**|Odsazení počátečního znaku ve zdrojovém souboru řádku, ve kterém došlo k chybě přidělení paměti.|  
|**Koncový znak zdrojového kódu**|Posun koncového znaku ve zdrojovém souboru řádku, ve kterém došlo k chybě přidělení paměti.|  
|**Adresa instrukce**|Adresa instrukce.|  
|**Výhradní přidělení**|Celkový počet objektů, které byly vytvořeny podle pokynů.|  
|**% Výhradních přidělení**|Procento všech objektů, které byly vytvořeny při spuštění profilace, které byly přiděleny podle pokynů.|  
|**Výhradní bajty**|Počet bajtů paměti, které byly přiděleny v profilování, které byly přiděleny podle pokynů.|  
|**% Výhradních bajtů**|Procento všech počet bajtů paměti, které byly přiděleny při spuštění profilace, které byly přiděleny podle pokynů.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení ukazatelů na instrukce](../profiling/instruction-pointers-ips-view-sampling-data.md)



