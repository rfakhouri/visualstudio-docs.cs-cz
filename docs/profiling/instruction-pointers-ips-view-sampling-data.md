---
title: Zobrazení ukazatelů na instrukce – vzorkování dat | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: c7f647bb-c5a3-4708-9f9d-33c0fd6e2e96
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 579887c22df16d555c3f309b4326740060aefc1f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442226"
---
# <a name="instruction-pointers-ips-view---sampling-data"></a>Zobrazení ukazatelů na instrukce – vzorkování dat
Zobrazení IP adres odběru vzorků dat výkonu datového seznamy pro instrukce sestavení, které byly přímo spuštěný, když nebyly shromážděny vzorky při spuštění profilace.

> [!NOTE]
> Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

|Sloupec|Popis|
|------------|-----------------|
|**ID procesu**|ID procesu (PID) běhu profilování.|
|**Název procesu**|Název procesu.|
|**Název modulu**|Název modulu, který obsahuje instrukce.|
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje instrukce.|
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje instrukce.|
|**Název funkce**|Název funkce, která obsahuje instrukce.|
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|
|**Adresa funkce**|Počáteční adresa paměti pro funkci načíst binárního souboru.|
|**Začátek řádku zdroje**|Počáteční řádek číslo ve zdrojovém souboru, ve kterém byl shromážděn této ukázce.|
|**Konec řádku zdroje**|Koncové číslo řádku ve zdrojovém souboru, ve kterém byl shromážděn této ukázce.|
|**Počáteční znak zdrojového kódu**|Odsazení počátečního znaku ve zdrojovém souboru řádku shromáždění této ukázce.|
|**Koncový znak zdrojového kódu**|Posun poslední znak v řádku zdrojového souboru shromáždění této ukázce.|
|**Adresa instrukce**|Adresa instrukce v načíst binární soubor.|
|**Výhradní vzorky**|Celkový počet vzorků, které byly shromážděny při provádění podle pokynů.|
|**% Výhradních vzorků**|Procento všechny ukázky v běhu profilování, které byly shromážděny při provádění podle pokynů.|

## <a name="see-also"></a>Viz také:
- [Ukazatele na instrukce (IP) zobrazení – vzorkování](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)