---
title: "Vizualizér souběžnosti | Microsoft Docs"
ms.custom: 
ms.date: 07/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.performance.viewnavigation
- vs.cv.overview
- vs.cv.performance.gettingstarted
- vs.cv.gettingstarted
helpviewer_keywords: Concurrency Visualizer, Concurrency Visualizer
ms.assetid: ae5879a0-1e1a-455a-ba72-148e57f59289
caps.latest.revision: "31"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 362daf0d3044841260ae7e9b8f0eb42bad8e610b
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="concurrency-visualizer"></a>Vizualizér souběžnosti
> [!NOTE]
>  Vizualizér souběžnosti je volitelné rozšíření pro Visual Studio. Stáhněte vizualizér souběžnosti a nástroje pro Concurrency Visualizer kolekce z následujících odkazů:  
>   
>  -   Stažení [vizualizér souběžnosti pro Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.ConcurrencyVisualizer2017#overview) rozšíření.  
>  -   Stažení [vizualizér souběžnosti pro Visual Studio 2015](https://visualstudiogallery.msdn.microsoft.com/a6c24ce9-beec-4545-9261-293061436ee9) rozšíření.  
> -   Stažení [Concurrency Visualizer kolekce nástrojů pro Visual Studio 2015](http://www.microsoft.com/en-in/download/details.aspx?id=49103).  
>   
>      [Concurrency Visualizer příkazového řádku nástroje (CVCollectionCmd)](../profiling/concurrency-visualizer-command-line-utility-cvcollectioncmd.md) umožňuje shromažďovat trasování z příkazového řádku, který si můžete prohlédnout v Concurrency Visualizer pro Visual Studio 2015. Nástroj můžete použít na počítačích, které nemají nainstalovanou sadu Visual Studio.  
  
 Vizualizér souběžnosti můžete najdete v části Jak vícevláknové aplikace provede. Zobrazení v Concurrency Visualizer poskytovat grafického rozhraní, tabulkový a textové data, která znázorňuje dočasné vztahy mezi vláken v programu a systém jako celek. Vizualizér souběžnosti vám pomůže najít kritické body, procesoru nedostatečné, kolizí přístup z více vláken, migrace mezi jádra podprocesu, synchronizace zpoždění, DirectX aktivity, oblasti překryté vstupně-výstupních operací a další informace. Zobrazení zadejte data, která může fungovat na pomocí propojení jeho grafického výstupu volat zásobníky a zdrojového kódu.  

> [!NOTE]
>  Vizualizér souběžnosti nepodporuje webové projekty.  
  
 Vizualizér souběžnosti spoléhá na [trasování událostí pro Windows](http://go.microsoft.com/fwlink/?LinkId=234579) funkce.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Zobrazení využití](../profiling/utilization-view.md)|Popisuje, jak můžete zobrazit a analyzovat aktivity systému do všech procesorů.|  
|[Zobrazení vláken](../profiling/threads-view-parallel-performance.md)|Popisuje, jak analyzovat interakce mezi vlákny v programu.|  
|[Zobrazení jader](../profiling/cores-view.md)|Popisuje, jak analyzovat vlákno migrace mezi jader.|  
|[Obecné vzory pro vícevláknové aplikace s nevhodným chováním](../profiling/common-patterns-for-poorly-behaved-multithreaded-applications.md)|Popisuje několik běžných vzorů a ukazuje, jak se zobrazují v vizualizér souběžnosti.|  
|[Paralelní vývoj v sadě Visual Studio blogu](http://go.microsoft.com/fwlink/?LinkId=235385)|Poskytuje tipy a osvědčené postupy pro Concurrency Visualizer.|  
|[Zobrazení sestav výkonu](../profiling/performance-report-views.md)|Poskytuje referenční informace pro sestavy a zobrazení profilace nástroje sady Visual Studio.|  
|[SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md)|Popisuje, jak k instrumentaci vašeho zdrojového kódu a zobrazte další informace v vizualizér souběžnosti.|  
|[Nástroj příkazového řádku ve Vizualizéru souběžnosti (CVCollectionCmd)](../profiling/concurrency-visualizer-command-line-utility-cvcollectioncmd.md)|Popisuje, jak používat nástroj příkazového řádku Vizualizéru souběžnosti (CVCollectionCmd.exe) ke sběru a zpracování trasování na počítačích, které nemají v sadě Visual Studio.|  
  
## <a name="see-also"></a>Viz také  
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)
