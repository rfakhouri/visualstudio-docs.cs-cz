---
title: Sestava profilu spuštění | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Profile Report
ms.assetid: c8128472-a8ed-46f4-b1c8-a25358d6f2c1
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a0d95d4593939b878194d2aeef79bdd0a8ad946a
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54756514"
---
# <a name="execution-profile-report"></a>Sestava profilu spuštění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sestava profilu spuštění je profil pro tradiční vzorkování. Vzorky jsou přibližně každých milisekund během období, kdy vlákno běží na logické jádro a Vizualizátor souběžnosti sestavení typické volání stromu po nahromaděné sadu zásobníky ukázka kolační. Data v této tabulce mohou mít vliv aktuální časový rozsah a skryté vlákna a tyto filtry, které mohou být použity:  
  
- Pokud je vybrána pouze můj kód, jsou uvedeny pouze bloky zásobníku, které mají kód uživatele a jednu úroveň pod uživatelského kódu.  
  
- Pokud je nastavena hodnota snížení šumu, porovnávány zásobníky, kterých je nižší než zadané frekvence jsou filtrovány ze sestavy  
  
  V následující tabulce jsou uvedeny sloupců v sestavě.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|Název|Název funkce pro každou úroveň zásobníku volání.|  
|Celkových vzorků|Celkový počet vzorků, které byly shromážděny pro všechny balíčky, které jsou zahrnuty do této úrovně stromu zásobníku volání. Celkový počet je součtem výhradních vzorků pro tuto funkci a včetně čítačů pro všechny jeho podřízené uzly.|  
|Výhradní vzorky|Celkový počet shromážděných vzorků, pro které tato funkce je nejnižší úroveň zásobníku volání.|  
|% Celkový čas|Procento celkového počtu vzorků, které se zobrazí ve sloupci celkových vzorků. Procenta jsou zaokrouhleny na dvě desetinná místa.|  
|% Výhradních|Procento celkového počtu vzorků, které se zobrazí ve sloupci výhradních vzorků. Procenta jsou zaokrouhleny na dvě desetinná místa.|  
|Podrobnosti|Plně kvalifikovaný název funkce. To zahrnuje počet řádků, až bude k dispozici.|  
  
 Tato tabulka sestavy si můžete prohlédnout ve [doba spuštění (zobrazení vláken)](../profiling/execution-time-threads-view.md) zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)
