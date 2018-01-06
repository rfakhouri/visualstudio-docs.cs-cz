---
title: "Legenda zobrazení jader | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.cores.legend
helpviewer_keywords: Concurrency Visualizer, Cores View Legend
ms.assetid: e160384c-fcfe-49b3-86b7-229adb736c51
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cb7ae3c6bee8b75fd99edc7da150e71ef7394d63
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cores-view-legend"></a>Legenda zobrazení jader
Legenda zobrazení jader identifikuje každé vlákno barva a název. Obsahuje sloupce, které se zobrazí počty pro přepnutí kontextu cross-core, celkový kontextu přepínače a procent kontextu přepínače, které zasahují jader. Řádky v legendě jsou seřazené podle počtu přepnutí kontextu cross-core, v sestupném pořadí.  
  
 Můžete vybrat řádky v legendě pro filtrování vláken, které se zobrazují v časovou osu. V časové ose jsou uvedeny pouze vybrané vláken. Pokud nejsou vybrány žádné řádky, zobrazí se všechny řádky v časovou osu.  
  
 Mezi základní kontext přepínačů náklady na další v režijní náklady a výkon než přepínače, které zůstávají ve stejné logické jádra. Při přepnutí kontextu registry procesoru jsou uložený a obnovený, kód jádra operačního systému se spustí, jsou znovu načíst položky překladu Page Table Entry vyrovnávací paměti a procesoru kanál vyprazdňuje. Mezi základní kontext přepínače může být i dražší než jiné přepínače kontextu, protože data v mezipaměti není platná pro tento přístup z více vláken na jiné jádra. Naproti tomu Pokud vlákno kontextu přepnuta do jádra, které dřív spustil na, je pravděpodobné, že užitečné data jsou stále v mezipaměti. Když zvýšili mezi základní kontext přepínače pokoušejí spravovat přístup z více vláken je degradovaný spřažení a výkonu, zvažte, zda chcete-li vyřešit tento problém. Spusťte odstraněním spřažení vláken a pak pozorovat, jejich výsledné chování mezi procesory.  
  
 Následující tabulka popisuje prvky legendy.  
  
|Prvek|Definice|  
|-------------|----------------|  
|Název vlákna|Zobrazí barvu vlákno v předchozí časová osa jader a název tento přístup z více vláken.|  
|Mezi základní kontext přepínače|Počet kontextu přepínačů pro vlákno, které z jednoho logického jádra také přepnout do jiného. Ho nebude rozlišit mezi základní kontext přepínače, které mezi z die jeden procesor na jiný a ty, které zůstanou na stejném die.|  
|Celkový počet kontextu přepínače|Celkový počet přepínačů kontext pro dané vlákno během intervalu získávání vzorků. Pokaždé, když vlákno změny kontextu (například ze spuštění se synchronizací) jeden kontextu přepínač se počítá.|  
|Procento kontextu přepínače, které zasahují jader|Počítá se jako procento vydělením počtu přepnutí kontextu jádra mezi počtem celkový kontextu přepínače. Tím vyšší toto procento, tím vyšší celkový efekt režii mezi základní kontext přepne na výkon této konkrétní přístup z více vláken.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení jader](../profiling/cores-view.md)