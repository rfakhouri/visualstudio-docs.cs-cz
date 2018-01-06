---
title: "Postupy: vyloučení nebo zahrnutí funkce CShort z instrumentace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, instrument events
- profiling tools, include short functions
- profiling tools, exclude short functions
ms.assetid: eaeead79-aafe-4490-86ff-6ed4cad9c15f
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1238e092bf1b088ba9ce377aeaf66b1fa953f1bc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-exclude-or-include-short-functions-from-instrumentation"></a>Postupy: Vyloučení funkce CShort z instrumentace nebo je zahrnout do instrumentace
Ve výchozím nastavení, nástroje pro profilování vyloučit *malé funkce* z instrumentace. Malé funkce jsou krátkých funkcí, které neprovádějte žádné volání funkcí. Kromě těchto funkcí malé poskytuje pro menší nároky na instrumentace a proto zlepšení instrumentace rychlost. Vyloučení malé funkce taky snižuje velikost souboru (.vsp) výkonu profilování data a času, který je vyžadován pro analýzu. Pokud malá funkce jsou vyloučeny, času stráveného v malých funkce započítává výhradní a včetně době jejich nadřazené funkce. Malé funkce můžete vyloučit nebo součástí instrumentace, jak je popsáno v následujícím postupu.  
  
### <a name="to-exclude-or-include-short-functions-from-instrumentation"></a>K vyloučení nebo zahrnutí funkce CShort z instrumentace  
  
1.  V **prohlížeč výkonu**, vyberte **výkonnostní relace** a potom klikněte pravým tlačítkem a vyberte **vlastnosti**.  
  
     **Stránky vlastností** se zobrazí dialogové okno.  
  
2.  V **stránky vlastností**, klikněte **instrumentace** vlastnosti.  
  
3.  Vyloučení krátkých funkcí z instrumentace, vyberte **vyloučení krátkých funkcí z instrumentace**. Toto je výchozí nastavení.  
  
     -nebo-  
  
     Chcete-li zahrnout krátkých funkcí instrumentace, zrušte **vyloučení krátkých funkcí z instrumentace**.  
  
4.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Řízení shromažďování dat](../profiling/controlling-data-collection.md)   
 [Vlastnosti výkonnostní relace](../profiling/performance-session-properties.md)