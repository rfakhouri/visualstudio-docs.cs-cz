---
title: Vlákna podrobnosti zobrazení – Data kolizí | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.threaddetails
helpviewer_keywords:
- Thread Details view
ms.assetid: 874c3b1c-88d8-479a-bb35-1291d9aa8e67
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d45d2da94535f4f017fab838a661a3c3e4bc438d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="thread-details-view---contention-data"></a>Vlákna podrobnosti zobrazení – Data kolizí
Zobrazit podrobnosti o vlákně uvede časová osa grafu blokování událostí ve vybrané vlákno spuštění profilování, která byla způsobena kolizí nad zdroji. Blokování události dojde při vlákno je nucen se pozastavit provádění, protože jiné vlákno zablokuje přístup k prostředku.  
  
 Toto zobrazení představuje časovou osu provádění vlákna jako vodorovný pruh a blokování událostí jako svislá čára na vodorovné ose pro vlákno. Pokud je to nezbytné, můžete přiblížit na oddíl časové osy a zobrazte jednotlivé události. K zobrazení cesty provádění funkcí, které vedly k události, klikněte na panelu událostí. Funkce se zobrazí v okně zásobník volání. Pokud zdrojový kód pro funkce je k dispozici, můžete kliknout na název funkce upravit zdrojový soubor v prostředí Visual Studio IDE.  
  
## <a name="navigating-the-timeline"></a>Navigace na časové ose  
  
#### <a name="to-zoom-in-on-a-timeline-segment"></a>Chcete-li přiblížení segment časové osy  
  
-   Klikněte na tlačítko a přetáhněte ukazatel myši a vyberte oblast časovou osu.  
  
     Při uvolnění myši zvětší zobrazení na segmentu vybraný čas. Zvětšení podrobněji proces, můžete opakovat. Posouvací políčko posuvníku čas představuje relativní velikost segmentu čas, který se zobrazí v zobrazení.  
  
#### <a name="to-zoom-out-on-a-timeline"></a>Zvětšit na časové ose  
  
-   Klikněte na tlačítko **Oddálit** se vrátíte do předchozího úroveň přiblížení.  
  
-   Klikněte na tlačítko **zvětšení resetovat** zobrazit celý časové osy v zobrazení.  
  
#### <a name="to-view-the-call-stack-of-an-event"></a>Chcete-li zobrazit zásobníku volání na událost  
  
-   V tomto časová osa grafu klikněte na tlačítko svislá čára, který představuje událost...  
  
#### <a name="to-view-or-edit-the-source-code-of-a-function-in-the-call-stack"></a>Chcete-li zobrazit nebo upravit zdrojový kód funkce v zásobníku volání  
  
-   V okně zásobník volání klikněte na název funkce.  
  
 Zdrojový kód funkce musí být součástí aktuálního projektu.  
  
#### <a name="to-view-the-contention-events-of-a-resource-in-all-threads-in-the-profiling-run"></a>Zobrazit události kolizí prostředku v všechna vlákna v profilaci spustit  
  
-   V tomto časová osa grafu klikněte na název nebo id prostředku.  
  
     [Zobrazení podrobností o prostředku](../profiling/resource-details-view-contention-data.md) se zobrazí pro vybraný zdroj.  
  
#### <a name="to-view-the-thread-contention-data-in-the-processes-window"></a>Chcete-li zobrazit data kolizí přístup z více vláken v okně procesy  
  
-   V tomto časová osa grafu, klikněte na tlačítko **celkový**.  
  
     [Zobrazení procesů](../profiling/process-view-contention-data.md) se zobrazí s vlákno vybrané.