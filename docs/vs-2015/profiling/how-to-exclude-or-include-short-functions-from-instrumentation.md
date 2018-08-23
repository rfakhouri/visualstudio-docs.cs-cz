---
title: 'Postupy: vyloučení nebo zahrnutí krátkých funkcí z instrumentace | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profiling tools, instrument events
- profiling tools, include short functions
- profiling tools, exclude short functions
ms.assetid: eaeead79-aafe-4490-86ff-6ed4cad9c15f
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f02e34e9fdb399aa8078342d3a8441f077a60f66
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676147"
---
# <a name="how-to-exclude-or-include-short-functions-from-instrumentation"></a>Postupy: Vyloučení funkce CShort z instrumentace nebo je zahrnout do instrumentace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [jak: vyloučit nebo zahrnout funkce CShort z instrumentace](https://docs.microsoft.com/visualstudio/profiling/how-to-exclude-or-include-short-functions-from-instrumentation).  
  
Ve výchozím nastavení, nástroje pro profilaci vyloučit *malé funkce* z instrumentace. Malé funkce jsou krátkých funkcí, které Nedovolte, aby byly všechny volání funkce. Kromě těchto malé funkce poskytuje pro menší nároky na instrumentace a proto zlepšit rychlost instrumentace. Vyloučení malé funkce taky snižuje velikost souboru (.vsp) výkonu profilování dat a čas, který je vyžadován pro analýzu. Pokud jsou malé funkce vyloučit, čas, který byl stráven malé funkce počítat celkové a výhradní čas jejich nadřazené funkce. Malé funkce můžete vyloučit nebo součástí instrumentace, jak je popsáno v následujícím postupu.  
  
### <a name="to-exclude-or-include-short-functions-from-instrumentation"></a>Vyloučení nebo zahrnutí krátkých funkcí z instrumentace  
  
1.  V **prohlížeč výkonu**vyberte **relace výkonu** a pak klikněte pravým tlačítkem a vyberte **vlastnosti**.  
  
     **Stránky vlastností** se zobrazí dialogové okno.  
  
2.  V **stránky vlastností**, klikněte na tlačítko **instrumentace** vlastnosti.  
  
3.  Chcete-li vyloučení krátkých funkcí z instrumentace, vyberte **vyloučení krátkých funkcí z instrumentace**. Toto je výchozí nastavení.  
  
     -nebo-  
  
     Chcete-li zahrnout krátkých funkcí instrumentace, zrušte **vyloučení krátkých funkcí z instrumentace**.  
  
4.  Klikněte na tlačítko **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Řízení sběru dat](../profiling/controlling-data-collection.md)   
 [Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)



