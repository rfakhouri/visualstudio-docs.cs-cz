---
title: "Zobrazení (IP) ukazatele na instrukce – Data kolizí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: f5e49c24-d4cf-4f87-977d-37e3223d1196
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3d6dcabe310743fee85c4560a0a37f029660bc90
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="instruction-pointers-ips-view---contention-data"></a>Zobrazení (IP) ukazatele na instrukce – Data kolizí
Zobrazení dat kolizí v IP adres zobrazí seznam dat pokyny sestavení, které byly blokovat spouštění v profilaci spustit.  
  
 Následující tabulka vysvětluje hodnot sloupce v zobrazení ukazatele na instrukce.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Výhradní blokované čas**|Blokované čas v této funkci.|  
|**Výhradní blokované čas: %**|Procento blokovaných čas při pokyn byla spuštěna.|  
|**Výhradní kolizí**|Počet kolizí, které došlo k chybě pokyn byla spuštěna.|  
|**% Výhradní kolizí**|Procento kolizí v profilaci spuštění, které došlo k chybě pokyn byla spuštěna.|  
|**Adresa funkce**|Počáteční adresa paměti funkce v načíst binárního souboru.|  
|**Název funkce**|Název funkce, která obsahuje pokyn.|  
|**Adresa instrukce**|Adresa paměti instrukce v načíst binárního souboru.|  
|**Číslo řádku – funkce**|Číslo řádku spuštění této funkce ve zdrojovém souboru.|  
|**Název modulu**|Název modul, který obsahuje pokyn.|  
|**Cesta modulu**|Cesta modul, který obsahuje pokyn.|  
|**ID procesu**|ID procesu (PID) PROFILOVANÉHO procesu.|  
|**Název procesu**|Název procesu.|  
|**Začátek znaku zdroje**|Posun znak v řádku souboru zdroje, na které tento pokyn začíná.|  
|**End znaku zdroje**|Posun znak v řádku souboru zdroje, u které tento pokyn končí.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje pokyn.|  
|**Začátek řádku zdroje**|Číslo řádku v zdrojový soubor, na které tento pokyn začíná.|  
|**End řádku zdroje**|Číslo řádku ve zdrojovém souboru, u které tento pokyn končí.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení ukazatele (IP) instrukcí](../profiling/instruction-pointers-ips-view.md)   
 [Ukazatele na instrukce (IP) zobrazení – vzorkování](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)   
 [Zobrazení ukazatelů na instrukce](../profiling/instruction-pointers-ips-view-sampling-data.md)