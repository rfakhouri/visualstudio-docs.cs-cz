---
title: 'Postupy: Serializace informací o symbolu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Performance.General
helpviewer_keywords:
- profiling tools, serializing symbol information
- performance tools, serializing symbol information
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c4ea056c48525014fffad0243dfeb4dd40a8daa3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687015"
---
# <a name="how-to-serialize-symbol-information"></a>Postupy: Serializace informací o symbolu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Může serializovat symboly, které potřebujete k analýze vaší aplikace. Serializace symbolu přidá symbolů do souboru .vsp. Přidáním informací o symbolech do souboru .vsp ostatní analyzovat sestavu výkonu bez nutnosti přístupu k původní symboly. Pokud nejsou serializován symboly, musíte mít původní instrumentované .exe a soubory PDB k analýze souboru .vsp.  
  
### <a name="to-automatically-serialize-symbol-information"></a>Automaticky serializovat informace o symbolech  
  
1. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
     **Možnosti** se zobrazí dialogové okno.  
  
2. Klikněte na tlačítko **nástroje pro měření výkonu**.  
  
3. V části **obecné nastavení**vyberte **automaticky serializovat informace o symbolech**.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Postupy: Referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)   
 [Postupy: Uložit analyzovanou sestavu soubory](https://msdn.microsoft.com/0340ddde-caf4-48ac-8af3-d15dcdade556)
