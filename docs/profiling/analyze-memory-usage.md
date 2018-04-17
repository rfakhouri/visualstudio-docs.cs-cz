---
title: Analýza využití paměti v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology:
- vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c9ed13bdb2bc94ca3ace19a6ffd4673525f1bc4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="analyze-memory-usage"></a>Analýza využití paměti
Použít integrované ladicí program **využití paměti** diagnostický nástroj Najít nevracení paměti a využití neefektivní paměti. Umožňuje nástroj využití paměti, proveďte jeden nebo více *snímky* heap spravovaná a nativní paměti. Můžete shromažďovat snímky .NET, nativní nebo smíšený režim (.NET a nativní) aplikace.  
  
-   Jeden snímek, abyste pochopili relativní dopad typy objektů na využití paměti a k nalezení kód ve vaší aplikaci, která používá paměti neefektivnímu můžete analyzovat.  
  
-   Také můžete porovnat (rozdílové) dva snímky najít oblastí v kódu aplikace způsobující využití paměti časem zvětšuje.  

Podrobné pokyny najdete v tématu [analýza využití paměti](../profiling/memory-usage.md) kurzu. Analýza využití paměti bez připojení ladicího programu, najdete v tématu [využití paměti bez ladicího programu](memory-usage-without-debugging2.md).
  
## <a name="blogs-and-videos"></a>Blogy a videa  

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video")  |    [Přehrát video,](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171) o používání nástroje diagnostiky, které ukazuje, jak analyzovat využití paměti a využití procesoru v aplikaci Visual Studio 2017. |

 [Analýza využití procesoru a paměti při ladění](https://blogs.msdn.microsoft.com/visualstudio/2016/02/15/analyze-cpu-memory-while-debugging/)  
  
 [Visual C++ Blog: Profilace paměti ve Visual C++ 2015](https://blogs.msdn.microsoft.com/vcblog/2015/10/21/memory-profiling-in-visual-c-2015/)  

## <a name="see-also"></a>Viz také
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)