---
title: Zobrazení modulů – vzorkování dat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Modules view
- sampling profiling method,Modules view
ms.assetid: 816f5633-65d7-41e5-aee1-033628d4e2df
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 80bb263f395930b77ff31cbc68f4f9695879756a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="modules-view---sampling-data"></a>Zobrazení modulů – Data vzorkování
Zobrazení modulů vzorkování dat výkonu zobrazí data, která se seskupují po moduly, které byly vzorkovat v profilaci data. Každý modul je kořenem hierarchickou stromovou strukturu. Jen Vzorkovaná funkce modulu jsou uvedené pod tímto uzlem modulu.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Pokud se provádí funkce když byly shromažďovány ukázky (tj. funkce se v horní části zásobníku volání aplikace), zdroj čar a instrukce adresy, které byly provádění jsou uvedené pod tímto uzlem funkce. Protože je prováděna řádek nebo instrukce je řádku zdroje nebo ukazatele instrukce shromažďovat data, včetně a výhradní hodnoty jsou vždy stejné pro řádek data a instrukce data.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Jméno**|Název modulu, funkce, číslo řádku nebo adresa instrukce ukazatele.|  
|**ID procesu**|ID procesu (PID) z profilace spustit.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modul, který obsahuje funkce, čáry nebo instrukce ukazatele.|  
|**Cesta modulu**|Cesta modul, který obsahuje ukazatele modulu, funkce, čáry nebo instrukcí.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
|**Číslo řádku – funkce**|Číslo řádku spuštění této funkce ve zdrojovém souboru.|  
|**Ukázky (včetně).**|-Pro funkci Počet vzorků, ve kterých tuto funkci nebo funkci, která byla volána pomocí této funkce provádění; To znamená počet volání zásobníku vzorků, které obsahovaly tuto funkci.<br />-Pro modul se provádí počet vzorků, ve které alespoň jednu funkci z modulu.<br />-Pro řádek nebo instrukce, počet vzorků, ve které tento řádek nebo instrukce provádění.|  
|**% Ukázky (včetně).**|-Pro funkci nebo modul procento všechny ukázky v profilaci spuštění, které byly včetně ukázky této funkce nebo modul.<br />-Pro řádek nebo instrukce procento všechny ukázky v profilaci spustit ve které tento řádek nebo instrukce provádění.|  
|**Výhradní ukázky**|-Pro funkci Počet volání zásobníku ukázky, ve kterých tuto funkci přímo provádění; To znamená, počet vzorků, ve kterých byla tato funkce v horní části zásobníku volání.<br />-Pro modul, součet výhradní ukázky funkce v modulu.<br />-Pro řádek nebo instrukce, počet vzorků, ve které tento řádek nebo instrukce provádění.|  
|**% Výhradní ukázky**|-Pro funkci nebo modul procento všechny ukázky v profilaci spuštění, které byly výhradní ukázky této funkce nebo modul.<br />-Pro řádek nebo instrukce procento všechny ukázky v profilaci spustit ve které tento řádek nebo instrukce provádění.|  
  
## <a name="see-also"></a>Viz také  
 [Moduly zobrazení – vzorkování](../profiling/modules-view-dotnet-memory-sampling-data.md)   
 [Zobrazení modulů – instrumentace](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [Zobrazení modulů](../profiling/modules-view-instrumentation-data.md)