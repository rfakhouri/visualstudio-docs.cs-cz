---
title: 'Postupy: serializace informací o symbolu | Dokumentace Microsoftu'
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
- VS.ToolsOptionsPages.Performance.General
helpviewer_keywords:
- profiling tools, serializing symbol information
- performance tools, serializing symbol information
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04bce9383142ee6916fa7ade50feda072019f530
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673092"
---
# <a name="how-to-serialize-symbol-information"></a>Postupy: Serializace informací o symbolu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: serializace informací o symbolu](https://docs.microsoft.com/visualstudio/profiling/how-to-serialize-symbol-information).  
  
Může serializovat symboly, které potřebujete k analýze vaší aplikace. Serializace symbolu přidá symbolů do souboru .vsp. Přidáním informací o symbolech do souboru .vsp ostatní analyzovat sestavu výkonu bez nutnosti přístupu k původní symboly. Pokud nejsou serializován symboly, musíte mít původní instrumentované .exe a soubory PDB k analýze souboru .vsp.  
  
### <a name="to-automatically-serialize-symbol-information"></a>Automaticky serializovat informace o symbolech  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
     **Možnosti** se zobrazí dialogové okno.  
  
2.  Klikněte na tlačítko **nástroje pro měření výkonu**.  
  
3.  V části **obecné nastavení**vyberte **automaticky serializovat informace o symbolech**.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Postupy: referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)   
 [Postupy: uložení analyzovat soubory sestav](http://msdn.microsoft.com/en-us/0340ddde-caf4-48ac-8af3-d15dcdade556)



