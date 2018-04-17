---
title: Přidělení paměti .NET – zobrazení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.allocation
helpviewer_keywords:
- performance reports, allocation view
- Allocations view
- profiling tools, Allocation view
- profiling tools reports, Allocation view
ms.assetid: 01eb876e-c413-4516-977b-4f896929e8a6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ef4e52257941192b12a2f7eb57393a536ab02e32
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="net-memory-allocations-view"></a>Přidělení paměti .NET – zobrazení
Zobrazení přidělení obsahuje typy, které byly vytvořeny při profilování spustit. Každý typ je kořenový uzel stromu volání, která zobrazuje funkce cesty provádění, jejichž výsledkem přidělení typu.  
  
 Data v řádku typ zobrazí celkový počet objektů typu, které byly vytvořeny při spuštění profilování a celkový počet bajtů přidělených pro objekty daného typu. (Včetně) a výhradní hodnoty pro typ jsou vždy stejné.  
  
-   (Včetně). hodnoty jsou pro objekty vytvořené v instance funkce a jeho podřízené funkce, které byly volá funkci nadřazené ve stromové struktuře volání.  
  
-   Hodnot, které jsou pro objekty, které byly vytvořeny přímo pomocí funkce při byly volání funkcí nadřazené. Objekty vytvořené v podřízených funkce nejsou zahrnuty.  
  
 Data pro funkce zobrazuje počet objekty vytvořené a počet bajtů přidělených pro objekty typu nadřazený.  
  
## <a name="highlighting-the-execution-hot-path"></a>Zvýraznění aktivní trase provádění  
 Můžete najít cestu spuštění stromu volání, který vytvořili většinu objektů typu nadřazený.  
  
-   Zobrazení Nejaktivnější cesty, klikněte pravým tlačítkem na typ nebo funkci a pak klikněte na tlačítko **rozbalte aktivní trase**.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název přidělené typ nebo funkci.|  
|**ID procesu**|ID procesu (PID) z profilace spustit.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modul, který obsahuje typ nebo funkci.|  
|**Cesta modulu**|Cesta modul, který obsahuje typ nebo funkci.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro typ nebo funkci.|  
|**Číslo řádku – funkce**|Číslo řádku spouštění této definici typu nebo funkce v zdrojový soubor.|  
|**úroveň**|Určuje, zda data pro určitý typ nebo funkci.|  
|**Přidělení (včetně).**|-Pro funkce, celkový počet objektů nadřazený typ, které byly vytvořené pomocí funkce. Tato hodnota zahrnuje objekty vytvořené v podřízených funkce.<br />– Pro typ, celkový počet instancí tohoto typu, které byly vytvořeny.|  
|**% Přidělení (včetně).**|-Pro funkce, procento všechny objekty vytvořené v profilaci spuštění, které byly včetně přidělení nadřazený typ funkce.<br />– Pro typ procento celkový počet objektů, které byly vytvořeny v profilaci spuštění, které byly instance typu.|  
|**Výhradní přidělení**|-Pro funkce, počet objektů, které byly vytvořeny při provádění funkce přímo v horní části zásobníku volání. Toto číslo nezahrnuje objekty vytvořené v podřízených funkce.<br />– Pro typ, celkový počet instancí tohoto typu, které byly vytvořeny.|  
|**Výhradní přidělení %**|-Pro funkce, procento všechny objekty vytvořené v profilaci spuštění, které byly výhradní přidělení nadřazený typ funkce.<br />– Pro typ procento celkový počet objektů, které byly vytvořeny v profilaci spuštění, které byly instance typu.|  
|**Bajtů (včetně).**|-Pro funkce, počet bajtů paměti, které byly přiděleny funkce pro objekty typu nadřazený. Tato hodnota zahrnuje paměti, která byla přidělena podle jeho podřízené funkce.<br />– Pro typ, celkový počet bajtů, který byl přidělen v profilaci spustit pro instance typu.|  
|**% Bajtů (včetně).**|-Pro funkci byl procento paměti všechny přidělené v profilaci spustit, včetně přidělení nadřazený typ funkce.<br />– Pro typ procento paměti všechny přidělené v profilaci spuštění, který byl přidělen pro instance typu.|  
|**Výhradní bajtů**|-Pro funkce, počet bajtů paměti, které byly přiděleny funkce pro objekty typu nadřazený. Toto číslo nezahrnuje paměti, která byla přidělena podle jeho podřízené funkce.<br />– Pro typ celkový počet bajtů, které byly přiděleny v profilaci spustit pro instance typu.|  
|**% Výhradní bajtů**|-Pro funkci procento paměti všechny přidělené v profilaci spuštění, který byl výhradní přidělení nadřazený typ funkce.<br />– Pro typ procento paměti všechny přidělené v profilaci spuštění, který byl přidělen pro instance typu.|