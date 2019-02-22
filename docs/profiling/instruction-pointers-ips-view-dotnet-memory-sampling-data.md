---
title: Zobrazení ukazatelů na instrukce – Data vzorkování paměti .NET | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: 7d91cc14-e8e9-4ebb-b14f-b9f0da770508
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 8443f17507b7e4225e6f04d914c115bf17f7d091
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56627022"
---
# <a name="instruction-pointers-ips-view---net-memory-sampling-data"></a>Zobrazení ukazatelů na instrukce – data vzorkování paměti .NET
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

## <a name="see-also"></a>Viz také:
- [Zobrazení ukazatelů na instrukce](../profiling/instruction-pointers-ips-view-sampling-data.md)