---
title: 'Postupy: Serializace informací o symbolu | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Performance.General
helpviewer_keywords:
- profiling tools, serializing symbol information
- performance tools, serializing symbol information
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f7957917c999396f2e09bbb697474beb47ebcc47
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55042436"
---
# <a name="how-to-serialize-symbol-information"></a>Postupy: Serializace informací o symbolu
Může serializovat symboly, které potřebujete k analýze vaší aplikace. Serializace symbolu přidá symboly. *vsp* souboru. Přidejte informace o symbolech pro. *vsp* souboru, ostatní analyzovat sestavu výkonu bez nutnosti přístupu k původní symboly. Pokud nejsou serializován symboly, musíte mít původní instrumentovány. *exe* a. *soubor PDB* souborů k analýze. *Vsp* souboru.  
  
### <a name="to-automatically-serialize-symbol-information"></a>Automaticky serializovat informace o symbolech  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
     **Možnosti** se zobrazí dialogové okno.  
  
2.  Klikněte na tlačítko **nástroje pro měření výkonu**.  
  
3.  V části **obecné nastavení**vyberte **automaticky serializovat informace o symbolech**.  
  
## <a name="see-also"></a>Viz také:  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Postupy: Referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)   
 [Postupy: Uložit analyzovanou sestavu soubory](/previous-versions/visualstudio/visual-studio-2010/bb763106\(v\=vs.100\))