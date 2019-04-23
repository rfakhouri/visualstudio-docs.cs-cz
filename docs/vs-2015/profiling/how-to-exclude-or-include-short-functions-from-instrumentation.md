---
title: 'Postupy: Vyloučení nebo zahrnutí krátkých funkcí z instrumentace | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, instrument events
- profiling tools, include short functions
- profiling tools, exclude short functions
ms.assetid: eaeead79-aafe-4490-86ff-6ed4cad9c15f
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c8bb49e650f2395bac8a3b5eb1d0f52e2e168731
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60078587"
---
# <a name="how-to-exclude-or-include-short-functions-from-instrumentation"></a>Postupy: Vyloučení nebo zahrnutí krátkých funkcí z instrumentace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ve výchozím nastavení, nástroje pro profilaci vyloučit *malé funkce* z instrumentace. Malé funkce jsou krátkých funkcí, které Nedovolte, aby byly všechny volání funkce. Kromě těchto malé funkce poskytuje pro menší nároky na instrumentace a proto zlepšit rychlost instrumentace. Vyloučení malé funkce taky snižuje velikost souboru (.vsp) výkonu profilování dat a čas, který je vyžadován pro analýzu. Pokud jsou malé funkce vyloučit, čas, který byl stráven malé funkce počítat celkové a výhradní čas jejich nadřazené funkce. Malé funkce můžete vyloučit nebo součástí instrumentace, jak je popsáno v následujícím postupu.  
  
### <a name="to-exclude-or-include-short-functions-from-instrumentation"></a>Vyloučení nebo zahrnutí krátkých funkcí z instrumentace  
  
1. V **prohlížeč výkonu**vyberte **relace výkonu** a pak klikněte pravým tlačítkem a vyberte **vlastnosti**.  
  
     **Stránky vlastností** se zobrazí dialogové okno.  
  
2. V **stránky vlastností**, klikněte na tlačítko **instrumentace** vlastnosti.  
  
3. Chcete-li vyloučení krátkých funkcí z instrumentace, vyberte **vyloučení krátkých funkcí z instrumentace**. Toto je výchozí nastavení.  
  
     -nebo-  
  
     Chcete-li zahrnout krátkých funkcí instrumentace, zrušte **vyloučení krátkých funkcí z instrumentace**.  
  
4. Klikněte na **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Řízení sběru dat](../profiling/controlling-data-collection.md)   
 [Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)
