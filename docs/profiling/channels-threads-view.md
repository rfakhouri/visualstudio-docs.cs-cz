---
title: "Kanály (zobrazení vláken) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.channelnames
helpviewer_keywords: Concurrency Visualizer, Channels (Threads View)
ms.assetid: 2f798c17-2363-42a4-be94-a5751d208eac
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 74d0796b1d2d3ecbe3ff08cc1eb4cfe79153f738
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="channels-threads-view"></a>Kanály (Zobrazení vláken)
Vizualizér souběžnosti znázorňuje čtyři typy kanály: vláken kanály, disku kanály, značky kanálů a kanály GPU.  
  
## <a name="thread-channels"></a>Kanály přístup z více vláken  
 Vlákno kanál, který ukazuje stav vlákna pomocí barev pro právě jedno vlákno. Při přesunutí ukazatele myši na název kanálu, zobrazí se funkce start pro dané vlákno. Vizualizér souběžnosti zjistí několik druhů vláken. V následující tabulce jsou uvedeny nejčastější typy.  
  
|||  
|-|-|  
|Hlavní vlákno|Vlákno, které spuštění aplikace.|  
|Pracovní vlákna|Vlákno, které pochází z hlavního vlákna aplikace.|  
|Pracovní podproces CLR|Pracovní podproces, který byl vytvořen common language runtime (CLR).|  
|Pomocník ladicí program|Pracovní podproces, který byl vytvořen pomocí ladicího programu sady Visual Studio.|  
|ConcRT přístup z více vláken|Vlákno, které vytvořil Microsoft Concurrency Runtime.|  
|GDI přístup z více vláken|Podproces, který byl vytvořen GDIPlus.|  
|OLE/RPC přístup z více vláken|Vlákno, která byla vytvořena jako pracovní vlákno RPC.|  
|RPC přístup z více vláken|Vlákno, která byla vytvořena jako podproces RPC.|  
|Rozhraní Winsock přístup z více vláken|Vlákno, která byla vytvořena jako vlákno rozhraní Winsock.|  
|Fondu vláken|Vlákno, které pochází z fondu podprocesů CLR.|  
  
## <a name="disk-channels"></a>Kanály disku  
 Kanály disku odpovídají fyzické jednotky v počítači. Protože samostatné kanály pro operace čtení a zápisu pro každý fyzický disk v systému existuje, každé jednotky, má dva kanály. Čísla disků odpovídají názvy zařízení jádra. Kanál disku se zobrazí, jenom Pokud byl na disku aktivity.  
  
## <a name="marker-channels"></a>Kanály značky.  
 Značky kanály odpovídají událostí generovaných aplikace a knihovny, které používá. Například Task Parallel Library, Parallel Library vzory a C++ AMP generovat události, které se zobrazují jako značky. Každý kanál značky je přidružen ID vlákna, který se zobrazí vedle popis kanálu. ID identifikuje vlákno, které vygenerovalo událost. Popis kanál obsahuje název zprostředkovatele trasování událostí pro Windows (ETW), která vygenerovala události. Pokud kanál zobrazí události z [SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md), zobrazí se také název řady.  
  
## <a name="gpu-channels"></a>Kanály GPU  
 Kanály GPU zobrazit informace o aktivitě DirectX 11 v systému.  Každý motor DirectX, který je spojen s grafické karty má samostatný kanál.  Jednotlivé segmenty představují čas, který má strávený zpracováváním paket přímý přístup do paměti.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)