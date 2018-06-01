---
title: Značky Vizualizéru souběžnosti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.markersui
ms.assetid: c4692d17-6cd2-4ad1-8590-d7275c771c70
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f59167b356f4a04b4b37e699fbe49f1ea82943e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692298"
---
# <a name="concurrency-visualizer-markers"></a>Značky Vizualizéru souběžnosti
Vizualizér souběžnosti značky jsou ikony, které představují události v aplikaci.  Obvykle se aplikace generuje těchto událostí k určení fáze nebo výskyty v aplikaci.  Události lze vygenerovat, aplikací nebo knihovny a moduly runtime, který používá aplikace.  
  
## <a name="kinds-of-markers"></a>Druhy značek  
 Vizualizér souběžnosti používá k reprezentaci události aplikace na tři druhy značek: flags zprávy a zahrnuje.  
  
1.  Použití *příznak* udávajících zajímavého bodu v čase ve vaší aplikaci.  Můžete například použít příznak představující, hodnota proměnné dosáhl určitou mez nebo došlo k výjimce.  
  
2.  A *zpráva* značky bod v době, ale můžete ji použít i pro stylu protokolu trasování.  Například co může mít byly zálohované do souboru protokolu, které můžete nyní zabalit do volání zpráva, aby mohli jeho trasování a zobrazení v vizualizér souběžnosti. Vizualizér souběžnosti také můžete tato data exportovat do souboru CSV.  
  
3.  A *span* představuje v intervalech ve vaší aplikaci, například jeden z jeho fází.  
  
## <a name="marker-linkage-to-threads"></a>Značky propojení vláken  
 Každé vlákno, který generuje značky má kanál časové osy.  ID podprocesu, který je zodpovědný za generování značky události se zobrazí vedle popis kanálu značky.  ID, které se zobrazí na levé straně kanálu značky odpovídá ID jiné vlákno v aktuálním procesu.  
  
## <a name="marker-importance"></a>Důležitost značky.  
 Značky může mít jednu z úrovní čtyři důležitosti: nízkou, Normální, vysoká a kritické.  Můžete filtrovat zdroje podle úrovně důležitosti značek.  Například pokud chcete najdete v části značky z určitého zdroje, který má význam normální nebo kritický stav, můžete nakonfigurovat filtru v [Upřesnit nastavení](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) dialogové okno. Význam značku se zobrazí na jeho popis a na [sestava značek](../profiling/markers-report.md).  
  
## <a name="marker-category"></a>Kategorie značky.  
 Kategorie značky označuje skupinu značky události, které pocházejí z jednoho zdroje.  Vizualizér souběžnosti používá k rozlišení různých kategorií příznaky a rozsahy barev. Vizualizér souběžnosti použití kategorie pro filtrování značky události od zprostředkovatele určitá událost můžete nakonfigurovat.  Použití [Upřesnit nastavení](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) dialogové okno Konfigurace filtru.  
  
## <a name="known-sources-of-markers"></a>Známé zdroje značek  
 Všechny zprostředkovatele trasování událostí pro Windows můžete vygenerovat značky, tak dlouho, dokud zprostředkovatele dodržuje určitá omezení. Vizualizér souběžnosti pro naslouchání na další událost zdroje pro označení můžete nakonfigurovat. Ve výchozím nastavení naslouchá na tyto zdroje událostí:  
  
-   [SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md)  
  
-   [Task Parallel Library (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl)  
  
-   [Tok dat](/dotnet/standard/parallel-programming/dataflow-task-parallel-library)  
  
-   [Paralelní LINQ (PLINQ)](/dotnet/standard/parallel-programming/parallel-linq-plinq)  
  
-   [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime)  
  
-   [Podpora scénář značky.](http://msdn.microsoft.com/en-us/e3b55bc2-b451-4214-ae00-0c7f5a5baec8)  
  
-   [C++ AMP (C++ Accelerated Massive Parallelism)](/cpp/parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism)  
  
 Můžete použít kartu značek v [Upřesnit nastavení](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) dialogové okno pro zobrazení nebo skrytí značek z různých zdrojů v Concurrency Visualizer a vy můžete filtrovat podle značky, na základě důležitosti a kategorie.  
  
## <a name="markers-from-eventsource"></a>Značky z EventSource  
 Vizualizér souběžnosti lze také zobrazit událostí EventSource.  Další informace najdete v tématu [událostí EventSource vizualizovat jako značky](../profiling/visualizing-eventsource-events-as-markers.md).  
  
## <a name="see-also"></a>Viz také:  
 [Značky příznaků](../profiling/flag-markers.md)   
 [Značky zpráv](../profiling/message-markers.md)   
 [Značky rozpětí](../profiling/span-markers.md)   
 [Vizualizace událostí EventSource v podobě značek](../profiling/visualizing-eventsource-events-as-markers.md)