---
title: Zobrazení řádků – Data vzorkování paměti .NET | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Lines view
ms.assetid: 6631ab87-0e62-4c76-a063-4ea7222b07da
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: c654bbcc9db696d78e651414bfa89d6ad1e2f3e3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63000066"
---
# <a name="lines-view---net-memory-sampling-data"></a>Zobrazení řádků – data vzorkování paměti .NET
Zobrazení řádků pro .NET profilování data o přidělování paměti, která používá metody vzorkování seznam příkazů, které přidělené paměti během spuštění profilování. Sloupce, které zahrnují také velikost a počet přidělení.

 Ve zdrojovém souboru příkaz se týkají více než jeden řádek ve zdrojovém souboru a jeden řádek může obsahovat více než jeden výraz.

 Příkaz je identifikován následující:

- Zdrojový soubor, který obsahuje Function – příkaz

- Funkce, která obsahuje příkaz.

- Zdrojový řádek, ve kterém se spustí příkaz.

- Znak ve zdrojovém řádku, ve kterém se spustí příkaz.

- Řádku zdroje, u které končí příkaz.

- Znak ve zdrojovém řádku, kdy příkaz skončí.

  Sloupec název řádek obsahuje seřaditelné zřetězení těchto dat identifikátor.

  Podle definice příkazu nevolá dalších funkcí. Proto jsou uvedeny pouze výhradní hodnoty.

|Sloupec|Popis|
|------------|-----------------|
|**ID procesu**|ID procesu (PID) běhu profilování.|
|**Název procesu**|Název procesu.|
|**Název modulu**|Název modulu, který obsahuje příkaz.|
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje příkaz.|
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje příkaz.|
|**Název funkce**|Název funkce, která obsahuje příkaz.|
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|
|**Adresa funkce**|Počáteční adresa funkce.|
|**Začátek řádku zdroje**|Počáteční řádek číslo ve zdrojovém souboru, ve kterém došlo k chybě přidělení paměti.|
|**Konec řádku zdroje**|Koncové číslo řádku ve zdrojovém souboru, ve kterém došlo k chybě přidělení paměti.|
|**Počáteční znak zdrojového kódu**|Odsazení počátečního znaku ve zdrojovém souboru řádku, ve kterém došlo k chybě přidělení paměti.|
|**Koncový znak zdrojového kódu**|Posun koncového znaku ve zdrojovém souboru řádku, ve kterém došlo k chybě přidělení paměti.|
|**Název čáry**|Identifikátor generovaný profileru řádku pomocí následující syntaxe:`Source File`**; [** `Line Number Start` **,**`Character Start`**] ->; [**`Line Number Start,Character Start`**]**|
|**Výhradní přidělení**|Celkový počet objektů, které byly vytvořeny v tomto řádku.|
|**% Výhradních přidělení**|Procento všech objektů, které byly vytvořeny při spuštění profilace, které byly přiděleny v tomto řádku.|
|**Výhradní bajty**|Procento všech počet bajtů paměti, které byly přiděleny při spuštění profilace, které byly přiděleny v tomto řádku.|
|**% Výhradních bajtů**|Procento všech počet bajtů paměti, které byly přiděleny při spuštění profilace, které byly přiděleny v tomto řádku.|

## <a name="see-also"></a>Viz také:
- [Zobrazení řádků](../profiling/lines-view-sampling-data.md)