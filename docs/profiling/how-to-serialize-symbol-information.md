---
title: "Postupy: serializace informací o symbolu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.Performance.General
helpviewer_keywords:
- profiling tools, serializing symbol information
- performance tools, serializing symbol information
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4941d3b5225a1d9c6b22eda3c8f79ef009f2b169
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-serialize-symbol-information"></a>Postupy: Serializace informací o symbolu
Znaky, které musí mít k analýze vaše aplikace může serializovat. Symbol serializace přidá do souboru .vsp symboly. Přidáním informací o symbolu k souboru .vsp ostatní můžete analyzovat Sestava výkonu bez nutnosti přístupu k původní symboly. Pokud nejsou serializované symboly, musíte mít soubory PDB k analýze souboru .vsp původní instrumentovaného .exe a.  
  
### <a name="to-automatically-serialize-symbol-information"></a>Chcete-li automaticky serializace informací o symbolu  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
     **Možnosti** se zobrazí dialogové okno.  
  
2.  Klikněte na tlačítko **nástroje pro sledování výkonu**.  
  
3.  V části **obecné nastavení**, vyberte **automaticky serializace informací o symbolu**.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Postupy: referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)   
 [Postupy: uložení analyzovali souborů sestav](http://msdn.microsoft.com/en-us/0340ddde-caf4-48ac-8af3-d15dcdade556)