---
title: Kanály (zobrazení vláken) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.channelnames
helpviewer_keywords:
- Concurrency Visualizer, Channels (Threads View)
ms.assetid: 2f798c17-2363-42a4-be94-a5751d208eac
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e4b67d4c4b2f3faf6147942b78a23999fdebb294
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669902"
---
# <a name="channels-threads-view"></a>Kanály (Zobrazení vláken)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kanály (zobrazení vláken)](https://docs.microsoft.com/visualstudio/profiling/channels-threads-view).  
  
Vizualizátor souběžnosti zobrazí čtyři typy kanálů: vláken kanály, disk kanály, značky kanálů a kanály GPU.  
  
## <a name="thread-channels"></a>Vláken kanály  
 Vlákno kanálu zobrazí stav vlákna, pomocí barev, pro pouze jedno vlákno. Při přesunutí ukazatele myši na název kanálu, zobrazí se spuštění funkce pro dané vlákno. Vizualizátor souběžnosti zjistí, několik druhů vlákna. Nejběžnější typy jsou uvedeny v následující tabulce.  
  
|||  
|-|-|  
|Hlavní vlákno|Podproces, který spustil aplikaci.|  
|Pracovní podproces|Vlákno, které bylo vytvořeno pomocí hlavního vlákna aplikace.|  
|Pracovní vlákno CLR|Pracovní podproces, který byl vytvořen modulem common language runtime (CLR).|  
|Nápověda ladicího programu|Pracovní podproces, který byl vytvořen pomocí ladicího programu sady Visual Studio.|  
|Vlákno ConcRT|Podproces, který byl vytvořen pomocí modulu Runtime souběžnosti Microsoft.|  
|Vlákno rozhraní GDI|Podproces, který byl vytvořen GDIPlus.|  
|Vlákno OLE/RPC|Podproces, který byl vytvořen jako podproces RPC.|  
|Vlákno RPC|Podproces, který byl vytvořen jako podproces RPC.|  
|Vlákno rozhraní Winsock|Podproces, který byl vytvořen jako vlákno rozhraní Winsock.|  
|Fondu vláken|Podproces, který byl vytvořen ve fondu vláken CLR.|  
  
## <a name="disk-channels"></a>Kanály disku  
 Kanály disku odpovídají fyzické jednotky v počítači. Vzhledem k tomu, že pro každý fyzický disk systému existují samostatné kanály pro operace čtení a zápisu, každá jednotka má dva kanály. Čísla disků odpovídat názvu zařízení jádra. Disk kanál se zobrazí pouze pokud byla nějaká aktivita na disku.  
  
## <a name="marker-channels"></a>Kanály značky  
 Značky kanály odpovídají události generované modulem aplikace a knihovny, které používá. Například Task Parallel Library, knihovny Ppl a jazyka C++ AMP generovat události, které se zobrazí jako značky. Každý kanál značky je přidružená ID vlákna, které se zobrazí vedle popis kanálu. Identifikuje ID vlákna, které vygenerovalo událost. Popis kanálu obsahuje název zprostředkovatele trasování událostí pro Windows (ETW), který vygeneruje události. Pokud kanál se zobrazí události od [sada Vizualizátor souběžnosti SDK](../profiling/concurrency-visualizer-sdk.md), zobrazí se také název řady.  
  
## <a name="gpu-channels"></a>Kanály GPU  
 Kanály GPU zobrazení informací o činnosti rozhraní DirectX 11 v systému.  Každý motor rozhraní DirectX, který je spojen s grafickou kartu má samostatný kanál.  Jednotlivé segmenty představují čas, který má strávený zpracováním paketů DMA.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)



