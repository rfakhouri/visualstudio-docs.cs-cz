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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5ae49e4656bcbeb8e1048331b9fb0b61849e4099
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53987590"
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