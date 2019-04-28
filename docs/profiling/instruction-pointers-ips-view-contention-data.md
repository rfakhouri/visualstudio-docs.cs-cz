---
title: Zobrazení ukazatelů na instrukce – Data kolizí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: f5e49c24-d4cf-4f87-977d-37e3223d1196
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d41f48594e50e9d5ae0c6f67aabab673a9f112a3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62995393"
---
# <a name="instruction-pointers-ips-view---contention-data"></a>Zobrazení ukazatelů na instrukce – data kolizí
IP adresy zobrazení dat kolizí zobrazí seznam dat pro instrukce sestavení, které se zablokoval spuštění při spuštění profilace.

 Následující tabulka vysvětluje hodnoty sloupců v zobrazení ukazatele na instrukce.

|Sloupec|Popis|
|------------|-----------------|
|**Výhradní čas zablokování**|Čas zablokování touto funkcí.|
|**% Výhradního času zablokování**|Procento času zablokování, když se provedl podle pokynů.|
|**Výhradní spory**|Počet sporů, ke kterým došlo během instrukce se spustil.|
|**% Výhradních sporů**|Procento všech sporů při spuštění profilace, ke kterým došlo během instrukce se spustil.|
|**Adresa funkce**|Počáteční adresa paměti pro funkci načíst binárního souboru.|
|**Název funkce**|Název funkce, která obsahuje instrukce.|
|**Adresa instrukce**|Adresa paměti podle pokynů v načíst binární soubor.|
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|
|**Název modulu**|Název modulu, který obsahuje instrukce.|
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje instrukce.|
|**ID procesu**|ID procesu (PID) PROFILOVANÉHO procesu.|
|**Název procesu**|Název procesu.|
|**Počáteční znak zdrojového kódu**|Odsazení znaku ve zdrojovém souboru řádku, ve kterém tento pokyn začne.|
|**Koncový znak zdrojového kódu**|Odsazení znaku ve zdrojovém souboru řádku, ve kterém tento pokyn končí.|
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje instrukce.|
|**Začátek řádku zdroje**|Číslo řádku ve zdrojovém souboru, ve kterém tento pokyn začne.|
|**Konec řádku zdroje**|Číslo řádku ve zdrojovém souboru, ve kterém tento pokyn skončí.|

## <a name="see-also"></a>Viz také:
- [Postupy: Přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)
- [Zobrazení ukazatelů na instrukce](../profiling/instruction-pointers-ips-view.md)
- [Ukazatele na instrukce (IP) zobrazení – vzorkování](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)
- [Zobrazení ukazatelů na instrukce](../profiling/instruction-pointers-ips-view-sampling-data.md)