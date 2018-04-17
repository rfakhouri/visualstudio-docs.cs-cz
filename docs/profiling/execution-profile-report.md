---
title: Sestava profilu spuštění | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Profile Report
ms.assetid: c8128472-a8ed-46f4-b1c8-a25358d6f2c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b2f878efffd658cbfa243ae4947613603db59777
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="execution-profile-report"></a>Sestava profilu spuštění
Sestava profilu spuštění je profil tradiční vzorkování. Vzorků přibližně každých milisekundu během období při vlákno je spuštěn na logická jádra a vizualizér souběžnosti vytvoří strom typické volání pomocí kompletování Akumulovaná sadu zásobníky ukázka. Aktuální časové rozmezí a skrytá vláken a tyto filtry, které mohou být použity, může mít vliv dat v této tabulce:  
  
-   Pokud je vybrána pouze můj kód, jsou zobrazeny pouze rámce zásobníku, které mají uživatelského kódu, plus o jednu úroveň pod uživatelského kódu.  
  
-   Pokud je nastavena hodnota snížení šumu, kompletován zásobníky, které mají menší než zadaná četnost jsou filtrovány mimo sestavy  
  
 V následující tabulce jsou uvedeny sloupce v sestavě.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|Název|Název funkce pro každou úroveň zásobníku volání.|  
|Ukázky (včetně).|Celkový počet vzorků, které se shromažďují pro všechny balíčky, které zahrnuta do této úrovni stromu zásobníku volání. Číslo (včetně) je součet hodnot výhradní ukázky pro tuto funkci a včetně čítačů pro všechny jeho podřízené uzly.|  
|Výhradní ukázky|Celkový počet shromažďovaných vzorků, pro které tato funkce je nejnižší úroveň zásobníku volání.|  
|% Vnitřní|Procento celkového počtu vzorků, které se zobrazí ve sloupci včetně ukázky. Procentuální hodnoty jsou zaokrouhleny na dvě desetinná místa.|  
|% Exkluzivní|Procento celkového počtu vzorků, které se zobrazí ve sloupci výhradní ukázky. Procentuální hodnoty jsou zaokrouhleny na dvě desetinná místa.|  
|Podrobnosti|Plně kvalifikovaný název funkce. To zahrnuje počet řádků, pokud je k dispozici.|  
  
 Tato tabulka sestavy si můžete prohlédnout ve [doba spuštění (zobrazení vláken)](../profiling/execution-time-threads-view.md) zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)