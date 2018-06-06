---
title: 'Postupy: serializace informací o symbolu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: a86c7171b781f85ae4679209519267adcadcc090
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573307"
---
# <a name="how-to-serialize-symbol-information"></a>Postupy: serializace informací o symbolu
Znaky, které musí mít k analýze vaše aplikace může serializovat. Symbol serializace přidá symbolů do. *vsp* souboru. Přidáním symbol informace na. *vsp* souboru, ostatní analyzovat Sestava výkonu bez nutnosti přístupu k původní symboly. Pokud nejsou serializované symboly, musíte mít původní instrumentovány. *exe* a. *pdb* soubory k analýze. *Vsp* souboru.  
  
### <a name="to-automatically-serialize-symbol-information"></a>Chcete-li automaticky serializace informací o symbolu  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
     **Možnosti** se zobrazí dialogové okno.  
  
2.  Klikněte na tlačítko **nástroje pro sledování výkonu**.  
  
3.  V části **obecné nastavení**, vyberte **automaticky serializace informací o symbolu**.  
  
## <a name="see-also"></a>Viz také:  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Postupy: odkaz na Windows symbolů informace](../profiling/how-to-reference-windows-symbol-information.md)   
 [Postupy: uložení analyzovali souborů sestav](http://msdn.microsoft.com/en-us/0340ddde-caf4-48ac-8af3-d15dcdade556)