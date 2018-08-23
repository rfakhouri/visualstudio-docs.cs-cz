---
title: 'Postupy: Konfigurace snížení šumu v zobrazeních sestav | Dokumentace Microsoftu'
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
- vs.performance.noisereduction.dialog
helpviewer_keywords:
- profiling tools, trimming
- profiling tools, report noise reduction
- profiling tools, folding
ms.assetid: b07e0375-bb73-47e3-8d1d-b9b492fb16c9
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee848f506a81b156309fa7e0d86891418251d0e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675941"
---
# <a name="how-to-configure-noise-reduction-in-report-views"></a>Postupy: Konfigurace snížení šumu v zobrazeních sestav
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: Konfigurace snížení šumu v zobrazeních sestav](https://docs.microsoft.com/visualstudio/profiling/how-to-configure-noise-reduction-in-report-views).  
  
Sestavy o výkonu lze nakonfigurovat pro snížení šumu tím, že omezíte množství dat, která jsou zobrazena v zobrazení stromu volání a přidělení. Pomocí snížení šumu jsou nejvážnějších problémy s výkonem. To je užitečné při analýze sestavy o výkonu.  
  
 Možnosti konfigurace snížení šumu zahrnují následující nastavení:  
  
-   **Ořezávání** při analýze sestavy zobrazení vynechá funkce, které spadají do nastavení hodnoty a prahové hodnoty, které jste nakonfigurovali, jak je popsáno v následujícím postupu oříznutí. Ve výchozím nastavení je povoleno oříznutí.  
  
-   **Skládání** Pokud povolíte skládání, budou sloučeny po sobě následující funkce na cestě, která odpovídají nastavení, které jste nakonfigurovali, jak je popsáno v postupu kontejner, který následuje. Ve výchozím nastavení je standardně povolená skládání.  
  
### <a name="to-configure-trimming-for-a-performance-report"></a>Ke konfiguraci ořezávání pro sestavu výkonu  
  
1.  Při zobrazení stromu volání nebo zobrazení přidělení se zobrazí v generované sestavě na **Developer** nabídky, klikněte na tlačítko **Profiler** a potom klikněte na tlačítko **možnosti snížení šumu**.  
  
     **Snížení šumu** zobrazí se dialogové okno.  
  
2.  Povolení ořezávání, postupujte podle těchto kroků:  
  
    1.  Vyberte **povolení ořezávání**. Toto je výchozí nastavení.  
  
        > [!NOTE]
        >  Pokud je povolené snížení šumu na informačním panelu se zobrazí v sestavě. Další informace najdete v tématu [zobrazení stromu volání](../profiling/call-tree-view.md) a [přidělení – zobrazení](../profiling/dotnet-memory-allocations-view.md).  
  
    2.  Nakonfigurovat pomocí nastavení hodnoty **hodnotu** rozevíracího seznamu a výběrem příslušné nastavení.  
  
    3.  Konfigurace nastavení požadované prahové hodnoty tak, že zadáte hodnotu v procentech v **prahová hodnota** textového pole.  
  
    4.  Pokud chcete povolit upozornění snížení šumu v generované sestavě, vyberte **zobrazovat upozornění, když je povolené snížení šumu**. Toto je výchozí nastavení.  
  
3.  Zakázat ořezávání, zrušte **povolení ořezávání**.  
  
4.  Klikněte na tlačítko **OK**.  
  
### <a name="to-configure-folding-for-a-performance-report"></a>Ke konfiguraci skládání pro sestavu výkonu  
  
1.  Na **Developer** nabídky, klikněte na tlačítko **Profiler** a potom klikněte na tlačítko **možnosti snížení šumu**.  
  
     **Snížení šumu** zobrazí se dialogové okno.  
  
2.  Pokud chcete povolit skládání, postupujte podle těchto kroků:  
  
    1.  Vyberte **Povolit skládání**. Toto je výchozí nastavení.  
  
        > [!NOTE]
        >  Pokud je povolené snížení šumu na informačním panelu se zobrazí v sestavě. Další informace najdete v tématu [zobrazení stromu volání](../profiling/call-tree-view.md) a [přidělení – zobrazení](../profiling/dotnet-memory-allocations-view.md).  
  
    2.  Nakonfigurovat pomocí nastavení hodnoty **hodnotu** rozevíracího seznamu a vyberte příslušné nastavení.  
  
    3.  Konfigurace nastavení požadované prahové hodnoty tak, že zadáte hodnotu v procentech v **prahová hodnota** textového pole.  
  
    4.  Pokud chcete povolit upozornění snížení šumu v generované sestavě, vyberte **zobrazovat upozornění, když je povolené snížení šumu**. Toto je výchozí nastavení.  
  
3.  Chcete-li zakázat skládání, zrušte **Povolit skládání**.  
  
4.  Klikněte na tlačítko **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení sestav nástrojů pro přizpůsobení výkonu](../profiling/customizing-performance-tools-report-views.md)   
 [Postupy: vyloučení nebo zahrnutí krátkých funkcí z instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)   
 [Zobrazení stromu volání](../profiling/call-tree-view.md)   
 [Přidělení – zobrazení](../profiling/dotnet-memory-allocations-view.md)



